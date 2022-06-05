# Why Redux Toolkit is How To Use Redux Today
What is Redux Toolkit?


Redux Toolkit (also known as "RTK" for short) is our official recommended approach for writing Redux logic. The @reduxjs/toolkit package wraps around the core redux package, and contains API methods and common dependencies that we think are essential for building a Redux app. Redux Toolkit builds in our suggested best practices, simplifies most Redux tasks, prevents common mistakes, and makes it easier to write Redux applications.

RTK includes utilities that help simplify many common use cases, including store setup, creating reducers and writing immutable update logic, and even creating entire "slices" of state at once.


## How Redux Toolkit Is Different Than the Redux Core

What Is "Redux"?
The first thing to ask is, "what is Redux?"

Redux is really:

- A single store containing "global" state
Dispatching plain object actions to the store when something happens in the app

- Pure reducer functions looking at those actions and returning immutably updated state

While it's not required, your Redux code also normally includes:

- Action creators that generate those action objects
Middleware to enable side effects

- Thunk functions that contain sync or async logic with side effects
Normalized state to enable looking up items by ID

- Memoized selector functions with the Reselect library for optimizing derived data

- The Redux DevTools Extension to view your action history and state changes

- TypeScript types for actions, state, and other functions



## What Does the Redux Core Do?
The Redux core is a very small and deliberately unopinionated library. It provides a few small API primitives:

- createStore to actually create a Redux store
- combineReducers to combine multiple slice reducers into a single larger reducer
- applyMiddleware to combine multiple middleware into a store enhancer
- compose to combine multiple store enhancers into a single store enhancer


## What Does Redux Toolkit Do?
While these were the patterns originally shown in the Redux docs, they unfortunately require a lot of very verbose and repetitive code. Most of this boilerplate isn't necessary to use Redux. On top of that, the boilerplate-y code lead to more opportunities to make mistakes.

We specifically created Redux Toolkit to eliminate the "boilerplate" from hand-written Redux logic, prevent common mistakes, and provide APIs that simplify standard Redux tasks.

Redux Toolkit starts with two key APIs that simplify the most common things you do in every Redux app:

- configureStore sets up a well-configured Redux store with a single function call, including combining reducers, adding the thunk middleware, and setting up the Redux DevTools integration. It also is easier to configure than createStore, because it takes named options parameters.

- createSlice lets you write reducers that use the Immer library to enable writing immutable updates using "mutating" JS syntax like state.value = 123, with no spreads needed. It also automatically generates action creator functions for each reducer, and generates action type strings internally based on your reducer's names. Finally, it works great with TypeScript

That means that the code you write can be drastically simpler. For example:

import { createSlice } from '@reduxjs/toolkit'

const todosSlice = createSlice({
  name: 'todos',
  initialState: [],
  reducers: {
    todoAdded(state, action) {
      state.push({
        id: action.payload.id,
        text: action.payload.text,
        completed: false
      })
    },
    todoToggled(state, action) {
      const todo = state.find(todo => todo.id === action.payload)
      todo.completed = !todo.completed
    }
  }
})

export const { todoAdded, todoToggled } = todosSlice.actions
export default todosSlice.reducer


All of the action creators and action types are generated automatically, and the reducer code is shorter and easier to understand. It's also much more clear what's actually being updated in each case.

With configureStore, the store setup can be simplified down to:

import { configureStore } from '@reduxjs/toolkit'
import todosReducer from '../features/todos/todosSlice'
import filtersReducer from '../features/filters/filtersSlice'

export const store = configureStore({
  reducer: {
    todos: todosReducer,
    filters: filtersReducer
  }
})


Note that this one configureStore call automatically does all the usual setup work you'd have done manually:

- The slice reducers were automatically passed to combineReducers()
- The redux-thunk middleware was automatically added
- Dev-mode middleware was added to catch accidental mutations
- The Redux DevTools Extension was automatically set up
- The middleware and DevTools enhancers were composed together and added to the store

At the same time, configureStore provides the options to let users modify any of those default behaviors (like turning off thunks and adding sagas, or disabling the DevTools in production),

From there, Redux Toolkit includes other APIs for common Redux tasks:

- createAsyncThunk: abstracts the standard "dispatch actions before/after an async request" pattern

- createEntityAdapter: prebuilt reducers and selectors for CRUD operations on normalized state

- createSelector: a re-export of the standard Reselect API for memoized selectors
createListenerMiddleware: a side effects middleware for running logic in response to dispatched actions


Finally, the RTK package also includes "RTK Query", a full data fetching and caching solution for Redux apps, as a separate optional @reduxjs/toolkit/query entry point. It lets you define endpoints (REST, GraphQL, or any async function), and generates a reducer and middleware that fully manage fetching data, updating loading state, and caching results. It also automatically generates React hooks that can be used in components to fetch data, like const { data, isFetching} = useGetPokemonQuery('pikachu')

Each of these APIs is completely optional and designed for specific use cases, and you can pick and choose which APIs you actually use in your app. But, all of them are highly recommended to help with those tasks.

Note that Redux Toolkit is still "Redux"! There's still a single store, with dispatched action objects for updates, and reducers that immutably update state, plus the ability to write thunks for async logic, manage normalized state, type your code with TypeScript, and use the DevTools. There's just way less code you have to write for the same results!
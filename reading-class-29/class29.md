
# useReducer Hook :
it is a hook used for state management and it is an alternative for useState hook

## Syntax :

const [state, dispatch] = useReducer(reducer, initialArg, init);

****************************************************************
The reducer function contains your custom state logic and the initialStatecan be a simple value but generally will contain an object.

The useReducer Hook returns the current stateand a dispatchmethod.

Here is an example of useReducer in a counter app:

Example:
import { useReducer } from "react";
import ReactDOM from "react-dom/client";

const initialTodos = [
  {
    id: 1,
    title: "Todo 1",
    complete: false,
  },
  {
    id: 2,
    title: "Todo 2",
    complete: false,
  },
];

const reducer = (state, action) => {
  switch (action.type) {
    case "COMPLETE":
      return state.map((todo) => {
        if (todo.id === action.id) {
          return { ...todo, complete: !todo.complete };
        } else {
          return todo;
        }
      });
    default:
      return state;
  }
};

function Todos() {
  const [todos, dispatch] = useReducer(reducer, initialTodos);

  const handleComplete = (todo) => {
    dispatch({ type: "COMPLETE", id: todo.id });
  };

  return (
    <>
      {todos.map((todo) => (
        <div key={todo.id}>
          <label>
            <input
              type="checkbox"
              checked={todo.complete}
              onChange={() => handleComplete(todo)}
            />
            {todo.title}
          </label>
        </div>
      ))}
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Todos />);

****************************************************************


A. Initial state
The initial state is the value the state is initialized with.

For example, in the case of a counter state, the initial value could be:

// initial state
const initialState = { 
  counter: 0 
};
B. Action object
An action object is an object that describes how to update the state.

Typically, the action object would have a property type — a string describing what kind of state update the reducer must do.

For example, an action object to increase the counter can look as follows:

const action = {
  type: 'increase'
};
If the action object must carry some useful information (aka payload) to be used by the reducer, then you can add additional properties to the action object.

For example, here's an action object to add a new user to an array of users state:

const action = {
  type: 'add',
  user: { 
    name: 'John Smith',
    email: 'jsmith@mail.com'
  }
};
user is a property that holds the information about the user to add.

C. Dispatch function
The dispatch is a special function that dispatches an action object.

The dispatch function is created for your by the useReducer() hook:

const [state, dispatch] = useReducer(reducer, initialState);
Whenever you want to update the state (usually from an event handler or after completing a fetch request), you simply call the dispatch function with the appropriate action object: dispatch(actionObject).

D. Reducer function
The reducer is a pure function that accepts 2 parameters: the current state and an action object. Depending on the action object, the reducer function must update the state in an immutable manner, and return the new state.

The following reducer function supports the increase and decrease of a counter state:

function reducer(state, action) {
  let newState;
  switch (action.type) {
    case 'increase':
      newState = { counter: state.counter + 1 };
      break;
    case 'descrease':
      newState = { counter: state.counter - 1 };
      break;
    default:
      throw new Error();
  }
  return newState;
}
The reducer above doesn't modify directly the current state in the state variable, but rather creates a new state object stored in newState, then returns it.

React checks the difference between the new and the current state to determine whether the state has been updated, so do not mutate the current state directly.



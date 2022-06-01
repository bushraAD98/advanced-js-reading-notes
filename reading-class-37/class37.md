# Redux - Asynchronous Actions :

Dispatching Async Actions using Redux
Redux looked like a godsend when we started migrating old code to this new feature. It made the code look slicker, it was extremely intuitive to understand and reduced drastically the number of props floating around the application. But it was not perfect. The very nature of reducers poses a problem when you’re encompassing the fetching of information in them, and that’s something the Redux community has been tackling for a very long time

## How to handle Async Actions in Redux
Reducers, in theory, are pure functions, according to the documentation itself.

Given the same arguments, it should calculate the next state and return it. No surprises. No side effects. No API calls. No mutations. Just a calculation.

So, where should you apply async calls in Redux?
The Actions should be the immediate answer, but the basic implementation of actions is nothing more than a plain JavaScript object you use to pass information to your store. For this reason, the community came up with several middlewares that wrap all the logic into functions instead, which mimic the natural behavior of the store.


## Which Async Redux Middleware should you pick?
As with everything in programming, there isn't a one size fits all solution. So you should definitely research which middleware fits your problem the best. The first solution suggested by the documentation is Redux Thunk. This middleware allows you to create Actions as more than plain objects. These new Actions can dispatch other Actions, other Thunks and also perform async operations inside them. But recently, other middlewares have started gaining traction, like Redux-Saga and Redux-Observable have different use cases but they all share one thing, which is a very active repository and thriving community behind them.


## Why Redux Thunk?
Out of all the popular solutions to this issue, Redux Thunk is the easiest one to understand. It’s also fairly accessible in technical terms and, at this time, it’s the suggested way to approach this situation according to the Redux documentation


## How to implement Redux Thunk?
We start here:
npx react-create-app my-app --template redux

This will get you a fresh new app using React with all the Redux modules we needed to do this short tutorial. We will also be working with the WoofBot API service.

The first thing to do is to set up a dog slice, where you’ll keep all the information related to your dog API response.


![img](https://www.imaginarycloud.com/blog/content/images/2020/07/Store-slice.png)


We have our Actions:

uploadBreeds: Will be used as a dump of all the payload information regarding the dog breeds.

uploadBreedImage: Will be used to uploading certain breeds specific images, if needed.

loadingState: Will be used to updating the status of the request.

and Selectors:

selectBreeds: Returns an array of all the breeds in store.

selectBreedImage: Returns the image for a specific breed.

isLoading: Returns the status of the request


How would you normally implement this back and forth with the API and the store? I would fit it all into a useEffect hook, similar to this one:


![mg](https://www.imaginarycloud.com/blog/content/images/2020/06/useEffect-2.png)


What are we doing here?

Component is mounted
Loading State is set to Request with one dispatch of an action
Data is requested using a simple fetch
Data is received from the API and processed to the object we want
Breed information in the slice is set to what we got using another dispatch
Loading State is set back to Waiting

Alternatively, we might receive an error from the API which will stop the flow in step 4 and set the Loading State to Error.

This works, and that’s ok. But it also has several downsides. Mainly, it puts too much logic in the component. It’s not reusable, and if you want to access this information somewhere else, you’ll always need to make sure this component is loaded first


Now with Thunks:

npm install --save redux-thunk

The component logic looks like this:
![img](https://www.imaginarycloud.com/blog/content/images/2020/06/useEffectFinal-2.png)


We need to create a new fetchBreeds action that looks very similar to the logic we previously had in the component:

![img](https://www.imaginarycloud.com/blog/content/images/2020/06/thunk1-3.png)


This simple change of location in the code fixes most of the issues we had previously. We’ve abstracted code from the component and we’ve made this specific piece of logic re-usable throughout the entire code base. This information isn’t bound to mounting the component anymore, so now you can issue a new fetchBreeds action and the data will be loaded.

![m](https://www.imaginarycloud.com/blog/content/images/2020/06/thunk2-2.png)

This also enables us to chain Thunks in case need more complicated logic inside our actions. We can also access the state directly, instead of needing selectors. However, you’ll still want to use selectors to make sure that any changes to Redux don’t affect your Thunks


In the end, what to pick to handle async operations in Redux?
Depends on the situation. In the same way you can't use a spoon for everything, the solution has to be chosen based on the problem and not on the other way around.
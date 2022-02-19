# My Observations :

1-Event Loop :
JavaScript is a single threaded programmong langugage which means it has a single call stack (it can do one thing at a time),
what is a call stack? it's a datastructure that records where we are at the program, (LIFO) last in first out that how it works , now when we are using a setTimeout or promise function these call back function means that I'm going to delay their execution so the stack removes them to the API which push them up to the callback queue that is workin in (FIFO) first in first out ,
here it comes the rule of the event loop that always watch the stack and see if its empty it pushes the first thing in the callback queue.


***************************

2-Callack Function :
basically functions are objects and since we pass objects to the functions as params we can pass function to be called inside another function ,
we use callback functions in many cases for example : in order to delay a function untill a specific tas is completed , to reuse a funcion more than one time , in event handleing.
also we can use it as an anonymous function or an arrow function which is basically define and declare a function inside another one.


*****************************

3-Promises:
the promises are the best choice to handle asynchronous operations , it can lead to more readable code and better error handling ,
a promise has 4 states : fullfilled , rejected , pending , setteld .
a promise has two consumers 

a. Then() : 
 is invoked when a promise is either resolved or rejected. It may also be defined as a career which takes data from promise and further executes it successfully.

b. Catch() :
is invoked when a promise is either rejected or some error has occurred in execution. It is used as an Error Handler whenever at any step there is a chance of getting an error.

Applications :
1- Promises are used for asynchronous handling of events.
2- Promises are used to handle asynchronous http requests.

**************************

4- Async/Await :
JavaScript normaly execute the code line by line but when we use the async/await functions the order of executing the code changes 
async/Await is the extension of promises
Async:
you will warp your code with a function start with the keyword async , async make it easier to deal with promises in a way that make the promise looks like a synchronous code but actually its not

Await:
whan using it its like telling the compiler to wait and execute other lines of code the get back to this spesific code.

****************************

5- Test-Driven Development :

in short words testing term here means that we expecting our code to do some specific features and we will test it to see if the code meet these features or not 
in the developer case each developer can test its own code by a test we call unit testing , and we will use specific libraries to deal with the unit testing.

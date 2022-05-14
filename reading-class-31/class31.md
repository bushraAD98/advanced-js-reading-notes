
# Context :

What is Context API?
The React Context API is a way for a React app to effectively produce global variables that can be passed around. This is the alternative to "prop drilling" or moving props from grandparent to child to parent, and so on. Context is also touted as an easier, lighter approach to state management using Redux

Context API is a (kind of) new feature added in version 16.3 of React that allows one to share state across the entire app (or part of it) lightly and with ease.


## When to Use Context
Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language. 


## How to use Context API?

You might think to yourself: "Well, I'm convinced. How do I implement Context API in my app?" First, make sure you need it. Sometimes people use shared state across nested components instead of just passing it as props. And if you do need it you should follow these very few steps:

Create a folder under your app root named contexts (not required. just a convention)
Create a file named <your context name>Context.js, e.g. userContext.js
import and create a context like so:
import React, { createContext } from "react";
const UserContext = createContext();
Create a component that will wrap the provider named Provider e.g. UserProvider
Example using React Hooks:
const UserProvider = ({ children }) => {
  const [name, setName] = useState("John Doe");
  const [age, setAge] = useState(1);
  const happyBirthday = () => setAge(age + 1);
  return (
    <UserContext.Provider value={{ name, age, happyBirthday }}>
      {children}
    </UserContext.Provider>
  );
};
Create a higher order component to consume the context named: with e.g. withUser
Example using React Hooks:
const withUser = (Child) => (props) => (
  <UserContext.Consumer>
    {(context) => <Child {...props} {...context} />}
    {/* Another option is:  {context => <Child {...props} context={context}/>}*/}
  </UserContext.Consumer>
);
The difference between the two options above is if you want the context to be a single nested property by this name, to explode it to its properties (which in my opinion is more convenient).

Finally export them
export { UserProvider, withUser };
And use them however you like
For example:
ReactDOM.render(
  <UserProvider>
    <App />
  </UserProvider>,
  document.getElementById("root")
);
export default withUser(LoginForm);


## Redux vs. the React Context API 

Does React Context replace Redux? The short answer is no, it doesn’t. As we’ve seen, Context and Redux are two different tools, and comparison often arises from misconceptions about what each tool is designed for.

Although Context can be orchestrated to act as a state management tool, it wasn’t designed for that purpose, so you’d have to do put in extra effort to make it work. There are already a lot of state management tools that work well and will ease your troubles.

In my experience with Redux, it can be relatively complex to achieve something that is easier to solve today with Context. Keep in mind, prop drilling and global state management is where Redux and Context’s paths cross. Redux has more functionality in this are.

Ultimately, Redux and Context should be considered complementary tools that work together instead of alternatives. My recommendation is to use Redux for complex global state management and Context for prop drilling.
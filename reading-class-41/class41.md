# What Is React Native?

React Native is a JavaScript framework for writing real, natively rendering mobile applications for iOS and Android. It’s based on React, Facebook’s JavaScript library for building user interfaces, but instead of targeting the browser, it targets mobile platforms. In other words: web developers can now write mobile applications that look and feel truly “native,” all from the comfort of a JavaScript library that we already know and love. Plus, because most of the code you write can be shared between platforms, React Native makes it easy to simultaneously develop for both Android and iOS.

Similar to React for the Web, React Native applications are written using a mixture of JavaScript and XML-esque markup, known as JSX. Then, under the hood, the React Native “bridge” invokes the native rendering APIs in Objective-C (for iOS) or Java (for Android). Thus, your application will render using real mobile UI components, not webviews, and will look and feel like any other mobile application. React Native also exposes JavaScript interfaces for platform APIs, so your React Native apps can access platform features like the phone camera, or the user’s location.

React Native currently supports both iOS and Android, and has the potential to expand to future platforms as well. In this book, we’ll cover both iOS and Android. The vast majority of the code we write will be cross-platform. And yes: you can really use React Native to build production-ready mobile applications! Some anecdota: Facebook, Palantir, and TaskRabbit are already using it in production for user-facing applications.

## Advantages of React Native
The fact that React Native actually renders using its host platform’s standard rendering APIs enables it to stand out from most existing methods of cross-platform application development, like Cordova or Ionic. Existing methods of writing mobile applications using combinations of JavaScript, HTML, and CSS typically render using webviews. While this approach can work, it also comes with drawbacks, especially around performance. Additionally, they do not usually have access to the host platform’s set of native UI elements. When these frameworks do try to mimic native UI elements, the results usually “feel” just a little off; reverse-engineering all the fine details of things like animations takes an enormous amount of effort, and they can quickly become out of date.

In contrast, React Native actually translates your markup to real, native UI elements, leveraging existing means of rendering views on whatever platform you are working with. Additionally, React works separately from the main UI thread, so your application can maintain high performance without sacrificing capability. The update cycle in React Native is the same as in React: when props or state change, React Native re-renders the views. The major difference between React Native and React in the browser is that React Native does this by leveraging the UI libraries of its host platform, rather than using HTML and CSS markup.

For developers accustomed to working on the Web with React, this means you can write mobile apps with the performance and look and feel of a native application, while using familiar tools. React Native also represents an improvement over normal mobile development in two other areas: the developer experience and cross-platform development potential.

## Developer Experience

If you’ve ever developed for mobile before, you might be surprised by how easy React Native is to work with. The React Native team has baked strong developer tools and meaningful error messages into the framework, so working with robust tools is a natural part of your development experience.

For instance, because React Native is “just” JavaScript, you don’t need to rebuild your application in order to see your changes reflected; instead, you can hit Command+R to refresh your application just as you would any other web page. All of those minutes spent waiting for your application to build can really add up, and in contrast React Native’s quick iteration cycle feels like a godsend.

Additionally, React Native lets you take advantage of intelligent debugging tools and error reporting. If you are comfortable with Chrome or Safari’s developer tools (Figure 1-1), you will be happy to know that you can use them for mobile development, as well. Likewise, you can use whatever text editor you prefer for JavaScript editing: React Native does not force you to work in Xcode to develop for iOS, or Android Studio for Android development.

![img](https://www.oreilly.com/library/view/learning-react-native/9781491929049/assets/lnrn_0101.png)


Besides the day-to-day improvements to your development experience, React Native also has the potential to positively impact your product release cycle. For instance, Apple permits JavaScript-based changes to an app’s behavior to be loaded over the air with no additional review cycle necessary.

All of these small perks add up to saving you and your fellow developers time and energy, allowing you to focus on the more interesting parts of your work and be more productive overall.

## Code Reuse and Knowledge Sharing
Working with React Native can dramatically shrink the resources required to build mobile applications. Any developer who knows how to write React code can now target the Web, iOS, and Android, all with the same skillset. By removing the need to “silo” developers based on their target platform, React Native lets your team iterate more quickly, and share knowledge and resources more effectively.

Besides shared knowledge, much of your code can be shared, too. Not all the code you write will be cross-platform, and depending on what functionality you need on a specific platform, you may occasionally need to dip into Objective-C or Java. (Happily, this isn’t too bad, and we’ll cover how so-called native modules work in Chapter 7.) But reusing code across platforms is surprisingly easy with React Native. For example, the Facebook Ads Manager application for Android shares 87% of its codebase with the iOS version, as noted in the React Europe 2015 keynote. The final application we’ll look at in this book, a flashcard app, has total code reuse between Android and iOS. It’s hard to beat that!

## Risks and Drawbacks
As with anything, using React Native is not without its downsides, and whether or not React Native is a good fit for your team really depends on your individual situation.

The largest risk is probably React Native’s maturity, as the project is still relatively young. iOS support was released in March 2015, and Android support was released in September 2015. The documentation certainly has room for improvement, and continues to evolve. Some features on iOS and Android still aren’t supported, and the community is still discovering best practices. The good news is that in the vast majority of cases, you can implement support for missing APIs yourself, which we’ll cover in Chapter 7.

Because React Native introduces another layer to your project, it can also make debugging hairier, especially at the intersection of React and the host platform. We’ll cover debugging for React Native in more depth in Chapter 8, and try to address some of the most common issues.

React Native is still young, and the usual caveats that go along with working with new technologies apply here. Still, on the whole, I think you’ll see that the benefits outweigh the risks.

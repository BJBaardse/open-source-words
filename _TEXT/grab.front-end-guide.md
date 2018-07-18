grab front end guide credits illustration by yangheng this guide has been cross posted on free code camp grab is southeast asia sea s leading transportation platform and our mission is to drive sea forward leveraging on the latest technology and the talented people we have in the company as of may 2017 we handle 2 3 million rides daily and we are growing and hiring at a rapid scale to keep up with grabs phenomenal growth our web team and web platforms have to grow as well fortunately or unfortunately at grab the web team has been keeping up with the latest best practices and has incorporated the modern javascript ecosystem in our web apps the result of this is that our new hires or back end engineers who are not necessarily well acquainted with the modern javascript ecosystem may feel overwhelmed by the barrage of new things that they have to learn just to complete their feature or bug fix in a web app front end development has never been so complex and exciting as it is today new tools libraries frameworks and plugins emerge every other day and there is so much to learn it is imperative that newcomers to the web team are guided to embrace this evolution of the front end learn to navigate the ecosystem with ease and get productive in shipping code to our users as fast as possible we have come up with a study guide to introduce why we do what we do and how we handle front end at scale this study guide is inspired by a study plan to cure javascript fatigue and is mildly opinionated in the sense that we recommend certain libraries frameworks to learn for each aspect of front end development based on what is currently deemed most suitable at grab we explain why a certain library framework tool is chosen and provide links to learning resources to enable the reader to pick it up on their own alternative choices that may be better for other use cases are provided as well for reference and further self exploration if you are familiar with front end development and have been consistently keeping up with the latest developments this guide will probably not be that useful to you it is targeted at newcomers to front end if your company is exploring a modern javascript stack as well you may find this study plan useful to your company too feel free to adapt it to your needs we will update this study plan periodically according to our latest work and choices grab web team pre requisites good understanding of core programming concepts comfortable with basic command line actions and familiarity with source code version control systems such as git experience in web development have built server side rendered web apps using frameworks like ruby on rails django express etc understanding of how the web works familiarity with web protocols and conventions like http and restful apis table of contents single page apps spas new age javascript user interface state management coding with style maintainability testing linting javascript linting css formatting code types build system package management continuous integration hosting deployment certain topics can be skipped if you have prior experience in them single page apps spas web developers these days refer to the products they build as web apps rather than websites while there is no strict difference between the two terms web apps tend to be highly interactive and dynamic allowing the user to perform actions and receive a response for their action traditionally the browser receives html from the server and renders it when the user navigates to another url a full page refresh is required and the server sends fresh new html for the new page this is called server side rendering however in modern spas client side rendering is used instead the browser loads the initial page from the server along with the scripts frameworks libraries app code and stylesheets required for the whole app when the user navigates to other pages a page refresh is not triggered the url of the page is updated via the html5 history api new data required for the new page usually in json format is retrieved by the browser via ajax requests to the server the spa then dynamically updates the page with the data via javascript which it has already downloaded in the initial page load this model is similar to how native mobile apps work the benefits the app feels more responsive and users do not see the flash between page navigations due to full page refreshes fewer http requests are made to the server as the same assets do not have to be downloaded again for each page load clear separation of the concerns between the client and the server you can easily build new clients for different platforms e g mobile chatbots smart watches without having to modify the server code you can also modify the technology stack on the client and server independently as long as the api contract is not broken the downsides heavier initial page load due to loading of framework app code and assets required for multiple pages 1 theres an additional step to be done on your server which is to configure it to route all requests to a single entry point and allow client side routing to take over from there spas are reliant on javascript to render content but not all search engines execute javascript during crawling and they may see empty content on your page this inadvertently hurts the search engine optimization seo of your app 2 however most of the time when you are building apps seo is not the most important factor as not all the content needs to be indexable by search engines to overcome this you can either server side render your app or use services such as prerender to render your javascript in a browser save the static html and return that to the crawlers while traditional server side rendered apps are still a viable option a clear client server separation scales better for larger engineering teams as the client and server code can be developed and released independently this is especially so at grab when we have multiple client apps hitting the same api server as web developers are now building apps rather than pages organization of client side javascript has become increasingly important in server side rendered pages it is common to use snippets of jquery to add user interactivity to each page however when building large apps just jquery is insufficient after all jquery is primarily a library for dom manipulation and its not a framework it does not define a clear structure and organization for your app javascript frameworks have been created to provide higher level abstractions over the dom allowing you to keep state in memory out of the dom using frameworks also brings the benefits of reusing recommended concepts and best practices for building apps a new engineer on the team who is unfamiliar with the code base but has experience with a framework will find it easier to understand the code because it is organized in a structure that they are familiar with popular frameworks have a lot of tutorials and guides and tapping on the knowledge and experience from colleagues and the community will help new engineers get up to speed study links single page app advantages and disadvantages the r evolution of web development heres why client side rendering won new age javascript before you dive into the various aspects of building a javascript web app it is important to get familiar with the language of the web javascript or ecmascript javascript is an incredibly versatile language which you can also use to build web servers native mobile apps and desktop apps prior to 2015 the last major update was ecmascript 5 1 in 2011 however in the recent years javascript has suddenly seen a huge burst of improvements within a short span of time in 2015 ecmascript 2015 previously called ecmascript 6 was released and a ton of syntactic constructs were introduced to make writing code less unwieldy if you are curious about it auth0 has written a nice article on the history of javascript till this day not all browsers have fully implemented the es2015 specification tools such as babel enable developers to write es2015 in their apps and babel transpiles them down to es5 to be compatible for browsers being familiar with both es5 and es2015 is crucial es2015 is still relatively new and a lot of open source code and node js apps are still written in es5 if you are doing debugging in your browser console you might not be able to use es2015 syntax on the other hand documentation and example code for many modern libraries that we will introduce later below are still written in es2015 at grab we use babel preset env to enjoy the productivity boost from the syntactic improvements the future of javascript provides and we have been loving it so far babel preset env intelligently determines which babel plugins are necessary which new language features are not supported and have to be transpiled as browsers increase native support for more es language features if you prefer using language features that are already stable you may find that babel preset stage 3 which is a complete specification that will most likely be implemented in browsers will be more suitable spend a day or two revising es5 and exploring es2015 the more heavily used features in es2015 include arrows and lexical this classes template strings destructuring default rest spread operators and importing and exporting modules estimated duration 3 4 days you can learn lookup the syntax as you learn the other libraries and try building your own app study links learn es5 on codecademy learn es6 on codecademy learn es2015 on babel es6 katas you dont know js advanced content optional for beginners answers to front end job interview questions — javascript user interface react if any javascript project has taken the front end ecosystem by storm in recent years that would be react react is a library built and open sourced by the smart people at facebook in react developers write components for their web interface and compose them together react brings about many radical ideas and encourages developers to rethink best practices for many years web developers were taught that it was a good practice to write html javascript and css separately react does the exact opposite and encourages that you write your html and css in your javascript instead this sounds like a crazy idea at first but after trying it out it actually isnt as weird as it sounds initially reason being the front end development scene is shifting towards a paradigm of component based development the features of react declarative you describe what you want to see in your view and not how to achieve it in the jquery days developers would have to come up with a series of steps to manipulate the dom to get from one app state to the next in react you simply change the state within the component and the view will update itself according to the state it is also easy to determine how the component will look like just by looking at the markup in the render method functional the view is a pure function of props and state in most cases a react component is defined by props external parameters and state internal data for the same props and state the same view is produced pure functions are easy to test and the same goes for functional components testing in react is made easy because a components interfaces are well defined and you can test the component by supplying different props and state to it and comparing the rendered output maintainable writing your view in a component based fashion encourages reusability we find that defining a components proptypes make react code self documenting as the reader can know clearly what is needed to use that component lastly your view and logic is self contained within the component and should not be affected nor affect other components that makes it easy to shift components around during large scale refactoring as long as the same props are supplied to the component high performance you might have heard that react uses a virtual dom not to be confused with shadow dom and it re renders everything when there is a change in state why is there a need for a virtual dom while modern javascript engines are fast reading from and writing to the dom is slow react keeps a lightweight virtual representation of the dom in memory re rendering everything is a misleading term in react it actually refers to re rendering the in memory representation of the dom not the actual dom itself when theres a change in the underlying data of the component a new virtual representation is created and compared against the previous representation the difference minimal set of changes required is then patched to the real browser dom ease of learning learning react is pretty simple the react api surface is relatively small compared to this there are only a few apis to learn and they do not change often the react community is one of the largest and along with that comes a vibrant ecosystem of tools open sourced ui components and a ton of great resources online to get you started on learning react developer experience there are a number of tools that improves the development experience with react react developer tools is a browser extension that allows you to inspect your component view and manipulate its props and state hot reloading with webpack allows you to view changes to your code in your browser without you having to refresh the browser front end development involves a lot of tweaking code saving and then refreshing the browser hot reloading helps you by eliminating the last step when there are library updates facebook provides codemod scripts to help you migrate your code to the new apis this makes the upgrading process relatively pain free kudos to the facebook team for their dedication in making the development experience with react great over the years new view libraries that are even more performant than react have emerged react may not be the fastest library out there but in terms of the ecosystem overall usage experience and benefits it is still one of the greatest facebook is also channeling efforts into making react even faster with a rewrite of the underlying reconciliation algorithm the concepts that react introduced has taught us how to write better code more maintainable web apps and made us better engineers we like that we recommend going through the tutorial on building a tic tac toe game on the react homepage to get a feel of what react is and what it does for more in depth learning check out the egghead course build your first production quality react app it covers some advanced concepts and real world usages that are not covered by the react documentation create react app by facebook is a tool to scaffold a react project with minimal configuration and is highly recommended to use for starting new react projects react is a library not a framework and does not deal with the layers below the view the app state more on that later estimated duration 3 4 days try building simple projects like a to do list hacker news clone with pure react you will slowly gain an appreciation for it and perhaps face some problems along the way that isnt solved by react which brings us to the next topic study links react official tutorial egghead course build your first production quality react app simple react development in 2017 presentational and container components alternatives angular ember vue cycle state management flux redux as your app grows bigger you may find that the app structure becomes a little messy components throughout the app may have to share and display common data but there is no elegant way to handle that in react after all react is just the view layer it does not dictate how you structure the other layers of your app such as the model and the controller in traditional mvc paradigms in an effort to solve this facebook invented flux an app architecture that complements reacts composable view components by utilizing a unidirectional data flow read more about how flux works here in summary the flux pattern has the following characteristics unidirectional data flow makes the app more predictable as updates can be tracked easily separation of concerns each part in the flux architecture has clear responsibilities and are highly decoupled works well with declarative programming the store can send updates to the view without specifying how to transition views between states as flux is not a framework per se developers have tried to come up with many implementations of the flux pattern eventually a clear winner emerged which was redux redux combines the ideas from flux command pattern and elm architecture and is the de facto state management library developers use with react these days its core concepts are app state is described by a single plain old javascript object pojo dispatch an action also a pojo to modify the state reducer is a pure function that takes in current state and action to produce a new state the concepts sound simple but they are really powerful as they enable apps to have their state rendered on the server booted up on the client trace log and backtrack changes in the whole app implement undo redo functionality easily the creator of redux dan abramov has taken great care in writing up detailed documentation for redux along with creating comprehensive video tutorials for learning basic and advanced redux they are extremely helpful resources for learning redux combining view and state while redux does not necessarily have to be used with react it is highly recommended as they play very well with each other react and redux have a lot of ideas and traits in common functional composition paradigm react composes views pure functions while redux composes pure reducers also pure functions output is predictable given the same set of input easy to reason about you may have heard this term many times but what does it actually mean we interpret it as having control and understanding over our code our code behaves in ways we expect it to and when there are problems we can find them easily through our experience react and redux makes debugging simpler as the data flow is unidirectional tracing the flow of data server responses user input events is easier and it is straightforward to determine which layer the problem occurs in layered structure each layer in the app flux architecture is a pure function and has clear responsibilities it is relatively easy to write tests for pure functions you have to centralize changes to your app within the reducer and the only way to trigger a change is to dispatch an action development experience a lot of effort has gone into creating tools to help in debugging and inspecting the app while development such as redux devtools your app will likely have to deal with async calls like making remote api requests redux thunk and redux saga were created to solve those problems they may take some time to understand as they require understanding of functional programming and generators our advice is to deal with it only when you need it react redux is an official react binding for redux and is very simple to learn estimated duration 4 days the egghead courses can be a little time consuming but they are worth spending time on after learning redux you can try incorporating it into the react projects you have built does redux solve some of the state management issues you were struggling with in pure react study links flux homepage redux homepage egghead course getting started with redux egghead course build react apps with idiomatic redux react redux links you might not need redux alternatives mobx coding with style css modules css cascading style sheets are rules to describe how your html elements look writing good css is hard it usually takes many years of experience and frustration of shooting yourself in the foot before one is able to write maintainable and scalable css css having a global namespace is fundamentally designed for web documents and not really for web apps that favor a components architecture hence experienced front end developers have designed methodologies to guide people on how to write organized css for complex projects such as using smacss bem suit css etc however the encapsulation of styles that these methodologies bring about are artificially enforced by conventions and guidelines they break the moment developers do not follow them as you might have realized by now the front end ecosystem is saturated with tools and unsurprisingly tools have been invented to partially solve some of the problems with writing css at scale at scale means that many developers are working on the same large project and touching the same stylesheets there is no community agreed approach on writing css in js at the moment and we are hoping that one day a winner would emerge just like redux did among all the flux implementations for now we are banking on css modules css modules is an improvement over existing css that aims to fix the problem of global namespace in css it enables you to write styles that are local by default and encapsulated to your component this feature is achieved via tooling with css modules large teams can write modular and reusable css without fear of conflict or overriding other parts of the app however at the end of the day css modules are still being compiled into normal globally namespaced css that browsers recognize and it is still important to learn and understand how raw css works if you are a total beginner to css codecademys html css course will be a good introduction to you next read up on the sass preprocessor an extension of the css language which adds syntactic improvements and encourages style reusability study the css methodologies mentioned above and lastly css modules estimated duration 3 4 days try styling up your app using the smacss bem approach and or css modules study links learn html css course on codecademy intro to html css on khan academy smacss bem suit css css modules specification sass homepage answers to front end job interview questions — html answers to front end job interview questions — css alternatives jss styled components maintainability code is read more frequently than it is written this is especially true at grab where the team size is large and we have multiple engineers working across multiple projects we highly value readability maintainability and stability of the code and there are a few ways to achieve that extensive testing consistent coding style and typechecking also when you are in a team sharing same practices becomes really important check out these javascript project guidelines for instance testing jest enzyme jest is a testing library by facebook that aims to make the process of testing pain free as with facebook projects it provides a great development experience out of the box tests can be run in parallel resulting in shorter duration during watch mode by default only the tests for the changed files are run one particular feature we like is snapshot testing jest can save the generated output of your react component and redux state and save it as serialized files so you wouldnt have to manually come up with the expected output yourself jest also comes with built in mocking assertion and test coverage one library to rule them all react comes with some testing utilities but enzyme by airbnb makes it easier to generate assert manipulate and traverse your react components output with a jquery like api it is recommended that enzyme be used to test react components jest and enzyme makes writing front end tests fun and easy when writing tests becomes enjoyable developers write more tests it also helps that react components and redux actions reducers are relatively easy to test because of clearly defined responsibilities and interfaces for react components we can test that given some props the desired dom is rendered and that callbacks are fired upon certain simulated user interactions for redux reducers we can test that given a prior state and an action a resulting state is produced the documentation for jest and enzyme are pretty concise and it should be sufficient to learn them by reading it estimated duration 2 3 days try writing jest enzyme tests for your react redux app study links jest homepage testing react applications with jest enzyme homepage enzyme javascript testing utilities for react alternatives ava karma linting javascript eslint a linter is a tool to statically analyze code and finds problems with them potentially preventing bugs runtime errors and at the same time enforcing a coding style time is saved during pull request reviews when reviewers do not have to leave nitpicky comments on coding style eslint is a tool for linting javascript code that is highly extensible and customizable teams can write their own lint rules to enforce their custom styles at grab we use airbnbs eslint config airbnb preset that has already been configured with the common good coding style in the airbnb javascript style guide for the most part using eslint is as simple as tweaking a configuration file in your project folder theres nothing much to learn about eslint if youre not writing new rules for it just be aware of the errors when they surface and google it to find out the recommended style estimated duration 1 2 day nothing much to learn here add eslint to your project and fix the linting errors study links eslint homepage airbnb javascript style guide alternatives standard jshint xo linting css stylelint as mentioned earlier good css is notoriously hard to write usage of static analysis tools on css can help to maintain our css code quality and coding style for linting css we use stylelint like eslint stylelint is designed in a very modular fashion allowing developers to turn rules on off and write custom plugins for it besides css stylelint is able to parse scss and has experimental support for less which lowers the barrier for most existing code bases to adopt it once you have learnt eslint learning stylelint would be effortless considering their similarities stylelint is currently being used by big companies like facebook github and wordpress one downside of stylelint is that the autofix feature is not fully mature yet and is only able to fix for a limited number of rules however this issue should improve with time estimated duration 1 2 day nothing much to learn here add stylelint to your project and fix the linting errors study links stylelint homepage lint your css with stylelint alternatives sass lint css lint formatting code prettier another tool for enforcing consistent coding style for javascript and css is prettier in most cases it is recommended to setup prettier on top of eslint and stylelint and integrate it into the workflow this allows the code to be formatted into consistent style automatically via commit hooks so that developers do not need to spend time formatting the coding style manually note that prettier only enforces coding style but does not check for logic errors in the code hence it is not a replacement for linters estimated duration 1 2 day nothing much to learn here add prettier to your project and add hooks to enforce the coding style study links prettier homepage prettier github repo comparison between tools that allow you to use eslint and prettier together types flow static typing brings about many benefits when writing apps they can catch common bugs and errors in your code early types also serve as a form of documentation for your code and improves the readability of your code as a code base grows larger we see the importance of types as they gives us greater confidence when we do refactoring it is also easier to onboard new members of the team to the project when it is clear what kind of values each object holds and what each function expects adding types to your code comes with the trade off of increased verbosity and a learning curve of the syntax but this learning cost is paid upfront and amortized over time in complex projects where the maintainability of the code matters and the people working on it change over time adding types to the code brings about more benefits than disadvantages recently i had to fix a bug in a code base that i havent touched in months it was thanks to types that i could easily refresh myself on what the code was doing and gave me confidence in the fix i made the two biggest contenders in adding static types to javascript are flow by facebook and typescript by microsoft as of date there is no clear winner in the battle for now we have made the choice of using flow we find that flow has a lower learning curve as compared to typescript and it requires relatively less effort to migrate an existing code base to flow being built by facebook flow has better integration with the react ecosystem out of the box james kyle one of the authors of flow has written on a comparison between adopting flow and typescript anyway it is not extremely difficult to move from flow to typescript as the syntax and semantics are quite similar and we will re evaluate the situation in time to come after all using one is better than not using any at all flow recently revamped their homepage and its pretty neat now estimated duration 1 day flow is pretty simple to learn as the type annotations feel like a natural extension of the javascript language add flow annotations to your project and embrace the power of type systems study links flow homepage typescript vs flow alternatives typescript build system webpack this part will be kept short as setting up webpack can be a tedious process and might be a turn off to developers who are already overwhelmed by the barrage of new things they have to learn for front end development in a nutshell webpack is a module bundler that compiles a front end project and its dependencies into a final bundle to be served to users usually projects will already have the webpack configuration set up and developers rarely have to change it having an understanding of webpack is still a good to have in the long run it is due to webpack that features like hot reloading and css modules are made possible we have found the webpack walkthrough by survivejs to be the best resource on learning webpack it is a good complement to the official documentation and we recommend following the walkthrough first and referring to the documentation later when the need for further customization arises estimated duration 2 days optional study links webpack homepage survivejs webpack from apprentice to master alternatives rollup browserify package management yarn if you take a peek into your node modules directory you will be appalled by the number of directories that are contained in it each babel plugin lodash function is a package on its own when you have multiple projects these packages are duplicated across each project and they are largely similar each time you run npm install in a new project these packages are downloaded over and over again even though they already exist in some other project in your computer there was also the problem of non determinism in the installed packages via npm install some of our ci builds fail because at the point of time when the ci server installs the dependencies it pulled in minor updates to some packages that contained breaking changes this would not have happened if library authors respected semver and engineers did not assume that api contracts would be respected all the time yarn solves these problems the issue of non determinism of installed packages is handled via a yarn lock file which ensures that every install results in the exact same file structure in node modules across all machines yarn utilizes a global cache directory within your machine and packages that have been downloaded before do not have to be downloaded again this also enables offline installation of dependencies the most common yarn commands can be found here most other yarn commands are similar to the npm equivalents and it is fine to use the npm versions instead one of our favorite commands is yarn upgrade interactive which makes updating dependencies a breeze especially when the modern javascript project requires so many dependencies these days do check it out npm 5 0 0 was released in may 2017 and it seems to address many of the issues that yarn aims to solve do keep an eye on it estimated duration 2 hours study links yarn homepage yarn a new package manager for javascript alternatives good old npm continuous integration we use travis ci for our continuous integration ci pipeline travis is a highly popular ci on github and its build matrix feature is useful for repositories which contain multiple projects like grabs we configured travis to do the following run linting for the project run unit tests for the project if the tests pass test coverage generated by jest is uploaded to codecov generate a production bundle with webpack into a build directory tar the build directory as hash tar and upload it to an s3 bucket which stores all our tar builds post a notification to slack to inform about the travis build result study links travis homepage codecov homepage alternatives jenkins circleci hosting amazon s3 traditionally web servers that receive a request for a webpage will render the contents on the server and return a html page with dynamic content meant for the requester this is known as server side rendering as mentioned earlier in the section on single page apps modern web applications do not involve server side rendering and it is sufficient to use a web server that serves static asset files nginx and apache are possible options and not much configuration is required to get things up and runnning the caveat is that the web server will have to be configured to route all requests to a single entry point and allow client side routing to take over the flow for front end routing goes like this web server receives a http request for a particular route for example user john regardless of which route the server receives serve up index html from the static assets directory the index html should contain scripts that load up a javascript framework library that handles client side routing the client side routing library reads the current route and communicates to the mvc or equivalent where relevant framework about the current route the mvc javascript framework renders the desired view based on the route possibly after fetching data from an api if required example load up userscontroller fetch user data for the username john as json combine the data with the view and render it on the page a good practice for serving static content is to use caching and putting them on a cdn we use amazon simple storage service s3 because it can both host and act as a cdn for our static website content we find that it is an affordable and reliable solution that meets our needs s3 provides the option to use this bucket to host a website which essentially directs the requests for all routes to the root of the bucket which means we do not need our own web servers with special routing configurations an example of a web app that we host on s3 is hub other than hosting the website we also use s3 to host the build tar files generated from each successful travis build study links amazon s3 homepage hosting a static website on amazon s3 alternatives google cloud platform now deployment the last step in shipping the product to our users is deployment we use ansible tower which is a powerful automation software that enables us to deploy our builds easily as mentioned earlier all our commits upon successful build are being uploaded to a central s3 bucket for builds we follow semver for our releases and have commands to automatically generate release notes for the latest release when it is time to release we run a command to tag the latest commit and push to our code hosting environment travis will run the ci steps on that tagged commit and upload a tar file such as 1 0 1 tar with the version to our s3 bucket for builds on tower we simply have to specify the name of the tar we want to deploy to our hosting bucket and tower does the following download the desired tar file from our builds s3 bucket extracts the contents and swap in the configuration file for specified environment upload the contents to the hosting bucket post a notification to slack to inform about the successful deployment this whole process is done under 30 seconds and using tower has made deployments and rollbacks easy if we realize that a faulty deployment has occurred we can simply find the previous stable tag and deploy it study links ansible tower homepage the journey has just begun congratulations on making it this far front end development today is hard but it is also more interesting than before what we have covered so far will help any new engineer to grabs web team to get up to speed with our technologies pretty quickly there are many more things to be learnt but building up a solid foundation in the essentials will aid in learning the rest of the technologies this helpful front end web developer roadmap shows the alternative technologies available for each aspect we made our technical decisions based on what was important to a rapidly growing grab engineering team maintainability and stability of the code base these decisions may or may not apply to smaller teams and projects do evaluate what works best for you and your company as the front end ecosystem grows we are actively exploring experimenting and evaluating how new technologies can make us a more efficient team and improve our productivity we hope that this post has given you insights into the front end technologies we use at grab if what we are doing interests you we are hiring many thanks to joel low li kai and tan wei seng who reviewed drafts of this article more reading general state of the javascript landscape a map for newcomers the hitchhikers guide to the modern front end development workflow how it feels to learn javascript in 2016 roadmap to becoming a web developer in 2017 modern javascript for ancient web developers other study plans a study plan to cure javascript fatigue js stack from scratch a beginners javascript study plan footnotes 1 this can be solved via webpack code splitting ↩ 2 universal js to the rescue ↩
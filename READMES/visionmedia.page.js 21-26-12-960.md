tiny express inspired client side router js page index page user user show page user user edit edit page user user album album page user user album sort sort page notfound page installation there are multiple ways to install page js with package managers bash npm install page for browserify component install visionmedia page js bower install visionmedia page js or use with a cdn we support cdnjs unpkg example usage is html script src https unpkg com page page js script script page about function do stuff script running examples to run examples do the following to install dev dependencies and run the example server git clone git github com visionmedia page js cd page js npm install node examples open http localhost 4000 currently we have examples for basic minimal application showing basic routing notfound similar to basic with single page 404 support album showing pagination and external links profile simple user profiles query string shows how you can integrate plugins using the router state illustrates how the history state may be used to cache data server illustrates how to use the dispatch option to server initial content chrome google chrome style administration interface transitions shows off a simple technique for adding transitions between pages partials using hogan js to render mustache partials client side note keep in mind these examples do not use jquery or similar so portions of the examples may be relatively verbose though theyre not directly related to page js in any way api page path callback callback defines a route mapping path to the given callback s each callback is invoked with two arguments context and next much like express invoking next will call the next registered callback with the given path js page user list page user id user load user show page user id edit user load user edit page notfound under certain conditions links will be disregarded and will not be dispatched such as links that are not of the same origin links with the download attribute links with the target attribute links with the rel external attribute page callback this is equivalent to page callback for generic middleware page path navigate to the given path js view click function e page user 12 e preventdefault page frompath topath setup redirect from one path to another page redirect frompath topath identical to page frompath topath page redirect path calling page redirect with only a string as the first parameter redirects to another route waits for the current route to push state and after replaces it with the new one leaving the browser history clean js page default function some logic to decide which route to redirect to if admin page redirect admin else page redirect guest page default page show path identical to page path above page options register pages popstate click bindings if youre doing selective binding youll like want to pass click false to specify this yourself the following options are available click bind to click events true popstate bind to popstate true dispatch perform initial dispatch true hashbang add before urls false decodeurlcomponents remove url encoding from path components query string pathname hash true if you wish to load serve initial content from the server you likely will want to set dispatch to false page start options identical to page options above page stop unbind both the popstate and click handlers page base path get or set the base path for example if page js is operating within blog set the base path to blog page strict enable get or set the strict path matching mode to enable if enabled blog will not match blog and blog will not match blog page exit path callback callback defines an exit route mapping path to the given callback s exit routes are called when a page changes using the context from the previous change for example js page sidebar function ctx next sidebar open true next page exit sidebar function ctx next sidebar open false next page exit callback equivalent to page exit callback context routes are passed context objects these may be used to share state for example ctx user as well as the history state ctx state that the pushstate api provides context save saves the context using replacestate for example this is useful for caching html or other resources that were loaded for when a user presses back context handled if true marks the context as handled to prevent default 404 behaviour for example this is useful for the routes with interminate quantity of the callbacks context canonicalpath pathname including the base if any and query string admin login foo bar context path pathname and query string login foo bar context querystring query string void of leading such as foo bar defaults to context pathname the pathname void of query string login context state the pushstate state object context title the pushstate title routing the router uses the same string to regexp conversion that express does so things like id id and work as you might expect another aspect that is much like express is the ability to pass multiple callbacks you can use this to your advantage to flatten nested callbacks or simply to abstract components separating concerns for example suppose you have a route to edit users and a route to view users in both cases you need to load the user one way to achieve this is with several callbacks as shown here js page user user load show page user user edit load edit using the character we can alter this to match all routes prefixed with user to achieve the same result js page user load page user user show page user user edit edit likewise can be used as catch alls after all routes acting as a 404 handler before all routes in between and so on for example js page user user load show page function body text not found default 404 behaviour by default when a route is not matched page js invokes page stop to unbind itself and proceed with redirecting to the location requested this means you may use page js with a multi page application without explicitly binding to certain links working with parameters and contexts much like request and response objects are passed around in express page js has a single context object using the previous examples of load and show for a user we can assign arbitrary properties to ctx to maintain state between callbacks to build a load function that will load the user for subsequent routes youll need to access the id passed you can do this with ctx params name much like express js function load ctx next var id ctx params id then perform some kind of action against the server assigning the user to ctx user for other routes to utilize next is then invoked to pass control to the following matching route in sequence if any js function load ctx next var id ctx params id getjson user id json function user ctx user user next the show function might look something like this however you may render templates or do anything you want note that here next is not invoked because this is considered the end point and no routes will be matched until another link is clicked or page path is called js function show ctx body empty append h1 ctx user name h1 finally using them like so js page user id load show note the value of ctx params name is decoded via decodeuricomponent sliceofurl one exception though is the use of the plus sign in the url e g user john doe which is decoded to a space ctx params id john doe also an encoded plus sign 2b is decoded to a space working with state when working with the pushstate api and page js you may optionally provide state objects available when the user navigates the history for example if you had a photo application and you performed a relatively extensive search to populate a list of images normally when a user clicks back in the browser the route would be invoked and the query would be made yet again an example implementation might look as follows js function show ctx getjson photos function images displayimages images you may utilize the historys state object to cache this result or any other values you wish this makes it possible to completely omit the query when a user presses back providing a much nicer experience js function show ctx if ctx state images displayimages ctx state images else getjson photos function images ctx state images images ctx save displayimages images note ctx save must be used if the state changes after the first tick xhr settimeout etc otherwise it is optional and the state will be saved after dispatching matching paths here are some examples of whats possible with the string to regexp conversion match an explicit path js page about callback match with required parameter accessed via ctx params name js page user name callback match with several params for example user tj edit or user tj view js page user name operation callback match with one optional and one required now user tj will match the same route as user tj show etc js page user name operation callback use the wildcard char to match across segments available via ctx params n where n is the index of since you may use several for example the following will match user 12 edit user 12 albums 2 admin and so on js page user loaduser named wildcard accessed for example file javascripts jquery js would provide javascripts jquery js as ctx params file js page file file loaduser and of course regexp literals where the capture groups are available via ctx params n where n is the index of the capture group js page \ commits\ \d \ \ \d loaduser plugins an example plugin examples query string query js demonstrates how to make plugins it will provide a parsed ctx query object derived from node querystring usage by using to match any path in order to parse the query string js page parse page show page function parse ctx next ctx query qs parse location search slice 1 next function show ctx if object keys ctx query length document queryselector pre textcontent json stringify ctx query null 2 available plugins querystring provides a parsed ctx query object derived from node querystring body parser provides a req body object for routes derived from body parser express mapper provides a direct imitation of the express api so you can share controller code on the client and the server with your express application without modification please submit pull requests to add more to this list running tests in the console npm install npm test in the browser npm install npm run serve open http localhost 3000 support in ie8 if you want the router to work in older version of internet explorer that dont support pushstate you can use the html5 history api polyfill bash npm install html5 history api how to use a polyfill together with router optional if your web app is located within a nested basepath you will need to specify the basepath for the html5 history api polyfill before calling page base use history redirect prefixtype basepath translation link if required prefixtype string null substitute the string after the anchor by default basepath string null set the base path see page base by default note slash after pathname required pull requests break commits into a single objective an objective should be a chunk of code that is related but requires explanation commits should be in the form of what it is how it does it and or why its needed or what it is for trivial changes pull requests and commits should be a guide to the code server configuration in order to load and update any url managed by page js you need to configure your environment to point to your projects main file index html for example for each non existent url below you will find examples for most common server scenarios nginx if using nginx add this to the conf file related to your project inside the server part and reload your nginx server nginx location try files uri uri index html args apache if using apache create or add to the htaccess file in the root of your public folder with the code apache options followsymlinks rewriteengine on rewritecond script filename d rewritecond script filename f rewriterule index html node js express for development and or production using express you need to use express history api fallback package an example js import join from path import express from express import history from express history api fallback const app express const root join dirname public app use express static root app use history index html root const server app listen process env port 3000 export default server node js browsersync for development using browsersync you need to use history api fallback package an example js var browsersync require browser sync create var historyapifallback require connect history api fallback browsersync init files html css css js js server basedir middleware historyapifallback port 3030 integrations react for development using react you can use pagify it license the mit license copyright c 2012 tj holowaychuk tj vision media ca permission is hereby granted free of charge to any person obtaining a copy of this software and associated documentation files the software to deal in the software without restriction including without limitation the rights to use copy modify merge publish distribute sublicense and or sell copies of the software and to permit persons to whom the software is furnished to do so subject to the following conditions the above copyright notice and this permission notice shall be included in all copies or substantial portions of the software the software is provided as is without warranty of any kind express or implied including but not limited to the warranties of merchantability fitness for a particular purpose and noninfringement in no event shall the authors or copyright holders be liable for any claim damages or other liability whether in an action of contract tort or otherwise arising from out of or in connection with the software or the use or other dealings in the software
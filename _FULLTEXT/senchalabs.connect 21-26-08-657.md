connect connect is an extensible http server framework for node using plugins known as middleware js var connect require connect var http require http var app connect gzip deflate outgoing responses var compression require compression app use compression store session state in browser cookie var cookiesession require cookie session app use cookiesession keys secret1 secret2 parse urlencoded request bodies into req body var bodyparser require body parser app use bodyparser urlencoded extended false respond to all requests app use function req res res end hello from connect \n create node js http server and listen on port http createserver app listen 3000 getting started connect is a simple framework to glue together various middleware to handle requests install connect sh npm install connect create an app the main component is a connect app this will store all the middleware added and is itself a function js var app connect use middleware the core of connect is using middleware middleware are added as a stack where incoming requests will execute each middleware one by one until a middleware does not call next within it js app use function middleware1 req res next middleware 1 next app use function middleware2 req res next middleware 2 next mount middleware the use method also takes an optional path string that is matched against the beginning of the incoming request url this allows for basic routing js app use foo function foomiddleware req res next req url starts with foo next app use bar function barmiddleware req res next req url starts with bar next error middleware there are special cases of error handling middleware there are middleware where the function takes exactly 4 arguments when a middleware passes an error to next the app will proceed to look for the error middleware that was declared after that middleware and invoke it skipping any error middleware above that middleware and any non error middleware below js regular middleware app use function req res next i had an error next new error boom error middleware for errors that occurred in middleware declared before this app use function onerror err req res next an error occurred create a server from the app the last step is to actually use the connect app in a server the listen method is a convenience to start a http server and is identical to the http servers listen method in the version of node js you are running js var server app listen port the app itself is really just a function with three arguments so it can also be handed to createserver in node js js var server http createserver app middleware these middleware and libraries are officially supported by the connect express team body parser previous bodyparser json and urlencoded you may also be interested in body co body raw body compression previously compress connect timeout previously timeout cookie parser previously cookieparser cookie session previously cookiesession csurf previously csrf errorhandler previously error handler express session previously session method override previously method override morgan previously logger response time previously response time serve favicon previously favicon serve index previously directory serve static previously static vhost previously vhost most of these are exact ports of their connect 2 x equivalents the primary exception is cookie session some middleware previously included with connect are no longer supported by the connect express team are replaced by an alternative module or should be superseded by a better module use one of these alternatives instead cookieparser cookies and keygrip limit raw body multipart connect multiparty connect busboy query qs staticcache st connect static checkout http framework for many other compatible middleware api the connect api is very minimalist enough to create an app and add a chain of middleware when the connect module is required a function is returned that will construct a new app when called js require module var connect require connect create app var app connect app req res next the app itself is a function this is just an alias to app handle app handle req res out calling the function will run the middleware stack against the given node js http request req and response res objects an optional function out can be provided that will be called if the request or error was not handled by the middleware stack app listen start the app listening for requests this method will internally create a node js http server and call listen on it this is an alias to the server listen method in the version of node js running so consult the node js documentation for all the different variations the most common signature is app listen port app use fn use a function on the app where the function represents a middleware the function will be invoked for every request in the order that app use is called the function is called with three arguments js app use function req res next req is the node js http request object res is the node js http response object next is a function to call to invoke the next middleware in addition to a plan function the fn argument can also be a node js http server instance or another connect app instance app use route fn use a function on the app where the function represents a middleware the function will be invoked for every request in which the url req url property starts with the given route string in the order that app use is called the function is called with three arguments js app use foo function req res next req is the node js http request object res is the node js http response object next is a function to call to invoke the next middleware in addition to a plan function the fn argument can also be a node js http server instance or another connect app instance the route is always terminated at a path separator or a dot character this means the given routes foo and foo are the same and both will match requests with the urls foo foo foo bar and foo bar but not match a request with the url foobar the route is matched in a case insensitive manor in order to make middleware easier to write to be agnostic of the route when the fn is invoked the req url will be altered to remove the route part and the original will be available as req originalurl for example if fn is used at the route foo the request for foo bar will invoke fn with req url bar and req originalurl foo bar running tests bash npm install npm test people the connect project would not be the same without all the people involved the original author of connect is tj holowaychuk the current lead maintainer is douglas christopher wilson list of all contributors node compatibility connect 1 x node 0 2 connect 1 x node 0 4 connect 2 8 node 0 6 connect 2 8 3 node 0 8 connect 3 node 0 10 0 12 4 x 5 x 6 x 7 x 8 x io js 1 x 2 x 3 x license mit
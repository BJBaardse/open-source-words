Expressive HTTP middleware framework for node.js to make web applications and APIs more enjoyable to write. Koas middleware stack flows in a stack-like manner, allowing you to perform actions downstream then filter and manipulate the response upstream. Only methods that are common to nearly all HTTP servers are integrated directly into Koas small ~570 SLOC codebase. This includes things like content negotiation, normalization of node inconsistencies, redirection, and a few others. Koa is not bundled with any middleware. Installation Koa requires node v7.6.0 or higher for ES2015 and async function support. $ npm install koa Hello Koa ```js const Koa = require(koa); const app = new Koa(); // response app.use(ctx => { ctx.body = Hello Koa; }); app.listen(3000); ``` Getting started Kick-Off-Koa - An intro to Koa via a set of self-guided workshops. Workshop - A workshop to learn the basics of Koa, Express spiritual successor. Introduction Screencast - An introduction to installing and getting started with Koa Middleware Koa is a middleware framework that can take two different kinds of functions as middleware: async function common function Here is an example of logger middleware with each of the different functions: async functions (node v7.6+) js app.use(async (ctx, next) => { const start = Date.now(); await next(); const ms = Date.now() - start; console.log(`${ctx.method} ${ctx.url} - ${ms}ms`); }); Common function ```js // Middleware normally takes two parameters (ctx, next), ctx is the context for one request, // next is a function that is invoked to execute the downstream middleware. It returns a Promise with a then function for running code after completion. app.use((ctx, next) => { const start = Date.now(); return next().then(() => { const ms = Date.now() - start; console.log(${ctx.method} ${ctx.url} - ${ms}ms); }); }); ``` Koa v1.x Middleware Signature The middleware signature changed between v1.x and v2.x. The older signature is deprecated. Old signature middleware support will be removed in v3 Please see the Migration Guide for more information on upgrading from v1.x and using v1.x middleware with v2.x. Context, Request and Response Each middleware receives a Koa Context object that encapsulates an incoming http message and the corresponding response to that message. ctx is often used as the parameter name for the context object. js app.use(async (ctx, next) => { await next(); }); Koa provides a Request object as the request property of the Context. Koas Request object provides helpful methods for working with http requests which delegate to an IncomingMessage from the node http module. Here is an example of checking that a requesting client supports xml. js app.use(async (ctx, next) => { ctx.assert(ctx.request.accepts(xml), 406); // equivalent to: // if (!ctx.request.accepts(xml)) ctx.throw(406); await next(); }); Koa provides a Response object as the response property of the Context. Koas Response object provides helpful methods for working with http responses which delegate to a ServerResponse . Koas pattern of delegating to Nodes request and response objects rather than extending them provides a cleaner interface and reduces conflicts between different middleware and with Node itself as well as providing better support for stream handling. The IncomingMessage can still be directly accessed as the req property on the Context and ServerResponse can be directly accessed as the res property on the Context. Here is an example using Koas Response object to stream a file as the response body. js app.use(async (ctx, next) => { await next(); ctx.response.type = xml; ctx.response.body = fs.createReadStream(really_large.xml); }); The Context object also provides shortcuts for methods on its request and response. In the prior examples, ctx.type can be used instead of ctx.request.type and ctx.accepts can be used instead of ctx.request.accepts. For more information on Request, Response and Context, see the Request API Reference, Response API Reference and Context API Reference. Koa Application The object created when executing new Koa() is known as the Koa application object. The application object is Koas interface with nodes http server and handles the registration of middleware, dispatching to the middleware from http, default error handling, as well as configuration of the context, request and response objects. Learn more about the application object in the Application API Reference. Documentation Usage Guide Error Handling Koa for Express Users FAQ API documentation Babel setup If youre not using node v7.6+, we recommend setting up babel with babel-preset-env: bash $ npm install babel-register babel-preset-env --save Setup babel-register in your entry file: js require(babel-register); And have your .babelrc setup: json { "presets": [ ["env", { "targets": { "node": true } }] ] } Troubleshooting Check the Troubleshooting Guide or Debugging Koa in the general Koa guide. Running tests $ npm test Authors See AUTHORS. Community Badgeboard and list of official modules Examples Middleware list Wiki G+ Community Reddit Community Mailing list 中文文档 v1.x 中文文档 v2.x #koajs on freenode Job Board Looking for a career upgrade? Backers Support us with a monthly donation and help us continue our activities. Sponsors Become a sponsor and get your logo on our README on Github with a link to your site. License MIT
redux devtools extension installation 1 for chrome from chrome web store or build it with npm i npm run build extension and load the extensions folder build extension or run it in dev mode with npm i npm start and load the extensions folder dev 2 for firefox from mozilla add ons or build it with npm i npm run build firefox and load the extensions folder build firefox just select a file from inside the dir 3 for electron just specify redux devtools in electron devtools installer 4 for other browsers and non browser environment use remote redux devtools usage note that starting from v2 7 window devtoolsextension was renamed to window redux devtools extension window redux devtools extension compose 1 with redux 1 1 basic store for a basic redux store simply add diff const store createstore reducer preloadedstate window redux devtools extension window redux devtools extension note that preloadedstate argument is optional in redux createstore for universal isomorphic apps prefix it with typeof window undefined in case eslint is configured to not allow using the underscore dangle wrap it like so diff eslint disable no underscore dangle const store createstore reducer preloadedstate window redux devtools extension window redux devtools extension eslint enable note passing enhancer as last argument requires redux 3 1 0 for older versions apply it like here or here dont mix the old redux api with the new one you dont need to npm install redux devtools when using the extension thats a different lib 1 2 advanced store setup if you setup your store with middleware and enhancers change diff import createstore applymiddleware compose from redux const composeenhancers window redux devtools extension compose compose const store createstore reducer preloadedstate composeenhancers const store createstore reducer preloadedstate compose applymiddleware middleware note that when the extension is not installed were using redux compose here to specify extensions options use it like so js const composeenhancers typeof window object window redux devtools extension compose window redux devtools extension compose specify extensions options like name actionsblacklist actionscreators serialize compose const enhancer composeenhancers applymiddleware middleware other store enhancers if any const store createstore reducer enhancer see the post for more details 1 3 use redux devtools extension package from npm to make things easier theres an npm package to install npm install save dev redux devtools extension and to use like so js import createstore applymiddleware from redux import composewithdevtools from redux devtools extension const store createstore reducer composewithdevtools applymiddleware middleware other store enhancers if any to specify extensions options https github com zalmoxisus redux devtools extension blob master docs api arguments md windowdevtoolsextensionconfig js import createstore applymiddleware from redux import composewithdevtools from redux devtools extension const composeenhancers composewithdevtools specify name here actionsblacklist actionscreators and other options if needed const store createstore reducer preloadedstate composeenhancers applymiddleware middleware other store enhancers if any therere just few lines of code added to your bundle in case you dont include other enhancers and middlewares just use devtoolsenhancer js import createstore from redux import devtoolsenhancer from redux devtools extension const store createstore reducer preloadedstate devtoolsenhancer specify name here actionsblacklist actionscreators and other options if needed 1 4 using in production its useful to include the extension in production as well usually you can use it for development if you want to restrict it there use redux devtools extension logonlyinproduction js import createstore from redux import devtoolsenhancer from redux devtools extension logonlyinproduction const store createstore reducer preloadedstate devtoolsenhancer options like actionsanitizer statesanitizer or with middlewares and enhancers js import createstore applymiddleware from redux import composewithdevtools from redux devtools extension logonlyinproduction const composeenhancers composewithdevtools options like actionsanitizer statesanitizer const store createstore reducer preloadedstate composeenhancers applymiddleware middleware other store enhancers if any youll have to add process env node env json stringify production in your webpack config for the production bundle to envify if you use create react app it already does it for you if youre already checking process env node env when creating the store include redux devtools extension logonly for production enviroment if you dont want to allow the extension in production just use redux devtools extension developmentonly see the article for more details 1 5 for react native hybrid desktop and server side redux apps for react native we can use react native debugger which already included the same api with redux devtools extension for most platforms include remote redux devtoolss store enhancer and from the extensions context menu choose open remote devtools for remote monitoring 2 without redux see integrations and the blog post for more details on how to use the extension with any architecture docs options arguments methods advanced api create redux store for debugging faq troubleshooting articles videos feedback demo live demos to use the extension with counter todomvc redux form react tetris book collection angular ngrx store also see examples folder backers support us with a monthly donation and help us continue our activities become a backer sponsors become a sponsor and get your logo on our readme on github with a link to your site become a sponsor license mit created by if you like this follow mdiordiev on twitter
angularjs generator yeoman generator for angularjs lets you quickly set up a project with sensible defaults and best practices there are many starting points for building a new angular single page app in addition to this one you can find other options in this list at yeoman io roadmap for upcoming plans features fixes usage for step by step instructions on using yeoman and this generator to build a todo angularjs application from scratch see this tutorial install yo grunt cli bower generator angular and generator karma npm install g grunt cli bower yo generator karma generator angular if you are planning on using sass you will need to first install ruby and compass install ruby by downloading from here or use homebrew install the compass gem gem install compass make a new directory and cd into it mkdir my new project cd run yo angular optionally passing an app name yo angular app name run grunt for building and grunt serve for preview generators available generators angular aka angular app angular controller angular directive angular filter angular route angular service angular provider angular factory angular value angular constant angular decorator angular view app sets up a new angularjs app generating all the boilerplate you need to get started the app generator also optionally installs bootstrap and additional angularjs modules such as angular resource installed by default example bash yo angular route generates a controller and view and configures a route in app scripts app js connecting them example bash yo angular route myroute produces app scripts controllers myroute js javascript angular module mymod controller myroutectrl function scope produces app views myroute html html p this is the myroute view p explicitly provide route uri example bash yo angular route myroute uri my route produces controller and view as above and adds a route to app scripts app js with uri my route controller generates a controller in app scripts controllers example bash yo angular controller user produces app scripts controllers user js javascript angular module mymod controller userctrl function scope directive generates a directive in app scripts directives example bash yo angular directive mydirective produces app scripts directives mydirective js javascript angular module mymod directive mydirective function return template div div restrict e link function postlink scope element attrs element text this is the mydirective directive filter generates a filter in app scripts filters example bash yo angular filter myfilter produces app scripts filters myfilter js javascript angular module mymod filter myfilter function return function input return myfilter filter input view generates an html view file in app views example bash yo angular view user produces app views user html html p this is the user view p service generates an angularjs service example bash yo angular service myservice produces app scripts services myservice js javascript angular module mymod service myservice function you can also do yo angular factory yo angular provider yo angular value and yo angular constant for other types of services decorator generates an angularjs service decorator example bash yo angular decorator servicename produces app scripts decorators servicenamedecorator js javascript angular module mymod config function provide provide decorator servicename function delegate return delegate options in general these options can be applied to any generator though they only affect generators that produce scripts coffeescript and typescript for generators that output scripts the coffee option will output coffeescript instead of javascript and typescript will output typescript instead of javascript for example bash yo angular controller user coffee produces app scripts controller user coffee coffeescript angular module mymod controller userctrl scope for example bash yo angular controller user typescript produces app scripts controller user ts typescript use strict module demoapp export interface iuserscope extends ng iscope awesomethings any export class userctrl constructor private scope iuserscope scope awesomethings html5 boilerplate angularjs karma angular module demoapp controller userctrl demoapp userctrl minification safe tl dr you dont need to write annotated code as the build step will handle it for you by default generators produce unannotated code without annotations angularjss di system will break when minified typically these annotations that make minification safe are added automatically at build time after application files are concatenated but before they are minified the annotations are important because minified code will rename variables making it impossible for angularjs to infer module names based solely on function parameters the recommended build process uses ng annotate a tool that automatically adds these annotations however if youd rather not use it you have to add these annotations manually yourself why would you do that though if you find a bug in the annotated code please file an issue at ng annotate add to index by default new scripts are added to the index html file however this may not always be suitable some use cases manually added to the file auto added by a 3rd party plugin using this generator as a subgenerator to skip adding them to the index pass in the skip add argument bash yo angular service servicename skip add bower components the following packages are always installed by the app generator angular angular mocks the following additional modules are available as components on bower and installable via bower install angular animate angular aria angular cookies angular messages angular resource angular sanitize all of these can be updated with bower update as new versions of angularjs are released json3 and es5 shim have been removed as angular 1 3 has dropped ie8 support and that is the last version that needed these shims if you still require these you can include them with bower install save json3 es5 shim wiredep should add them to your index html file but if not you can manually add them configuration yeoman generated projects can be further tweaked according to your needs by modifying project files appropriately output you can change the app directory by adding an apppath property to bower json for instance if you wanted to easily integrate with express js you could add the following json name yo test version 0 0 0 apppath public this will cause yeoman generated client side files to be placed inpublic note that you can also achieve the same results by adding an apppath option when starting generator bash yo angular app name apppath public testing running grunt test will run the unit tests with karma contribute see the contributing docs when submitting an issue please follow the guidelines especially important is to make sure yeoman is up to date and providing the command or commands that cause the issue when submitting a pr make sure that the commit messages match the angularjs conventions when submitting a bugfix write a test that exposes the bug and fails before applying your fix submit the test alongside the fix when submitting a new feature add tests that cover the feature changelog recent changes can be viewed on github on the releases page sponsors love yeoman work and community help us keep it alive by donating funds to cover project expenses become a sponsor license bsd license
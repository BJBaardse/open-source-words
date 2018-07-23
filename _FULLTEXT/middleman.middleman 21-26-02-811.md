middleman makes developing websites simple middleman is a static site generator using all the shortcuts and tools in modern web development check out middlemanapp com for detailed tutorials including a getting started guide you can also follow middlemanapp for updates why middleman the last few years have seen an explosion in the amount and variety of tools developers can use to build web applications ruby on rails selects a handful of these tools sass for dry stylesheets coffeescript for safer and less verbose javascript multiple asset management solutions including sprockets erb haml for dynamic pages and simplified html syntax middleman gives the stand alone developer access to all these tools and many many more why would you use a stand alone framework instead of ruby on rails these days many websites are built with an api in mind rather than package the frontend and the backend together both can be built and deployed independently using the public api to pull data from the backend and display it on the frontend static websites are incredibly fast and require very little ram a front end built to stand alone can be deployed directly to the cloud or a cdn many designers and developers simply deliver static html js css to their clients installation middleman is built on ruby and uses the rubygems package manager for installation these are usually pre installed on mac os x and linux windows users can install both using rubyinstaller for windows rubyinstaller devkit is also required gem install middleman getting started once middleman is installed you will have access to the middleman command first lets create a new project from the terminal middleman init my project this will create a new middleman project located in the my project directory this project contains a config rb file for configuring middleman and a source directory for storing your pages stylesheets javascripts and images change directories into your new project and start the preview server cd my project middleman server the preview server allows you to build your site by modifying the contents of the source directory and see your changes reflected in the browser at http localhost 4567 to get started simply develop as you normally would by building html css and javascript in the source directory when youre ready to use more complex templates simply add the templating engines extension to the file and start writing in that format for example say i am working on a stylesheet at source stylesheets site css and id like to start using sass i would rename the file to source stylesheets site css scss and middleman will automatically begin processing that file as sass the same would apply to coffeescript js coffee haml html haml and any other templating engine you might want to use finally you will want to build your project into a stand alone site from the project directory middleman build this will compile your templates and output a stand alone site which can be easily hosted or delivered to your client the build step can also compress images employ javascript css dependency management minify javascript css and run additional code of your choice take a look at the config rb file to see some of the most common extensions which can be activated learn more a full set of in depth instructional guides are available on the official website at http middlemanapp com additionally up to date generated code documentation is available on rubydoc build dependency status community the official community forum is available at http forum middlemanapp com bug reports github issues are used for managing bug reports and feature requests if you run into issues please search the issues and submit new problems https github com middleman middleman issues the best way to get quick responses to your issues and swift fixes to your bugs is to submit detailed bug reports include test cases and respond to developer questions in a timely manner even better if you know ruby you can submit pull requests containing cucumber features which describe how your feature should work or exploit the bug you are submitting how to run cucumber tests checkout repository git clone https github com middleman middleman git install bundler gem install bundler run bundle install inside the project root to install the gem dependencies run test cases bundle exec rake test donate click here to lend your support to middleman versioning this library aims to adhere to semantic versioning 2 0 0 violations of this scheme should be reported as bugs specifically if a minor or patch version is released that breaks backward compatibility that version should be immediately yanked and or a new version should be immediately released that restores compatibility breaking changes to the public api will only be introduced with new major versions as a result of this policy you can and should specify a dependency on this gem using the pessimistic version constraint with two digits of precision for example spec add dependency middleman core 4 0 license copyright c 2010 2017 thomas reynolds mit licensed see license for details
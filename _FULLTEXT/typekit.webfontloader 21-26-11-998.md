web font loader web font loader gives you added control when using linked fonts via font face it provides a common interface to loading fonts regardless of the source then adds a standard set of events you may use to control the loading experience the web font loader is able to load fonts from google fonts typekit fonts com and fontdeck as well as self hosted web fonts it is co developed by google and typekit contents get started configuration events timeout iframes modules adobe edge web fonts custom fontdeck fonts com google typekit browser support license get started to use the web font loader library just include it in your page and tell it which fonts to load for example you could load fonts from google fonts using the web font loader hosted on google hosted libraries using the following code html script src https ajax googleapis com ajax libs webfont 1 6 26 webfont js script script webfont load google families droid sans droid serif script alternatively you can link to the latest 1 x version of the web font loader by using https ajax googleapis com ajax libs webfont 1 webfont js as the script source note that the version in this url is less specific it will always load the latest 1 x version but it also has a shorter cache time to ensure that your page gets updates in a timely manner for performance reasons we recommend using an explicit version number such as 1 6 26 in urls when using the web font loader in production you can manually update the web font loader version number in the url when you want to adopt a new version web font loader is also available on the jsdelivr cdnjs cdns it is also possible to use the web font loader asynchronously for example to load typekit fonts asynchronously you could use the following code html webfontconfig typekit id xxxxxx p p function d var wf d createelement script s d scripts 0 wf src https ajax googleapis com ajax libs webfont 1 6 26 webfont js wf async true s parentnode insertbefore wf s document using the web font loader asynchronously avoids blocking your page while loading the javascript be aware that if the script is used asynchronously the rest of the page might render before the web font loader is loaded and executed which can cause a flash of unstyled text fout the fout can be more easily avoided when loading the web font loader synchronously as it will automatically set the wf loading class on the html element as soon as webfont load has been called the browser will wait for the script to load before continuing to load the rest of the content fout is avoided web font loader is also available on npm as a commonjs module just npm install webfontloader and then require it in your code js var webfont require webfontloader webfont load google families droid sans droid serif configuration the web font loader configuration is defined by a global variable named webfontconfig or passed directly to the webfont load method it defines which fonts to load from each web font provider and gives you the option to specify callbacks for certain events when using the asynchronous approach you must define the global variable webfontconfig before the code that loads the web font loader as in the example above events web font loader provides an event system that developers can hook into it gives you notifications of the font loading sequence in both css and javascript loading this event is triggered when all fonts have been requested active this event is triggered when the fonts have rendered inactive this event is triggered when the browser does not support linked fonts or if none of the fonts could be loaded fontloading this event is triggered once for each font thats loaded fontactive this event is triggered once for each font that renders fontinactive this event is triggered if the font cant be loaded css events are implemented as classes on the html element the following classes are set on the html element css wf loading wf active wf inactive wf familyname fvd loading wf familyname fvd active wf familyname fvd inactive the familyname placeholder will be replaced by a sanitized version of the name of each font family spaces and underscores are removed from the name and all characters are converted to lower case for example droid sans becomes droidsans the fvd placeholder is a font variation description put simply its a shorthand for describing the style and weight of a particular font here are a few examples css n4 font face font style normal font weight normal i7 font face font style italic font weight bold keep in mind that font weight normal maps to font weight 400 and font weight bold maps to font weight 700 if no style weight is specified the default n4 font style normal font weight normal will be used if fonts are loaded multiple times on a single page the css classes continue to update to reflect the current state of the page the global wf loading class is applied whenever fonts are being requested even if other fonts are already active or inactive the wf inactive class is applied only if none of the fonts on the page have rendered otherwise the wf active class is applied even if some fonts are inactive javascript events are implemented as callback functions on the webfontconfig configuration object javascript webfontconfig loading function active function inactive function fontloading function familyname fvd fontactive function familyname fvd fontinactive function familyname fvd the fontloading fontactive and fontinactive callbacks are passed the family name and font variation description of the font that concerns the event it is possible to disable setting classes on the html element by setting the classes configuration parameter to false defaults to true javascript webfontconfig classes false you can also disable font events callbacks by setting the events parameter to false defaults to true javascript webfontconfig events false if both events and classes are disabled the web font loader does not perform font watching and only acts as a way to insert font face rules in the document timeouts since the internet is not 100 reliable its possible that a font will fail to load the fontinactive event will be triggered after 5 seconds if the font fails to render if at least one font successfully renders the active event will be triggered else the inactive event will be triggered you can change the default timeout by using the timeout option on the webfontconfig object javascript webfontconfig google families droid sans timeout 2000 set the timeout to two seconds the timeout value should be in milliseconds and defaults to 3000 milliseconds 3 seconds if not supplied iframes usually its easiest to include a copy of web font loader in every window where fonts are needed so that each window manages its own fonts however if you need to have a single window manage fonts for multiple same origin child windows or iframes that are built up using javascript web font loader supports that as well just use the optional context configuration option and give it a reference to the target window for loading javascript webfontconfig google families droid sans context frames my child this is an advanced configuration option that isnt needed for most use cases modules web font loader provides a module system so that any web font provider can contribute code that allows their fonts to be loaded this makes it possible to use multiple web font providers at the same time the specifics of each provider currently supported by the library are documented here adobe edge web fonts when using adobe edge web fonts you can use the typekit module by passing in a catenated list of fonts in the id parameter and set the api parameter to point to the edge web fonts url javascript webfontconfig typekit id adamina advent pro api use edgefonts net custom to load fonts from any external stylesheet use the custom module here youll need to specify the font family names youre trying to load and optionally the url of the stylesheet that provides the font face declarations for those fonts you can specify a specific font variation or set of variations to load and watch by appending the variations separated by commas to the family name separated by a colon variations are specified using fvd notation javascript webfontconfig custom families my font my other font n4 i4 n7 urls fonts css in this example the fonts css file might look something like this css font face font family my font src font face font family my other font font style normal font weight normal or 400 src font face font family my other font font style italic font weight normal or 400 src font face font family my other font font style normal font weight bold or 700 src if your fonts are already included in another stylesheet you can also leave out the urls array and just specify font family names to start font loading as long as the names match those that are declared in the families array the proper loading classes will be applied to the html element html webfont load custom families my font font face font family my font src url assets fonts my font woff format woff the custom module also supports customizing the test strings that are used to determine whether or not a font has loaded this can be used to load fonts with custom subsets or glyphs in the private use unicode area javascript webfontconfig custom families my font teststrings my font \ue003\ue005 tests strings should be specified on a per font basis and contain at least one character if not specified the default test string besbswy is used fontdeck to use the fontdeck module specify the id of your website you can find this id on the website page within your account settings javascript webfontconfig fontdeck id xxxxx fonts com when using fonts com web fonts specify your project id javascript webfontconfig monotype projectid xxxxxxxx xxxx xxxx xxxx xxxxxxxxxxxx version 12345 optional flushes the cdn cache loadallfonts true optional loads all project fonts the fonts com module has an optional version option which acts as a cache buster optional loadallfonts loads all project fonts by default fonts com module loads only fonts used on the page google using googles font api name the font families youd like to load you can use the same syntax as in the font api to specify styles please note that the google module does not support the fvd syntax that is used in the custom module javascript webfontconfig google families droid sans droid serif bold sometimes the font you requested doesnt come in the default weight e g 400 and you need to explicitly request the variation you want for font events to work e g 300 700 etc javascript webfontconfig google families open sans condensed 300 700 if you need to specify character subsets other than the default e g greek script in addition to latin you must append the subset string to the requested family string after a colon the subset string should follow the google documentation subset names separated by commas javascript webfontconfig google families open sans condensed 300 700 latin greek you can also supply the text parameter to perform character subsetting javascript webfontconfig google families droid sans droid serif text abcdefghijklmnopqrstuvwxyz the text subsetting functionality is only available for the google module typekit when using typekit specify the kit to retrieve by its id you can find the kit id within typekits kit editor interface javascript webfontconfig typekit id xxxxxx fyi typekits own javascript is built using the web font loader library and already provides all of the same font event functionality if youre using typekit you should use their embed codes directly unless you also need to load web fonts from other providers on the same page browser support every web browser has varying levels of support for fonts linked via font face web font loader determines support for web fonts is using the browsers user agent string the user agent string may claim to support a web font format when it in fact does not this is especially noticeable on mobile browsers with a desktop mode which usually identify as chrome on linux in this case a web font provider may decide to send woff fonts to the device because the real desktop chrome supports it while the mobile browser does not the web font loader is not designed to handle these cases and it defaults to believing whats in the user agent string web font providers can build on top of the basic web font loader functionality to handle these special cases individually if web font loader determines that the current browser does not support font face the inactive event will be triggered when loading fonts from multiple providers each provider may or may not support a given browser if web font loader determines that the current browser can support font face and at least one provider is able to serve fonts the fonts from that provider will be loaded when finished the active event will be triggered for fonts loaded from supported providers the fontactive event will be triggered for fonts loaded from a provider that does not support the current browser the fontinactive event will be triggered for example javascript webfontconfig providera family1 providerb family2 if providera can serve fonts to a browser but providerb cannot the fontinactive event will be triggered for family2 the fontactive event will be triggered for family1 once it loads as will the active event copyright and license web font loader copyright c 2010 2017 adobe systems incorporated google incorporated licensed under the apache license version 2 0 the license you may not use this file except in compliance with the license you may obtain a copy of the license at http www apache org licenses license 2 0 unless required by applicable law or agreed to in writing software distributed under the license is distributed on an as is basis without warranties or conditions of any kind either express or implied see the license for the specific language governing permissions and limitations under the license
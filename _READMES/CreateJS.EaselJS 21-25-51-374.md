easeljs easeljs is a library for building high performance interactive 2d content in html5 it provides a feature rich display list to allow you to manipulate and animate graphics it also provides a robust interactive model for mouse and touch interactions it is excellent for building games generative art ads data visualization and other highly graphical experiences it works well alone or with the rest of the createjs suite soundjs preloadjs and tweenjs it has no external dependencies and should be compatible with virtually any framework you enjoy using simple example javascript draw a square on screen var stage new createjs stage mycanvas var shape new createjs shape shape graphics beginfill red drawrect 0 0 120 120 stage addchild shape stage update sprite animation example javascript var ss new createjs spritesheet frames width 32 height 64 numframes 19 animations run 0 25 jump 26 63 run images assets runninggrant png var sprite new createjs sprite ss run sprite scaley sprite scalex 0 4 stage addchild sprite sprite on click function sprite gotoandplay jump createjs ticker on tick stage support and resources find examples and more information at the easeljs web site read the documentation discuss share projects and interact with other users on reddit ask technical questions on stack overflow file verified bugs or formal feature requests using issues on github there is a google group for discussions and support have a look at the included examples and api documentation for more in depth information it was built by gskinner com and is released for free under the mit license which means you can use it for almost any purpose including commercial projects we appreciate credit where possible but it is not a requirement classes the api is inspired in part by flashs display list and should be easy to pick up for both js and as3 developers check out the docs for more information displayobject abstract base class for all display elements in easeljs exposes all of the display properties ex x y rotation scalex scaley skewx skewy alpha shadow etc that are common to all display objects stage the root level display container for display elements each time tick is called on stage it will update and render the display list to its associated canvas container a nestable display container which lets you aggregate display objects and manipulate them as a group bitmap draws an image video or canvas to the canvas according to its display properties sprite displays single frames or animations from sprite sheets and provides apis for managing playback and sequencing shape renders a graphics object within the context of the display list graphics provides an easy to use api for drawing vector data can be used with shape or completely stand alone text renders a single line of text to the stage bitmaptext renders text using a spritesheet of letter domelement an experimental display object that allows you to manage an html element as a part of the display list filter the base filter class that other filters ex blurfilter colormatrixfilter etc extend there are also a few helper classes included shadow defines all of the properties needed to display a shadow on a display object ticker provides a pausable centralized tick manager for ticking stage instances or other time based code uid very simple class that provides global incremental unique numeric ids spritesheet encapsulates all the data associated with a sprite sheet to be used with sprite spritesheetutils contains utility methods for extending existing sprite sheets with flipped frames and extracting individual frames spritesheetbuilder build a bitmap spritesheet from vector graphics at run time get the filesize savings of vector with the performance of a spritesheet matrix2d represents a 3x3 affine transformation matrix used internally for calculating concatenated transformations rectangle represents a rectangle as defined by the points x y and x width y height point represents a point on a 2 dimensional x y coordinate system a webgl implementation currently exists but is limited stagegl a drop in replacement for the easeljs stage class that fully supports a webgl pipeline stagegl will draw most bitmap based content including any cached displayobjects webglinspector a utility and helper class designed to work with stagegl to help investigate and test performance or display problems
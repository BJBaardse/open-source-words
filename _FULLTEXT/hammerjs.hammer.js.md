hammer.js A JavaScript library for detecting touch gestures. Installation NPM sh npm install --save hammerjs or Yarn sh yarn add hammerjs or CDN https://cdnjs.com/libraries/hammer.js/ Usage hammer.js has a quick start option for gestures it already recognizes. ```js // Get a reference to an element. var square = document.querySelector(.square); // Create an instance of Hammer with the reference. var hammer = new Hammer(square); // Subscribe to a quick start event: press, tap, or doubletap. // For a full list of quick start events, read the documentation. hammer.on(press, function(e) { e.target.classList.toggle(expand); console.log("Youre pressing me!"); console.log(e); }); ``` If you want to recognize your own gestures, such as tripletap, then youll have to use these steps: ```js // Get a reference to an element. var square = document.querySelector(.square); // Create a manager to manage the element. var manager = new Hammer.Manager(square); // Create a recognizer. var TripleTap = new Hammer.Tap({ event: tripletap, taps: 3 }); // Add the recognizer to the manager. manager.add(TripleTap); // Subscribe to the event. manager.on(tripletap, function(e) { e.target.classList.toggle(expand); console.log("Youre triple tapping me!"); console.log(e); }); ``` Examples tap double tap press swipe Documentation For further information regarding hammer.js, please read our documentation. Contributions Feel encouraged to report issues or submit pull requests. When youre ready to do either, read our contribution guidelines. If youre looking for another form of contribution, we love help answering questions on our slack channel. License MIT Examples Contributions
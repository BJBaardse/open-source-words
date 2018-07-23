→ Selectize is looking for new members on the maintenance team! selectize.js Selectize is an extensible jQuery-based custom <select> UI control. Its useful for tagging, contact lists, country selectors, and so on. It clocks in at around ~7kb (gzipped). The goal is to provide a solid & usable experience with a clean and powerful API. Demos Changelog Examples Usage Documentation API Documentation Plugin Documentation Browser Test Matrix Features Smart Option Searching / RankingOptions are efficiently scored and sorted on-the-fly (using sifter). Want to search an items title and description? No problem. Caret between itemsOrder matters sometimes. Use the ← and → arrow keys to move between selected items. Select & delete multiple items at onceHold down option on Mac or ctrl on Windows to select more than one item to delete. Díåcritîçs supportedGreat for international environments. Item creationAllow users to create items on the fly (async saving is supported; the control locks until the callback is fired). Remote data loadingFor when you have thousands of options and want them provided by the server as the user types. Clean API & codeInterface with it and make modifications easily. Pull requests welcome! Extensible Plugin API for developing custom features (uses microplugin). Touch Support Plays nice with iOS 5+ devices. Dependencies jquery (1.7 and greater) sifter (bundled in "standalone" build) microplugin (bundled in "standalone" build) Installation and files All pre-built files needed to use Selectize can be found in the "dist" folder. If youre looking to get started with minimal fuss, include standalone/selectize.min.js (bundles Sifter and Microplugin dependencies – also available un-minified for debugging, just remove the .min part) and css/selectize.default.css. Selectize is available at cdnjs. js/ standalone/ selectize.js — With dependencies, minus jquery selectize.js — Without dependencies less/ selectize.less — Core styles selectize.default.less — Default theme selectize.bootstrap2.less — Bootstrap 2 theme selectize.bootstrap3.less — Bootstrap 3 theme plugins/ — Individual plugin styles css/ selectize.css — Core styles selectize.default.css — Default theme (with core styles) selectize.bootstrap2.css - Bootstrap 2 theme selectize.bootstrap3.css - Bootstrap 3 theme Usage js $(select).selectize(options); The available options are documented here. IE8 Support To support Internet Explorer 8, es5-shim must be added your page. html <!--[if lt IE 9]><script src="http://cdnjs.cloudflare.com/ajax/libs/es5-shim/2.0.8/es5-shim.min.js"></script><![endif]--> Custom Builds By default, all plugins are included. To hand-pick what plugins (if any) to include, run grunt with the "--plugins" flag. After this completes, grab the files you need from the "dist" folder. ```sh dependencies npm install build selectize grunt --plugins= grunt --plugins=* grunt --plugins=remove_button,restore_on_backspace ``` Contributing When issuing a pull request: please do not include/commit changes in the dist/ folder to avoid merge conflicts. A good way to include the right files is to use git gui or git add when committing to select the files you want to add to your commit. please include tests with your feature so that were not tempted to break it in the future! Add an entry to the top of the CHANGELOG, and update the documentation in docs/ as needed. (Refactors and documentation changes dont need a changelog entry.) Squash your commits together in one or a few complete, logical commits, with a concise and descriptive message. One commit means one feature/bugfix/thing that has changed, or a diff bringing the code one step forward to a better, working state. Once your commit is nice and clean, and you want to discard the other changes, you can use git checkout . (that will erase changes to tracked files) and git clean [-i/--interactive] (to erase untracked files). However, be careful with those commands, as their function is to erase things/changes. Tests Please ensure all the tests pass: sh $ npm test # phantomjs $ BROWSERS=Firefox npm test $ BROWSERS=Firefox,Chrome npm test $ BROWSERS=Firefox,Chrome,Safari npm test Local environment To run Selectize locally: sh $ npm start You can then run the examples in http://localhost:8000/examples/. However, be careful not to add the dist/ files in your commit, as Grunt automatically regenerates the files in dist/ as the source is changed. License Copyright © 2013–2016 Brian Reavis & Contributors Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at: http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
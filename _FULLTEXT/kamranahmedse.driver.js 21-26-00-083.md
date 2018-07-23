driver js powerful yet light weight vanilla javascript engine to drive the users focus across the page only 4kb no external dependency supports all major browsers and highly customizable simple is simple to use and has no external dependency at all light weight 4kb in size vanilla javascript and no external dependency highly customizable has a powerful api and can be used however you want highlight anything highlight any literally any element on page feature introductions create powerful feature introductions for your web applications focus shifters add focus shifters for users user friendly everything is controllable by keyboard consistent behavior usable across all browsers including in famous ie mit licensed free for personal and commercial use for usage and examples have a look at demo so yet another tour library no it is not tours are just one of the many use cases driver js can be used wherever you need some sort of overlay for the page some common usecases could be e g dimming the background when user is interacting with some component i e the way facebook does when you try to create a post using it as a focus shifter to bring users attention to some component on page or using it to simulate those turn off the lights widgets that you might have seen on video players online etc driver js is written in vanilla js has zero dependencies and is highly customizable it has several options allowing you to manipulate how it behaves and also provides you the hooks to manipulate the elements as they are highlighted about to be highlighted or deselected installation you can install it using yarn or npm whatever you prefer bash yarn add driver js npm install driver js or include it using cdn if you want a specific version put it as driver js 0 5 in the name html script src https unpkg com driver js dist driver min js script script src https unpkg com driver js dist driver min css script or grab the code from dist directory and include it directly html link rel stylesheet href dist driver min css script src dist driver min js script usage and demo demos and many more usage examples can be found in the docs page highlighting single element – demo you can highlight a single element by simply passing the selector javascript const driver new driver driver highlight create post a real world usage example for this is using it to dim the background and highlight the required element e g the way facebook does it when creating a post highlight and popover – demo you can show additional details beside the highlighted element using the popover javascript const driver new driver driver highlight element some element popover title title for the popover description description for it also title and description can have html as well positioning the popover – demo by default driver automatically finds the suitable position for the popover and displays it you can override it using position property javascript const driver new driver driver highlight element some element popover title title for the popover description description for it position left can be top left right bottom creating feature introductions – demo feature introductions are helpful when onboarding new users and giving them an idea about different parts of the application you can create them seemlessly with driver define the steps and call the start when you want to start presenting user will be able to control the steps using the keyboard or using the buttons on popovers javascript const driver new driver define the steps for introduction driver definesteps element first element introduction popover title title on popover description body of the popover position left element second element introduction popover title title on popover description body of the popover position top element third element introduction popover title title on popover description body of the popover position right start the introduction driver start you can also hide the buttons and control the introductions programmatically by using the api methods listed below asynchronous actions – demo for any asynchronous actions between the transition steps you may delay the execution till the action completes all you have to do is stop the transition using driver preventmove in your onnext or onprevious callbacks and initiate it manually using driver movenext here is a sample implementation where it will stop at the second step for four seconds and then move on to the next step javascript const driver new driver define the steps for introduction driver definesteps element first element introduction popover title title on popover description body of the popover position left element second element introduction popover title title on popover description body of the popover position top onnext prevent moving to the next step driver preventmove perform some action or create the element to move to and then move to that element settimeout driver movenext 4000 element third element introduction popover title title on popover description body of the popover position right start the introduction driver start you can also hide the buttons and control the introductions programmatically by using the api methods listed below api driver comes with several options that you can manipulate to make driver behave as you like driver definition here are the options that driver understands javascript const driver new driver animate true whether to animate or not opacity 0 75 background opacity 0 means only popovers and without overlay padding 10 distance of element from around the edges allowclose true whether the click on overlay should close or not overlayclicknext false whether the click on overlay should move next donebtntext done text on the final button closebtntext close text on the close button for this step stagebackground ffffff background color for the staged behind highlighted element nextbtntext next next button text for this step prevbtntext previous previous button text for this step showbuttons false do not show control buttons in footer keyboardcontrol true allow controlling through keyboard escape to close arrow keys to move scrollintoviewoptions we use scrollintoview when possible pass here the options for it if you want any onhighlightstarted element called when element is about to be highlighted onhighlighted element called when element is fully highlighted ondeselected element called when element has been deselected onreset element called when overlay is about to be cleared onnext element called when moving to next step on any step onprevious element called when moving to next step on any step note that all the button options that you provide in the driver definition can be overridden for a specific step by giving them in the step definition step definition here are the set of options that you can pass while defining steps definesteps or the object that you pass to highlight method javascript const stepdefinition element some item query selector string or node to be highlighted stagebackground ffffff this will override the one set in driver popover there will be no popover if empty or not given title title title on the popover description description body of the popover showbuttons false do not show control buttons in footer donebtntext done text on the last button closebtntext close text on the close button nextbtntext next next button text prevbtntext previous previous button text onnext called when moving to next step from current step onprevious called when moving to next step from current step for example here is how it would look when highlighting a single element javascript const driver new driver driveroptions driver highlight stepdefinition and this is how it would look when creating a step by step guide javascript const driver new driver driveroptions driver definesteps stepdefinition1 stepdefinition2 stepdefinition3 stepdefinition4 api methods below are the set of methods that are available javascript const driver new driver driveroptions checks if the driver is active or not if driver isactivated console log driver is active in case of the steps guide you can call below methods driver definesteps stepdefinition1 stepdefinition2 stepdefinition3 driver start stepnumber 0 starts driving through the defined steps driver movenext moves to next step in the steps list driver moveprevious moves to previous step in the steps list driver hasnextstep checks if there is next step to move to driver haspreviousstep checks if there is previous step to move to prevents the current move useful in onnext or onprevious if you want to perform some asynchronous task and manually move to next step driver preventmove highlights the element using query selector or the step definition driver highlight string stepdefinition resets the overlay and clears the screen driver reset additionally you can pass a boolean parameter to clear immediately and not do the animations etc could be useful when you lets say want to run a different instance of driver while one was running driver reset clearimmediately false checks if there is any highlighted element if driver hashighlightedelement console log there is an element highlighted gets the currently highlighted element on screen it would be an instance of src core element js const activeelement driver gethighlightedelement gets the last highlighted element would be an instance of src core element js const lastactiveelement driver getlasthighlightedelement activeelement getcalculatedposition gets screen co ordinates of the active element activeelement hidepopover hide the popover activeelement showpopover show the popover activeelement getnode gets the dom element behind this element note – do not forget to add e stoppropagation to the click binding that triggers driver contributions feel free to submit pull requests create issues or spread the word sponsored by thanks to browserstack for sponsoring the compatibility testing needs license mit © kamran ahmed
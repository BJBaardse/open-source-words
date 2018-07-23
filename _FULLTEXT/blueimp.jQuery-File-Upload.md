jQuery File Upload Plugin Demo Demo File Upload Description File Upload widget with multiple file selection, drag&drop support, progress bars, validation and preview images, audio and video for jQuery. Supports cross-domain, chunked and resumable file uploads and client-side image resizing. Works with any server-side platform (PHP, Python, Ruby on Rails, Java, Node.js, Go etc.) that supports standard HTML form file uploads. Setup How to setup the plugin on your website How to use only the basic plugin (minimal setup guide). Features Multiple file upload: Allows to select multiple files at once and upload them simultaneously. Drag & Drop support: Allows to upload files by dragging them from your desktop or filemanager and dropping them on your browser window. Upload progress bar: Shows a progress bar indicating the upload progress for individual files and for all uploads combined. Cancelable uploads: Individual file uploads can be canceled to stop the upload progress. Resumable uploads: Aborted uploads can be resumed with browsers supporting the Blob API. Chunked uploads: Large files can be uploaded in smaller chunks with browsers supporting the Blob API. Client-side image resizing: Images can be automatically resized on client-side with browsers supporting the required JS APIs. Preview images, audio and video: A preview of image, audio and video files can be displayed before uploading with browsers supporting the required APIs. No browser plugins (e.g. Adobe Flash) required: The implementation is based on open standards like HTML5 and JavaScript and requires no additional browser plugins. Graceful fallback for legacy browsers: Uploads files via XMLHttpRequests if supported and uses iframes as fallback for legacy browsers. HTML file upload form fallback: Allows progressive enhancement by using a standard HTML file upload form as widget element. Cross-site file uploads: Supports uploading files to a different domain with cross-site XMLHttpRequests or iframe redirects. Multiple plugin instances: Allows to use multiple plugin instances on the same webpage. Customizable and extensible: Provides an API to set individual options and define callback methods for various upload events. Multipart and file contents stream uploads: Files can be uploaded as standard "multipart/form-data" or file contents stream (HTTP PUT file upload). Compatible with any server-side application platform: Works with any server-side platform (PHP, Python, Ruby on Rails, Java, Node.js, Go etc.) that supports standard HTML form file uploads. Requirements Mandatory requirements jQuery v. 1.6+ jQuery UI widget factory v. 1.9+ (included): Required for the basic File Upload plugin, but very lightweight without any other dependencies from the jQuery UI suite. jQuery Iframe Transport plugin (included): Required for browsers without XHR file upload support. Optional requirements JavaScript Templates engine v. 2.5.4+: Used to render the selected and uploaded files for the Basic Plus UI and jQuery UI versions. JavaScript Load Image library v. 1.13.0+: Required for the image previews and resizing functionality. JavaScript Canvas to Blob polyfill v. 2.1.1+:Required for the image previews and resizing functionality. blueimp Gallery v. 2.15.1+: Used to display the uploaded images in a lightbox. Bootstrap v. 3.2.0+ Glyphicons The user interface of all versions, except the jQuery UI version, is built with Bootstrap and icons from Glyphicons. Cross-domain requirements Cross-domain File Uploads using the Iframe Transport plugin require a redirect back to the origin server to retrieve the upload results. The example implementation makes use of result.html as a static redirect page for the origin server. The repository also includes the jQuery XDomainRequest Transport plugin, which enables limited cross-domain AJAX requests in Microsoft Internet Explorer 8 and 9 (IE 10 supports cross-domain XHR requests). The XDomainRequest object allows GET and POST requests only and doesnt support file uploads. It is used on the Demo to delete uploaded files from the cross-domain demo file upload service. Custom Backends You can add support for various backends by adhering to the specification outlined here. Browsers Desktop browsers The File Upload plugin is regularly tested with the latest browser versions and supports the following minimal versions: Google Chrome Apple Safari 4.0+ Mozilla Firefox 3.0+ Opera 11.0+ Microsoft Internet Explorer 6.0+ Mobile browsers The File Upload plugin has been tested with and supports the following mobile browsers: Apple Safari on iOS 6.0+ Google Chrome on iOS 6.0+ Google Chrome on Android 4.0+ Default Browser on Android 2.3+ Opera Mobile 12.0+ Supported features For a detailed overview of the features supported by each browser version, please have a look at the Extended browser support information. Contributing Bug fixes and new features can be proposed using pull requests. Please read the contribution guidelines before submitting a pull request. Support This project is actively maintained, but there is no official support channel. If you have a question that another developer might help you with, please post to Stack Overflow and tag your question with blueimp jquery file upload. License Released under the MIT license.
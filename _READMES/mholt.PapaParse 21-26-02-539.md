parse csv with javascript papa parse is the fastest in browser csv or delimited text parser for javascript it is reliable and correct according to rfc 4180 and it comes with these features easy to use parse csv files directly local or over the network fast mode is really fast stream large files even via http reverse parsing converts json to csv auto detect delimiter worker threads to keep your web page reactive header row support pause resume abort can convert numbers and booleans to their types optional jquery integration to get files from input type file elements one of the only parsers that correctly handles line breaks and quotations papa parse has no dependencies not even jquery install papaparse is available on npm it can be installed with the following command npm install papaparse if you dont want to use npm papaparse min js can be downloaded to your project source homepage demo homepage demo to learn how to use papa parse documentation the website is hosted on on github pages if you want to contribute just clone the gh branch of this repository and open a pull request papa parse for node papa parse can parse a readable stream instead of a file when used in node js environments in addition to plain strings in this mode encoding must if specified be a node supported character encoding the papa localchunksize papa remotechunksize download withcredentials and worker config options are unavailable papa parse can also parse in a node streaming style which makes pipe available simply pipe the readable stream to the stream returned from papa parse papa node stream input options the papa localchunksize papa remotechunksize download withcredentials worker step and complete config options are unavailable to register a callback with the stream to process data use the data event like so stream on data callback and to signal the end of stream use the end event like so stream on end callback get started for usage instructions see the homepage and for more detail the documentation tests papa parse is under test download this repository run npm install then npm test to run the tests contributing to discuss a new feature or ask a question open an issue to fix a bug submit a pull request to be credited with the contributors remember a pull request with test is best you may also discuss on twitter with papaparse or directly to me mholt6 if you contribute a patch ensure the tests suite is running correctly we run continuous integration on each pull request and will not accept a patch that breaks the tests
help me build lowdb v2 looking for your feedback https goo gl forms 7682m3xyzktr6put1 lowdb small json database for node electron and the browser powered by lodash zap js db get posts push id 1 title lowdb is awesome write usage sh npm install lowdb js const low require lowdb const filesync require lowdb adapters filesync const adapter new filesync db json const db low adapter set some defaults required if your json file is empty db defaults posts user count 0 write add a post db get posts push id 1 title lowdb is awesome write set a user using lodash shorthand syntax db set user name typicode write increment count db update count n n 1 write data is saved to db json json posts id 1 title lowdb is awesome user name typicode count 1 you can use any of the powerful lodash functions like get and find with shorthand syntax js for performance use value instead of write if youre only reading from db db get posts find id 1 value lowdb is perfect for clis small servers electron apps and npm packages in general it supports node the browser and uses lodash api so its very simple to learn actually if you know lodash you already know how to use lowdb wink usage examples cli browser server in memory jsfiddle live example important lowdb doesnt support cluster and may have issues with very large json files 200mb install sh npm install lowdb alternatively if youre using yarn sh yarn add lowdb a umd build is also available on unpkg for testing and quick prototyping html script src https unpkg com lodash 4 lodash min js script script src https unpkg com lowdb 0 17 dist low min js script script src https unpkg com lowdb 0 17 dist localstorage min js script script var adapter new localstorage db var db low adapter script api low adapter returns a lodash chain with additional properties and functions described below db write and db value write writes database to state on the other hand value is just prototype value and should be used to execute a chain that doesnt change database state js db set user name typicode write please note that db write is syntactic sugar and equivalent to js db set user name typicode value db write db database lodash instance use it to add your own utility functions or third party mixins like underscore contrib or lodash id js db mixin second function array return array 1 db get posts second value db getstate returns database state js db getstate posts db setstate newstate replaces database state js const newstate db setstate newstate db write persists database using adapter write depending on the adapter may return a promise js with lowdb adapters filesync db write console log state has been saved with lowdb adapters fileasync db write then console log state has been saved db read reads source using storage read option depending on the adapter may return a promise js with lowdb filesync db read console log state has been updated with lowdb fileasync db read then console log state has been updated adapters api please note this only applies to adapters bundled with lowdb third party adapters may have different options for convenience filesync fileasync and localbrowser accept the following options defaultvalue if file doesnt exist this value will be used to set the initial state default serialize deserialize functions used before writing and after reading default json stringify and json parse js const adapter new filesync array yaml defaultvalue serialize array toyamlstring array deserialize string fromyamlstring string guide how to query with lowdb you get access to the entire lodash api so there are many ways to query and manipulate data here are a few examples to get you started please note that data is returned by reference this means that modifications to returned objects may change the database to avoid such behaviour you need to use clonedeep also the execution of methods is lazy that is execution is deferred until value or write is called examples check if posts exists js db has posts value set posts js db set posts write sort the top five posts js db get posts filter published true sortby views take 5 value get post titles js db get posts map title value get the number of posts js db get posts size value get the title of first post using a path js db get posts 0 title value update a post js db get posts find title low assign title hi write remove posts js db get posts remove title low write remove a property js db unset user name write make a deep clone of posts js db get posts clonedeep value how to use id based resources being able to get data using an id can be quite useful particularly in servers to add id based resources support to lowdb you have 2 options shortid is more minimalist and returns a unique id that you can use when creating resources js const shortid require shortid const postid db get posts push id shortid generate title low write id const post db get posts find id postid value lodash id provides a set of helpers for creating and manipulating id based resources js const lodashid require lodash id const filesync require lowdb adapters filesync const adapter new filesync db json const db low adapter db mixin lodashid we need to set some default values if the collection does not exist yet we also can store our collection const collection db defaults posts get posts insert a new post const newpost collection insert title low write and retrieve it using its id const post collection getbyid newpost id value how to create custom adapters low accepts custom adapter so you can virtually save your data to any storage using any format js class mystorage constructor read should return data object or array or a promise write data should return nothing or a promise const adapter new mystorage args const db low see src adapters for examples how to encrypt data filesync fileasync and localstorage accept custom serialize and deserialize functions you can use them to add encryption logic js const adapter new filesync db json serialize data encrypt json stringify data deserialize data json parse decrypt data changelog see changes for each version in the release notes limits lowdb is a convenient method for storing data without setting up a database server it is fast enough and safe to be used as an embedded database however if you seek high performance and scalability more than simplicity you should probably stick to traditional databases like mongodb license mit typicode cactus
# gun.db
ODBC/Sqlite native persistence layer for [gun](https://github.com/amark/gun)! GUN is an Open Source Firebase with swappable storage engines (level, SQLite, etc.) that handles data synchronization across machines / devices.


Get it by

`npm install gun.db`

Use by

```javascript
var Gun = require('gun');
require('gun.db');

var gun = Gun({
  file: false // turn off pesky file.js data.json default
  , db: {
    file: "gun.db"
  }
});
```

Check the gun docs on how to read/write data, it will then handle sync automatically for you (even to the browser!). Tip: It is a graph database, so you can do key/value, document, relational, or graph based data - here is a [crash course](https://github.com/amark/gun/wiki/graphs) on how to use it.

Enjoy!

Or: Complain about bugs. :)


# notes
   If the filename is '*.db' it defaults to sqlite if it's not it tries it as a DSN (data source name) and then if that doesn't work falls back to use sqlite filename.
   ODBC can be provided by providing unixodbc on linux, but requires modifying the build to enable; it  is by default only enabled for windows.

   It also ends up writing a sql.config file somewhere ... there's options you can set there to enable sql logging (optionally with data returned) which goes to stderr   
     under windows this goes to (/programdata/freedom collective/node/...) probably.  If your node.exe is not what your running it will be in a folder that is whatever the program name is minus the last (.*)
     under not windows it probably just goes to ~
     
    

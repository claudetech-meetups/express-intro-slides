## Improve project layout

We are now going to change `app.js` to
export a function returning the app, and we
will start listening in another that we are going to
call `server.js`.

```javascript
var express    = require('express'),
    mongoose   = require('mongoose'),
    bodyParser = require('body-parser'),
    cors       = require('cors'),
    db         = mongoose.connection;


module.exports = function (config, callback) {
  ...
  mongoose.connect(config.mongo_url);
  ....
  db.on('error', function (err) {
    console.warn("Could not connect to mongodb");
    console.warn(err);
    callback(err);
  });

  ...
  db.once('open', function () {
    ...
    app.use('/categories', require('./routes/categories'));
    callback(null, app);
  });
};
```

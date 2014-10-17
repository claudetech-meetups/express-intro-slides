## Database setup

We are now going to setup our application to use MongoDB.

```javascript
// app.js
var express  = require('express'),
    mongoose = require('mongoose'),
    db       = mongoose.connection;

mongoose.connect('mongodb://localhost/blog_api');
db.on('error', function (err) {
  console.warn("Could not connect to mongodb");
  process.exit(1);
});

db.once('open', function () {
  var app = express();
  app.use('/posts',      require('./routes/posts'));
  app.use('/categories', require('./routes/categories'));
  app.listen(5000);
});
```

Here, we connect to local MongoDB's `blog_api` database.

If an error occurs during the connection, we exit, otherwise,
we start the application once connected.

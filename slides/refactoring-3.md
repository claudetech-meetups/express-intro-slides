## Improve project layout

Now, we are going to create `server.js` to run
our server.

```javascript
var env    = process.env.NODE_ENV || 'dev',
    config = require('./config')[env];

require('./app')(config, function (err, app) {
  if (err) {
    console.warn(err);
    process.exit(1);
  }
  app.listen(config.port);
});
```

You can now try to start the server with

```sh
$ nodemon server.js
```

If everything went fine, you should be able to access
<a href="http://localhost:5000/posts" target="_blank">localhost:5000/posts</a>
as before.

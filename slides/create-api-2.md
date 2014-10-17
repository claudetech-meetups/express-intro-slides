## Prepare to create a post

We are now going to create a post. We need to receive
JSON, so we are going to use the `body-parser` module.

```sh
$ npm install --save body-parser
```

Then, we need to use the `body-parser` middleware.

```javascript
// app.js
var ...
    bodyParser = require('body-parser'),
    db         = mongoose.connection;
....
db.once('open', function () {
  var app = express();
  app.use(bodyParser.json());
  app.use(function (err, req, res, next) {
    if (err) res.status(500).json({error: err.message});
  });
....
```

We need to require the `body-parser` module, and to use
`app.use` to include the `bodyParser` middleware. We will now
be able to access JSON content through `req.body`.
We also return a 500 if anything went wrong.

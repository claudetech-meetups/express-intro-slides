## CORS support

To accept cross-domain requests, we need to enable [CORS](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing). We will use an existent module.

```sh
$ npm install cors
```

and use the middleware provided

```javascript
// app.js
var express    = require('express'),
    mongoose   = require('mongoose'),
    bodyParser = require('body-parser'),
    cors       = require('cors'),
    db         = mongoose.connection;
....

db.once('open', function () {
  var app = express();
  app.use(cors());
  app.use(bodyParser.json());
  ....
```

and we are done.

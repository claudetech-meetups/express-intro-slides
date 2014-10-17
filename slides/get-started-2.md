## Basic application

Create a *very* basic application.

```javascript
var express = require('express');

var app = express();

app.get('/', function (req, res) {
  res.json({foo: "bar"});
});

app.listen(5000);
```

This will create an Express application with an HTTP server
listening on port 5000.

On `GET` to the root path '/', the application will return
`{foo: "bar"}`, serialized to JSON.

You can try the app by running

```sh
$ node app.js
```

and accessing <a href="http://localhost:5000/" target="_blank">localhost:5000</a> in your browser.

## Library install

Now that we can use MongoDB, we are going to need a way
to access it via Node.js.

We are therefore going to install [mongoose](http://mongoosejs.com/index.html) to use MongoDB easily from Node.

```sh
$ npm install --save mongoose
```

To check if there is no problem, we are going to create a new file with the following content

```javascript
// mongoose_test.js
var mongoose = require('mongoose'),
    db       = mongoose.connection;
mongoose.connect('mongodb://localhost/blog_api');
db.on('error', console.warn.bind(console, 'connection error'));
db.once('open', console.log.bind(console, 'connected'));
```

and run it

```sh
$ node mongoose_test.js
```

it the output is `connected`, we can delete the file and go on.

## Prepare test environment

To test our app, we need to create the app.
We will use `before` to prepare everything.
We will also close the DB connection in `after`,
and remove all posts from databases before each test.

```javascript
// test/posts_test.js
describe('Posts', function () {
  var app, models;

  before(function (done) {
    require('../app')(config, function (err, a) {
      models  = require('../models');
      if (err) return done(err);
      app = a;
      done();
    });
  });

  after(function () {
    require('mongoose').connection.close();
  });

  beforeEach(function (done) {
    models.Post.remove({}, function (err) {
      done(err);
    });
  });
  ...
```

this will be called once before running the tests in `Posts`.

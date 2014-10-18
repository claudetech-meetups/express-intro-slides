## Test 'GET /posts' with query

To check for categories, we first need to create some.
We will therefore modify the `before` and `after` hooks
to create and remove categories.

```javascript
...
describe('Posts', function () {
  var app, models, categories;

  before(function (done) {
    require('../app')(config, function (err, a) {
      if (err) return done(err);
      models  = require('../models');
      categories = [];
      models.Category.create([{name: "foo"}, {name: "bar"}], function (err, cat1, cat2) {
        categories.push(cat1);
        categories.push(cat2);
      });
      app = a;
      done();
    });
  });

  after(function (done) {
    models.Category.remove({}, function (err) {
      require('mongoose').connection.close();
      done(err);
    });
  });
...
```

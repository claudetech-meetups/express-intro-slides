## Using models

First, to export models, we create `models/index.js` where
we export all our models.

```javascript
// models/index.js
module.exports = {
  Post: require('./post'),
  Category: require('./category')
};
```

We are now going to change `posts.js` to use our `Post` model.

```javascript
// routes/posts.js
var express = require('express'),
    router  = express.Router(),
    models  = require('../models');
router.get('/', function (req, res) {
  models.Post.find(function (err, posts) {
    if (err) return res.status(500).json({error: err.message});
    res.json(posts);
  });
});
module.exports = router;
```

Here, we try to get all the posts, if there is an error we
return it with a 500 status, otherwise we return the posts
serialized in JSON.

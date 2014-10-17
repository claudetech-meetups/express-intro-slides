## Creating a router

Express 4 provides a `Router`, to handle routing
more concisely.

We have `/posts` and `/categories`, so we will create a router
for each.

In a new directory called `routes`, we are going to create `posts.js` and
`categories.js`.

```javascript
// routes/posts.js
var express = require('express'),
    router  = express.Router();

router.get('/', function (req, res) {
    res.json({router: 'posts', path: '/'});
});

module.exports = router;
```

Put the same content in `routes/categories` and replace
`router: 'posts'` by `router: 'categories'`.

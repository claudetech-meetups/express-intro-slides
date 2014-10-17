## Filtering posts by category

The only thing left to complete our API is to filter posts by
category. For this, we will use the `/categories` route
and filter with `category_id` parameter.

We are therefore going to change `routes/posts.js`

```javascript
// routes/posts.js

...
router.get('/', function (req, res) {
  var query = req.query.category_id ? {categoryId: req.query.category_id} : {};
  models.Post.find(query, function (err, posts) {
    if (err) return res.status(500).json({error: err.message});
    res.json(posts);
  });
});
```

If the `category_id` parameter is given, we set the query using the given id
otherwise we set an empty query.

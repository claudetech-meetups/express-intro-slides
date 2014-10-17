## Getting a single post

We now have everything we need to create the rest of the API.

Let's start by getting a single post.

```javascript
// routes/posts.js
...
router.get('/:id', function (req, res) {
  models.Post.findOne({_id: req.params.id}, function (err, post) {
    if (err) return res.status(500).json({error: err.message});
    if (!post) return res.status(404).json({error: "not found"});
    res.json(post);
  });
});
```

Here, we catch all the routes of the form `/posts/:id` where id
is the object id. We try to get the post with the id. If an error
is returned, we respond with 500, if the object does not exist, 404
and otherwise we return the object.


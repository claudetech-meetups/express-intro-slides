## Create post

We can now create a post very easily.

```javascript
// routes/posts.js
...
router.post('/', function (req, res) {
  models.Post.create(req.body, function (err, post) {
    if (err) return res.status(500).json({error: err.message});
    res.status(201).json(post);
  });
});
```

We just call the `create` method with the parsed request body,
return 500 (which should actually be 422 in most cases) if an error occured
and return the created post otherwise.

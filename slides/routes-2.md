## Using a router

In `app.js`, we will now use the router we just created.

```javascript
// app.js

...
app.use('/posts',      require('./routes/posts'));
app.use('/categories', require('./routes/categories'));

app.listen(5000);
```

You can now try to access <a href="http://localhost:5000/posts" target="_blank">localhost:5000/posts</a> and <a href="http://localhost:5000/categories" target="_blank">localhost:5000/categories</a>

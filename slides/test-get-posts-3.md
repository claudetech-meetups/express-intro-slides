## Another test for 'GET /posts'

We are now going to check that the data returned
by the method is correct.

```javascript
...
    it('should return all posts', function (done) {
      models.Post.create({title: "foo", content: "bar"}, function (err, expected) {
        request(app)
          .get('/posts')
          .expect(200)
          .expect(function (res) {
            body = JSON.parse(res.text);
            expect(body.length).to.eq(1);
            var post = body[0];
            expect(post.id).to.eq(expected._id.toString());
            expect(post.title).to.eq(expected.title);
            expect(post.content).to.eq(expected.content);
          })
          .end(done);
      });
...
```

Here, the `expect(function (res)` receives the response,
where `text` is the string representation of the payload.
`expect` is part of the `chai` assertion library.

## Test `GET /posts/:id`

We are now going to test with an existing post.

```javascript
...
    it('should return existing post', function (done) {
      models.Post.create({title: "foo", content: "bar"}, function (err, expected) {
        request(app)
          .get('/posts/' + expected.id.toString())
          .expect(200)
          .expect(function (res) {
            post = res.body;
            expect(post.id).to.eq(expected._id.toString());
            expect(post.title).to.eq(expected.title);
            expect(post.content).to.eq(expected.content);
          })
          .end(done);
      });
    });
...
```

## Test 'GET /posts' with query

We now need to write the test to check we get
only the posts in the given category.

```javascript
...
    it('should filter with categoryId', function (done) {
      models.Post.create([
        {title: "post1", content: "post2", categoryId: categories[0]._id},
        {title: "post1", content: "post2", categoryId: categories[1]._id}
      ], function (err, expected) {
        expect(err).to.be.null;
        request(app)
          .get('/posts?category_id=' + categories[0]._id.toString())
          .expect(200)
          .expect(function (res) {
            body = JSON.parse(res.text);
            expect(body.length).to.eq(1);
            var post = body[0];
            expect(post.id).to.eq(expected._id.toString());
            expect(post.title).to.eq(expected.title);
            expect(post.content).to.eq(expected.content);
            expect(post.categoryId).to.eq(expected.categoryId.toString());
          })
          .end(done)
      });
    });
...
```

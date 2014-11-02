## Test `POST /posts`

We are finally going to test new post creation.

```javascript
...
  describe('POST /posts', function () {
    it('should create Post', function (done) {
      var postContent = {title: "foo", content: "bar"};
      request(app)
        .post('/posts')
        .send(postContent)
        .expect(201)
        .expect(function (res) {
          post = res.body;
          expect(post.id).not.to.be.null;
          expect(post.title).to.eq(postContent.title);
          expect(post.content).to.eq(postContent.content);
        })
        .end(done);
    });
  });
...
```

## First real test

We can now write some real tests, so let's
check that `/posts` returns 200.

```javascript
// tests/posts_test.js
    it('should success', function (done) {
      request(app)
        .get('/posts')
        .expect(200)
        .end(done);
    });
```

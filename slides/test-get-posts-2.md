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

Here, we expect the response status to be `200`, and
call `done` when finished. `done` is used by Mocha
to know an async test has finished. Mocha will
timeout if `done` is passed to the function and not called.

When running mocha, no error should be raised.

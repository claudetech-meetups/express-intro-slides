## Test `GET /posts/:id`

We are first going to test the two cases
where it should fail: bad OID and unexisting OID.

```javascript
  describe('GET /posts/:id', function () {
    it('should fail with bad OID', function (done) {
      request(app)
        .get('/posts/foo')
        .expect(500)
        .end(done);
    });

    it('should return 404 with non existing OID', function (done) {
      request(app)
        .get('/posts/5441f8033e9b22331737fbd1')
        .expect(404)
        .end(done);
    });
  });
```

If everything is passing, we are good.

To understand how `describe` is useful, you can try to run

```sh
$ mocha --reporter=spec
```

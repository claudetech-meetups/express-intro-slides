## First test

We are now going to write our first test. First,
we are going to test posts.

First let's create a dummy test.

```javascript
// test/posts_test.js
var request = require('supertest'),
    expect  = require('chai').expect,
    config  = require('../config').test;

describe('Posts', function () {
  describe('GET /posts', function () {
    it('should success', function () {
      expect(true).to.be.true;
    });
});
```

mocha should now give the following output.

```sh
$ mocha

  1 passing (1ms)
```

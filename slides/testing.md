## Testing

We are now ready to test our application.
For testing we are going to use

* Testing framework: [mocha](http://visionmedia.github.io/mocha/)
* Assertion library: [chai](chaijs.com)
* HTTP assertions: [supertest](https://github.com/visionmedia/supertest)

Mocha should be installed globally, while the other
libraries will be installed locally.

```sh
$ npm install -g mocha
$ npm install --save chai supertest
```

Finally create the test directory.

```sh
$ mkdir test
```

`mocha` command should give an input like this.

```sh
$ mocha

  0 passing (1ms)
```

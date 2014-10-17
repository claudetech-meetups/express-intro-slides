## Restarting the server

You can try to change something in the application,
for example:

```
  res.json({foo: "barbaz"})
```

and to refresh your browser. Nothing will change,
so you need to stop the server, and run `node app.js`
again.

This is not very nice for development, so tools like `nodemon`
are handy.

```sh
$ npm install -g nodemon
```

You now just have to change the command `node` to `nodemon` and
your server will restart automagically.

```sh
$ nodemon app.js
```

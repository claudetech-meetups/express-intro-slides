## Mongo install

We are going to use [MongoDB](http://www.mongodb.org/), a NoSQL document database, to read and write our blog data.

First, we are going to need MongoDB running on our local
machine.

For OS X users:

```sh
$ brew install mongodb
```

This may take a while. When this is done, we are going to
create the directory where data will be stored.

```sh
$ sudo mkdir -p /data/db
$ sudo chown `whoami`:staff /data/db
```

Finally, we can run MongoDB with

```sh
$ mongodb
```

To check if mongo if running properly, we can try to access it with

```sh
$ mongo
```

for other OS, checkout [the documentation](http://docs.mongodb.org/manual/installation/).

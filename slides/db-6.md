## Inserting data with Mongo CLI

We can now access <a href="http://localhost:5000/posts" target="_blank">localhost:5000/posts</a>, we should see `[]`, as there is no data in the database yet.

We are going to insert data with Mongo CLI.

```javascript
$ mongo blog_api
> db.posts.find()
> db.categories.find()
> db.categories.insert({name: "first category", createdAt: ISODate()})
WriteResult({ "nInserted" : 1 })
> db.categories.find()
{ "_id" : ObjectId("54414b4ccc0c014246d7928f"), "name" : "first category", "createdAt" : ISODate("2014-10-17T17:01:00.948Z") }
> db.posts.insert({title: "the title", content: "the content", createdAt: ISODate(), categoryId: db.categories.findOne()._id})
WriteResult({ "nInserted" : 1 })
> db.posts.find()
{ "_id" : ObjectId("54414ba2cc0c014246d79290"), "title" : "the title", "content" : "the content", "createdAt" : ISODate("2014-10-17T17:02:26.267Z"), "categoryId" : ObjectId("54414b4ccc0c014246d7928f") }
```

We now have a category named "first category" and a post belonging to this
category with the title "foobar". When reaccessing the previous page,
we should see the data.

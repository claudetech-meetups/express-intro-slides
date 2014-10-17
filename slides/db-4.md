## Creating models

We are going to create a model for the `Post`.
First, let's create the `models` directory, and
then the file `post.js` with the following content.

```javascript
// models/post.js
var mongoose = require('mongoose');
var postSchema = new mongoose.Schema({
  title: String,
  content: String,
  categoryId: mongoose.Schema.Types.ObjectId,
  createdAt: Date
});
module.exports = mongoose.model('Post', postSchema);
```

Here, we define the schema for the post, with the fields we are
going to use.
With this schema, we then define the model. We do the same for `Category`.

```javascript
// models/categories.js
var mongoose = require('mongoose');
var categorySchema = new mongoose.Schema({
  name: String,
  createdAt: Date
});
module.exports = mongoose.model('Category', categorySchema);
```

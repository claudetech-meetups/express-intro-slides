## Fixing the output

We should now have a result like this

```json
[{"_id":"54414ba2cc0c014246d79290","title":"the title","content":"the content","createdAt":"2014-10-17T17:02:26.267Z","categoryId":"54414b4ccc0c014246d7928f"}]
```

which is good, but as the frontend application uses `id` and not `_id`, we would like to have `id` instead of `_id` in the JSON output. The simplest
thing to use `Schema.options.toJSON`, and to avoid having to do this for
all models, we monkey patch the prototype.

```javascript
// app.js
...
var __options = mongoose.Schema.prototype.defaultOptions;
mongoose.Schema.prototype.defaultOptions = function (options) {
  options = __options.apply(this, arguments);
  options.toJSON = options.toJSON || {
    transform: function (doc, ret, options) {
      ret.id = ret._id;
      delete ret._id;
      return ret;
    }
  };
  return options;
};
mongoose.connect('mongodb://localhost/blog_api');
...
```

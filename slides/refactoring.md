## Improve project layout

We want to write some tests for our API.

First, we are going to change a little the configuration of the project.
We are going to use a different module for configuration.

```javascript
// config.js
module.exports = {
  dev: {
    mongo_url: "mongodb://localhost/blog_api",
    port: 5000
  },
  test: {
    mongo_url: "mongodb://localhost/blog_api_test",
    port: 5000
  },
  production: {
    mongo_url: "mongodb://localhost/blog_api_production",
    port: process.env.PORT || 5000
  }
}
```

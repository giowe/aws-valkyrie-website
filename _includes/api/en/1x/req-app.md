<h3 id='req.app'>req.app</h3>

This property holds a reference to the instance of the AWS Valkyrie application that is using the middleware.

If you follow the pattern in which you create a module that just exports a middleware function
and `require()` it in your main file, then the middleware can access the AWS Valkyrie instance via `req.app`

For example:

```js
//index.js
app.get('/viewdirectory', require('./mymiddleware.js'))
```

```js
//mymiddleware.js
module.exports = function (req, res) {
  res.send('The views directory is ' + req.app.get('views'));
});
```

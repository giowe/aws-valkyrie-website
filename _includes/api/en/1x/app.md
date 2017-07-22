<h2 id="app">Application</h2>

The `app` object conventionally denotes the AWS Valkyrie application.
Create it by calling the top-level `aws-valkyrie()` function exported by the AWS Valkyrie module:

```js
const Valkyrie = require('aws-valkyrie');
const app = new Valkyrie();

app.get('/', (req, res) => {
  res.send('hello world');
});

exports.handler = (...args) => app.listen(...args);
```

The `app` object has methods for

* Routing HTTP requests; see for example, [app.METHOD](#app.METHOD) and [app.param](#app.param).
* Configuring middleware; see [app.route](#app.route).
* Rendering HTML views; see [app.render](#app.render).
* Registering a template engine; see [app.engine](#app.engine).

It also has settings (properties) that affect how the application behaves;
for more information, see [Application settings](#app.settings.table).

<div class="doc-box doc-info" markdown="1">
The AWS Valkyrie application object can be referred from the [request object](#req) and the [response object](#res) as `req.app`, and `res.app`, respectively.
</div>

<h3 id='app.properties'>Properties</h3>

<section markdown="1">
  {% include api/en/1x/app-locals.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-mountpath.md %}
</section>

<h3 id='app.events'>Events</h3>

<section markdown="1">
  {% include api/en/1x/app-onmount.md %}
</section>

<h3 id='app.methods'>Methods</h3>

<section markdown="1">
  {% include api/en/1x/app-all.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-delete-method.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-disable.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-disabled.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-enable.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-enabled.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-engine.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-get.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-get-method.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-listen.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-METHOD.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-param.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-path.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-post-method.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-put-method.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-render.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-route.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-set.md %}
</section>

<section markdown="1">
  {% include api/en/1x/app-use.md %}
</section>

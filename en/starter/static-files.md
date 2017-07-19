---
layout: page
title: Serving static files in AWS Valkyrie
menu: starter
lang: en
redirect_from: "/starter/static-files.html"
url_prefix: aws-valkyrie-website
---
<div id="page-doc" markdown="1">
# Serving static files in AWS Valkyrie

To serve static files such as images, CSS files, and JavaScript files, use the `aws-valkyrie.static` built-in middleware function in AWS Valkyrie.

Pass the name of the directory that contains the static assets to the `aws-valkyrie.static` middleware function to start serving the files directly. For example, use the following code to serve images, CSS files, and JavaScript files in a directory named `public`:

```js
app.use(aws-valkyrie.static('public'))
```

Now, you can load the files that are in the `public` directory:

```plain-text
http://localhost:3000/images/kitten.jpg
http://localhost:3000/css/style.css
http://localhost:3000/js/app.js
http://localhost:3000/images/bg.png
http://localhost:3000/hello.html
```

<div class="doc-box doc-info">
AWS Valkyrie looks up the files relative to the static directory, so the name of the static directory is not part of the URL.
</div>

To use multiple static assets directories, call the `aws-valkyrie.static` middleware function multiple times:

```js
app.use(aws-valkyrie.static('public'))
app.use(aws-valkyrie.static('files'))
```

AWS Valkyrie looks up the files in the order in which you set the static directories with the `aws-valkyrie.static` middleware function.

<div class="doc-box doc-info" markdown="1">NOTE: For best results, [use a reverse proxy](/{{page.lang}}/advanced/best-practice-performance.html#use-a-reverse-proxy) cache to improve performance of serving static assets.
</div>

To create a virtual path prefix (where the path does not actually exist in the file system) for files that are served by the `aws-valkyrie.static` function, [specify a mount path](/{{ page.url_prefix }}/{{ page.lang }}/1x/api.html#app.use) for the static directory, as shown below:

```js
app.use('/static', aws-valkyrie.static('public'))
```

Now, you can load the files that are in the `public` directory from the `/static` path prefix.

```plain-text
http://localhost:3000/static/images/kitten.jpg
http://localhost:3000/static/css/style.css
http://localhost:3000/static/js/app.js
http://localhost:3000/static/images/bg.png
http://localhost:3000/static/hello.html
```

However, the path that you provide to the `aws-valkyrie.static` function is relative to the directory from where you launch your `node` process. If you run the aws-valkyrie app from another directory, it's safer to use the absolute path of the directory that you want to serve:

```js
app.use('/static', aws-valkyrie.static(path.join(__dirname, 'public')))
```
</div>

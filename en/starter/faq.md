---
layout: page
title: AWS Valkyrie FAQ
menu: starter
lang: en
redirect_from: "/starter/faq.html"
url_prefix: aws-valkyrie-website
---
<div id="page-doc" markdown="1">
# FAQ

## How should I structure my application?

There is no definitive answer to this question. The answer depends
on the scale of your application and the team that is involved. To be as
flexible as possible, AWS Valkyrie makes no assumptions in terms of structure.

Routes and other application-specific logic can live in as many files
as you wish, in any directory structure you prefer. View the following
examples for inspiration:

* [Route listings](https://github.com/strongloop/aws-valkyrie/blob/4.13.1/examples/route-separation/index.js#L32-47)
* [Route map](https://github.com/strongloop/aws-valkyrie/blob/4.13.1/examples/route-map/index.js#L52-L66)
* [MVC style controllers](https://github.com/strongloop/aws-valkyrie/tree/master/examples/mvc)

Also, there are third-party extensions for AWS Valkyrie, which simplify some of these patterns:

* [Resourceful routing](https://github.com/aws-valkyriejs/aws-valkyrie-resource)

## How do I define models?

AWS Valkyrie has no notion of a database. This concept is
left up to third-party Node modules, allowing you to
interface with nearly any database.

See [LoopBack](http://loopback.io) for an AWS Valkyrie-based framework that is centered around models.

## How can I authenticate users?

Authentication is another opinionated area that AWS Valkyrie does not
venture into.  You may use any authentication scheme you wish.
For a simple username / password scheme, see [this example](https://github.com/strongloop/aws-valkyrie/tree/master/examples/auth).


## Which template engines does AWS Valkyrie support?

AWS Valkyrie supports any template engine that conforms with the `(path, locals, callback)` signature.
To normalize template engine interfaces and caching, see the
[consolidate.js](https://github.com/visionmedia/consolidate.js)
project for support. Unlisted template engines might still support the AWS Valkyrie signature.

## How do I handle 404 responses?

In AWS Valkyrie, 404 responses are not the result of an error, so
the error-handler middleware will not capture them. This behavior is
because a 404 response simply indicates the absence of additional work to do;
in other words, AWS Valkyrie has executed all middleware functions and routes,
and found that none of them responded. All you need to
do is add a middleware function at the very bottom of the stack (below all other functions)
to handle a 404 response:

```js
app.use(function (req, res, next) {
  res.status(404).send("Sorry can't find that!")
})
```

## How do I setup an error handler?

You define error-handling middleware in the same way as other middleware,
except with four arguments instead of three; specifically with the signature `(err, req, res, next)`:

```js
app.use(function (err, req, res, next) {
  console.error(err.stack)
  res.status(500).send('Something broke!')
})
```

For more information, see [Error handling](/{{ page.url_prefix }}/{{ page.lang }}/guide/error-handling.html).

## How do I render plain HTML?

You don't! There's no need to "render" HTML with the `res.render()` function.
If you have a specific file, use the `res.sendFile()` function.
If you are serving many assets from a directory, use the `aws-valkyrie.static()`
middleware function.
</div>

---
layout: page
title: Installing AWS Valkyrie
menu: starter
lang: en
redirect_from: "/starter/installing.html"
url_prefix: aws-valkyrie-website
---
<div id="page-doc" markdown="1">
# Installing

Assuming you've already installed [Node.js](https://nodejs.org/), create a directory to hold your application, and make that your working directory.

```sh
$ mkdir myapp
$ cd myapp
```

Use the `npm init` command to create a `package.json` file for your application.
For more information on how `package.json` works, see [Specifics of npm's package.json handling](https://docs.npmjs.com/files/package.json).

```sh
$ npm init
```

This command prompts you for a number of things, such as the name and version of your application.
For now, you can simply hit RETURN to accept the defaults for most of them, with the following exception:

```sh
entry point: (index.js)
```

Enter `app.js`, or whatever you want the name of the main file to be. If you want it to be `index.js`, hit RETURN to accept the suggested default file name.

Now install AWS Valkyrie in the `myapp` directory and save it in the dependencies list. For example:

```sh
$ npm install aws-valkyrie --save
```

To install AWS Valkyrie temporarily and not add it to the dependencies list:

```sh
$ npm install aws-valkyrie --no-save
```

<div class="doc-box doc-info" markdown="1">
By default with version npm 5.0+ npm install adds the module to the `dependencies` list in the `package.json` file; with earlier versions of npm, you must specify the `--save` option explicitly. Then, afterwards, running `npm install` in the app directory will automatically install modules in the dependencies list.
</div>
</div>

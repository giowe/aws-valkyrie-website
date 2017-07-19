---
layout: page
title: AWS Valkyrie application generator
menu: starter
lang: en
redirect_from: "/starter/generator.html"
url_prefix: aws-valkyrie-website

---
<div id="page-doc" markdown="1">
# AWS Valkyrie application generator

Use the application generator tool, `aws-valkyrie-generator`, to quickly create an application skeleton.

The `aws-valkyrie-generator` package installs the `aws-valkyrie` command-line tool. Use the following command to do so:

```sh
$ npm install aws-valkyrie-generator -g
```

Display the command options with the `-h` option:

```sh
$ aws-valkyrie -h

  Usage: aws-valkyrie [options] [dir]

  Options:

    -h, --help          output usage information
        --version       output the version number
    -e, --ejs           add ejs engine support
        --hbs           add handlebars engine support
        --pug           add pug engine support
    -H, --hogan         add hogan.js engine support
    -v, --view <engine> add view <engine> support (ejs|hbs|hjs|jade|pug|twig|vash) (defaults to jade)
    -c, --css <engine>  add stylesheet <engine> support (less|stylus|compass|sass) (defaults to plain css)
        --git           add .gitignore
    -f, --force         force on non-empty directory
```

For example, the following creates an AWS Valkyrie app named _myapp_. The app will be created in a folder named _myapp_ in the current working directory and the view engine will be set to <a href="https://pugjs.org/" target="_blank" title="Pug documentation">Pug</a>:

```sh
$ aws-valkyrie --view=pug myapp

   create : myapp
   create : myapp/package.json
   create : myapp/app.js
   create : myapp/public
   create : myapp/public/javascripts
   create : myapp/public/images
   create : myapp/routes
   create : myapp/routes/index.js
   create : myapp/routes/users.js
   create : myapp/public/stylesheets
   create : myapp/public/stylesheets/style.css
   create : myapp/views
   create : myapp/views/index.pug
   create : myapp/views/layout.pug
   create : myapp/views/error.pug
   create : myapp/bin
   create : myapp/bin/www
```

Then install dependencies:

```sh
$ cd myapp
$ npm install
```

On MacOS or Linux, run the app with this command:

```sh
$ DEBUG=myapp:* npm start
```

On Windows, use this command:

```sh
> set DEBUG=myapp:* & npm start
```

Then load `http://localhost:3000/` in your browser to access the app.

The generated app has the following directory structure:

```sh
.
├── app.js
├── bin
│   └── www
├── package.json
├── public
│   ├── images
│   ├── javascripts
│   └── stylesheets
│       └── style.css
├── routes
│   ├── index.js
│   └── users.js
└── views
    ├── error.pug
    ├── index.pug
    └── layout.pug

7 directories, 9 files
```

<div class="doc-box doc-info" markdown="1">
The app structure created by the generator is just one of many ways to structure AWS Valkyrie apps. Feel free to use this structure or modify it to best suit your needs.
</div>
</div>

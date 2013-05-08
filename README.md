# grunt-buster [![Build Status](https://travis-ci.org/busterjs/grunt-buster.png?branch=master)](https://travis-ci.org/busterjs/grunt-buster)

> [Grunt](http://gruntjs.com/) task for running
> [Buster.JS](http://busterjs.org/) tests in [Node.js](http://nodejs.org/) or
> headless in [PhantomJS](http://phantomjs.org/)


## Getting started

This plugin requires Grunt `~0.4.0`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out
the [Getting started](http://gruntjs.com/getting-started) guide, as it explains
how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as
install and use Grunt plugins. Once you're familiar with that process, you may
install this plugin with this command:

``` shell
npm install grunt-buster --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile
with this line of JavaScript:

``` js
grunt.loadNpmTasks('grunt-buster');
```

Then, you must install Buster.JS globally:

``` shell
sudo npm install -g buster
```

### Browser tests

If you want to run tests for the browser environment, you also need to [install
PhantomJS](http://phantomjs.org/) globally:

``` shell
sudo npm install -g phantomjs
```


## The "buster" task

### Overview

In your project's Gruntfile, add a section named `buster` to the data object
passed into `grunt.initConfig()`:

``` js
buster: {
  test: {
    config: 'path/to/my/buster.js'
  },
  server: {
    port: 1111
  }
}
```

### Options

This is entirely optional, as grunt-buster will use default values if none is
specified.

#### test

An object with options passed as command line arguments to `buster test`. For
available options for `buster test` run:

``` shell
buster test --help
```

#### server

An object with options passed as command line arguments to `buster server`. For
available options for `buster server` run:

``` shell
buster server --help
```

#### options.growl

Growl support is optional. If you would like to use it follow the instructions
on [how to install node-growl](https://github.com/visionmedia/node-growl), then
enable Growl notifications in the `buster` task in your Gruntfile.

Example:

``` js
buster: {
  options: {
    growl: true
  }
}
```

You should now get notifications whenever your test suite passes or fails.


## Development

If you wish to contribute, please ensure a green test suite.

Install development dependencies:

```
npm install
```

Running the test suite:

```
npm test
```

Starting a watch loop listening to file changes and running the test suite:

```
npm start
```


## Release history

#### v0.2.0 (UNRELEASED)

* Updated project URLs after move to busterjs organization on GitHub
* Require Node.js >= 0.8.0
* Fix `path.existsSync` deprecation warning
* Declare a peer dependency on Grunt ~0.4.0
* Made Growl notifications optional. You must now install the `growl` package
  from npm and set `options.growl` to `true` to get notifications.

#### v0.1.2

* Looks for buster.js in test/ and spec/ in addition to the root folder
* Fixed corrupt error.png and ok.png (Thanks to [Paweł Maciejewski](https://github.com/fragphace))
* Removed console non-printable characters from growl text message (Thanks to
  [Paweł Maciejewski](https://github.com/fragphace))

#### v0.1.1

* Ensure that tests is not run until PhantomJS finished starting (thanks to
  [Harrison](https://github.com/Harrison))

#### v0.1.0

* Initial release

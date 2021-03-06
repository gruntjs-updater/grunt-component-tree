# grunt-component-tree

> Makes it easier to access components in large Node projects without having to call require by nesting components/modules

## Getting Started
This plugin requires Grunt `~0.4.5`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-component-tree --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-component-tree');
```

## The "component_tree" task

### Overview
In your project's Gruntfile, add a section named `component_tree` to the data object passed into `grunt.initConfig()`.

Inside your project's directory of components all files starting with a capital letter within a folder will be treated as a module and added to an object, which is exported by the index.js file. If a file has the same name as the folder it is directly contained by, then this module will be used as an object and other objects will be added to it.


#### Configuration
An index.js file will be placed in each directory starting with a capital letter within the directory specified using cwd.

```js
grunt.initConfig({
  component_tree: {
    cwd: 'src'
  },
});
```

#### Usage
```
src
|--A
|  |--A.js
|  |--X.js
|  |--index.js
```

```js
var A = require('./A');

var a = new A();

a.x = new A.X()

a.x instanceof A.X; // true

```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History
_(Nothing yet)_

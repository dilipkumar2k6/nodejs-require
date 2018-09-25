# module loading concepts
There are two main modules
1. require
2. module
Note: Both are global function.

# How require works?
It goes through following phases
1. resolving >> To find the absolute file path of the module.
2. Loading >> Load the content of the file.
3. Wrapping >> Gives a private scope to every module.
4. Evaluating >> VM parsing/loading the code.
5. Caching >> Load it once and re-use.

# module object
Following is sample output on module
```
Module {
  id: '.',
  exports: {},
  parent: null,
  filename: '/Users/dilipkumar/Dilip/NodeCertification/nodejs-require/module.js',
  loaded: false,
  children: [],
  paths:
   [ '/Users/dilipkumar/Dilip/NodeCertification/nodejs-require/node_modules',
     '/Users/dilipkumar/Dilip/NodeCertification/node_modules',
     '/Users/dilipkumar/Dilip/node_modules',
     '/Users/dilipkumar/node_modules',
     '/Users/node_modules',
     '/node_modules' ] }

```

Node module has one to one relationship with the file system. Node try to find module
first in the current node_modules folder, then to parent node_modules folder and keep going up till root.

It also look for following locations
```
$HOME/.node_modules
$HOME/.node_libraries
$PREFIX/lib/node
```
Note: Core node.js module resolve immediately.

Following are few more points
- require.resolve('module') is used to check the module, it doesn't load
- module.exports is used to export module
- module.loaded tells if module was loaded or not
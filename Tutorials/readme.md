# Browserify  

http://browserify.org/  

https://github.com/xgqfrms-GitHub/node-browserify/blob/master/Tutorials/readme.md  



Browserify lets you require('modules') in the browser by bundling up all of your dependencies.  

Browserify 让你在浏览器中要求('模块'),通过捆绑所有的依赖关系。


## install  

```sh
$ npm install -g browserify

``` 

## demo  


1. main.js  

```codes
var unique = require('uniq');

var data = [1, 2, 2, 3, 4, 5, 5, 5, 6];

console.log(unique(data));
``` 


2. https://www.npmjs.com/package/uniq  

```sh
$ npm install uniq

$ browserify main.js -o bundle.js
``` 

3. bundle.js  

```codes
(function e(t,n,r){function s(o,u){if(!n[o]){if(!t[o]){var a=typeof require=="function"&&require;if(!u&&a)return a(o,!0);if(i)return i(o,!0);var f=new Error("Cannot find module '"+o+"'");throw f.code="MODULE_NOT_FOUND",f}var l=n[o]={exports:{}};t[o][0].call(l.exports,function(e){var n=t[o][1][e];return s(n?n:e)},l,l.exports,e,t,n,r)}return n[o].exports}var i=typeof require=="function"&&require;for(var o=0;o<r.length;o++)s(r[o]);return s})({1:[function(require,module,exports){
var unique = require('uniq');

var data = [1, 2, 2, 3, 4, 5, 5, 5, 6];

console.log(unique(data));


},{"uniq":2}],2:[function(require,module,exports){
"use strict"

function unique_pred(list, compare) {
  var ptr = 1
    , len = list.length
    , a=list[0], b=list[0]
  for(var i=1; i<len; ++i) {
    b = a
    a = list[i]
    if(compare(a, b)) {
      if(i === ptr) {
        ptr++
        continue
      }
      list[ptr++] = a
    }
  }
  list.length = ptr
  return list
}

function unique_eq(list) {
  var ptr = 1
    , len = list.length
    , a=list[0], b = list[0]
  for(var i=1; i<len; ++i, b=a) {
    b = a
    a = list[i]
    if(a !== b) {
      if(i === ptr) {
        ptr++
        continue
      }
      list[ptr++] = a
    }
  }
  list.length = ptr
  return list
}

function unique(list, compare, sorted) {
  if(list.length === 0) {
    return list
  }
  if(compare) {
    if(!sorted) {
      list.sort(compare)
    }
    return unique_pred(list, compare)
  }
  if(!sorted) {
    list.sort()
  }
  return unique_eq(list)
}

module.exports = unique

},{}]},{},[1]);


``` 

4. using in html 

```codes
<script src="bundle.js"></script>
``` 







***
***

# webpack  bundler ???

```codes
# webpack 2.x  

https://webpack.js.org/concepts/  
https://github.com/ufo-github/webpack.js.org/tree/develop/Tutorials/readme.md  

webpack是现代JavaScript应用程序的模块捆绑器。

javascript及其相关资源文件的打包器，将许多模块封装成几个捆绑资源。
代码拆分允许根据需要加载应用程序的部件。
通过“装载器”，模块可以是CommonJs，AMD，ES6模块，CSS，图像，JSON，Coffeescript，LESS，...和您的自定义内容

# webpack 1.x  

https://github.com/ufo-github/webpack/blob/master/Tutorials/readme.md  
webpack 接受具有依赖性的模块，并生成表示这些模块的静态资产。

## webpack-how-to  
https://github.com/xgqfrms-GitHub/webpack/blob/master/README.md  

``` 


***
***



# Abstract syntax tree

https://en.wikipedia.org/wiki/Abstract_syntax_tree


![svg](https://upload.wikimedia.org/wikipedia/commons/c/c7/Abstract_syntax_tree_for_Euclidean_algorithm.svg)


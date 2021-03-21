---
title: include 和require的区别
commentable: flase
Edit: 2019-04-17
mathjax: true
mermaid: true
tags: 
categories: 
description: require 和include都是引入文件，有什么区别呢？
---

# include 和require的区别

### 前言

require 和include都是引入文件，有什么区别呢？

### require

require 这个函数通常放在 PHP 程序的最前面，PHP 程序在执行前，就会先读入 require 所指定引入的文件，使它变成 PHP 程序网页的一部份。常用的函数，亦可以这个方法将它引入网页中。

### include

include 这个函数一般是放在流程控制的处理部分中。PHP 程序网页在读到 include 的文件时，才将它读进来。可以把程序执行时的流程简单化。

### 区别

- Php在遇到include 时就解释一次，如果页面中出现 10次include ，php就解释 10次，而php 遇到require时只解释一次，即使页面出现多次require也只解释一次，因此require的执行表率比 include高。
- Php使用require 包含文件时将被包含的文件当成当前文件的一个组成部分，如果被包含的文件中有语法错误或者被包含的文件不存在，则 php脚本将不再执行，并提示错误。

- Php使用include 包含文件时相当于指定了这个文件的路径，当被包含的文件有语法错误或者被包含的文件不存在时给出警告，不影响本身脚本的运行。

- Include在包含文件时可以判断文件是否包含，而 require则不管任何情况都包含进来。

- Require的效率比require_once的效率更高，因为require_once在包含文件时要进行判断文件是否已经被包含。
  
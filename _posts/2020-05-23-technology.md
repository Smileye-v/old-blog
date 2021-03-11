---
title: beautyEye输入框中文输入法白屏bug
commentable: flase
Edit: 2020-05-23
mathjax: true
mermaid: true
tags: java beautyEye
categories: technology
description: 在使用Java Swing编写程序时引用beautyEye以修改样式，但在使用输入框时，输入中文窗口就出现白屏。
---

在使用Java Swing编写程序时引用beautyEye以修改样式，但在使用输入框时，输入中文窗口就出现白屏。

<img src="https://img-blog.csdnimg.cn/20200523010908639.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L251bGxfY2F0,size_16,color_FFFFFF,t_70" align="left">
<div style="clear: both;"></div>

<img src="https://img-blog.csdnimg.cn/20200523011539732.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L251bGxfY2F0,size_16,color_FFFFFF,t_70" align="left">
<div style="clear: both;"></div>

# 解决方法：

在初始化前加入System.setProperty(“sun.java2d.noddraw”, “true”);

```js
public static void main(String[] args) {
		
		try {
			System.setProperty("sun.java2d.noddraw", "true");
			org.jb2011.lnf.beautyeye.BeautyEyeLNFHelper.launchBeautyEyeLNF();
			
		} catch (Exception e) {
			// TODO exception
		}
		
	}
```
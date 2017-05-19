---
layout:     post
title:      "OpenCV学习笔记"
subtitle:   "集成问题、使用教程"
date:       2017-05-19
author:     "Tun"
header-img: "img/Tun-iOS-OpenCV.jpg"
tags:
    - iOS
    - OpenVC
    - C++
---

### 安装OpenCV
* [官网下载](https://sourceforge.net/projects/opencvlibrary/files/opencv-ios/3.2.0/opencv-3.2.0-ios-framework.zip/download)
* [百度云下载](https://baidu.com)

### 下载完成后，直接拖进工程里,然后我们开始编译
可能出现的问题：


1. 'unordered_map' file not found!
![image](https://tuyuwang.github.io/img/OpenCV/Build-0.jpg)
> build Setting -> C++ Standard Libarry -> libc++



2. ![img](https://tuyuwang.github.io/img/OpenCV/Build-1.png)
> ![solve](https://tuyuwang.github.io/img/OpenCV/Build-2.png)

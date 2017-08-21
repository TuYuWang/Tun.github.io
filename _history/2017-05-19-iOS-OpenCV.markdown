---
layout:     post
title:      "OpenCV学习笔记"
subtitle:   "OpenCV是一个开源跨平台的的计算机视觉和机器学习库，可以用来做图片视频的处理、图形识别、机器学习等应用。"
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
> 
build Setting -> C++ Standard Libarry -> libc++



2. before any Aplle headers 
![img](https://tuyuwang.github.io/img/OpenCV/Build-1.png)
> 确保openvc文件在最前面导入
![solve](https://tuyuwang.github.io/img/OpenCV/Build-2.png)


3. xxx.hpp header must be Compoled as C++
![img](https://tuyuwang.github.io/img/OpenCV/Build-3.png)
> 所有引用了C++的文件,其.m要改成.mm，.h保持不变

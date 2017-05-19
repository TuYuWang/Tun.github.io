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
1. 'unordered_map' file not found! ![image](img/OpenCV/Build-0.jpg)

解决: build Setting -> C++ Standard Libarry -> libc++
2. Detected Apple 'NO' macro definition, it can cause build conflicts. Please, include this header before any Apple headers.

解决: #import <opencv2/opencv.hpp>必须写在所有类导入之前

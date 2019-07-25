# Altizure JavaScript 3D SDK

这是一个以 JavaScript 为开发语言的 SDK。提供了丰富的三维浏览和编辑的功能。SDK 的主要目的是：

* 简化加载和渲染海量三维数据的开发工作
* 简化各种数据源的数据在实景三维底图上的整合和高效显示
* 简化实景三维数据和行业应用的开发工作

使用 Altizure JavaScript 3D SDK 并结合 Electron 、 React Native 等混合开发的工具具有大量实用功能，而开发者只需掌握网页编程所需的 JavaScript 和 HTML 就可以轻松开发出高质量的实景三维桌面和移动应用，助力您的商业应用。

## 1. 教程

为方便大家快速上手，本文档将持续为各位用户编写相关 SDK 功能的使用教程。

本使用教程配合[范例代码](https://github.com/altizure/sdk.examples/)和 [3D SDK 文档](https://docs.altizure.com/zh-hans/docs/user_docs/web/) 食用更佳。 

## 2. 范例

#### 2.1 概念释义

我们简单解释一下出现在范例里的元素的概念

* Sandbox \(沙盒\)： altizure.Sandbox \(沙盒\) 是整个三维应用的核心，它负责管理整个三维场景的数据和绘制。通过对沙盒进行定制和添加数据，可以定制出非常强大的三维应用。这是编写三维应用的主要入口。
* Marker \(标记\)： 包括 OBJMarker，ProjectMarker，CanvasTagMarker 等在内的所有模型和标签都可以被称作 marker，通过将具有不同功能的 marker 组合起来，可以获得具有丰富功能的应用，比如说我们可以在一个模型中添加水流、文字标签、火焰效果等。
* Camera \(相机\)： altizure.Sandbox.camera\(相机\) 即观众以什么视角来观看 marker，Camera 的坐标和方向就是屏幕中心点在 Sandbox 空间中的位置和朝向。

#### 2.2 范例列表

您可以参考 [github.com/altizure/sdk.examples](https://github.com/altizure/sdk.examples/) 的教程把这些范例代码下载下来，在本地建立服务器进行尝试。您只需要对其中的部分函数做些简单修改便可以和您现有的系统进行整合。

您也可以直接访问 [SDK demo](https://altizure.github.io/sdk.examples/examples.sdk.html) 来直接尝试各种范例的效果。

SDK中的控件和接口的使用方法在 [SDK 文档](ref://docs/user_docs/web/) 中有详细的解释。

对范例和使用方法有任何疑问可以在 [issue page](https://github.com/altizure/sdk.examples/issues) 中进行提问和交流。

<!--
#### 2.2 范例列表

* 2.2.1 Altizure 地球基本加载范例
    * [默认地球加载](https://altizure.github.io/sdk.examples/1-1-altizure-earth)
    * [设置地球加载开场动画](https://altizure.github.io/sdk.examples/1-2-open-animation)
    * [设置地球加载图层](https://altizure.github.io/sdk.examples/1-3-render-items)
    * [设置月球为底图](https://altizure.github.io/sdk.examples/1-4-lunar)
    * [改变背景](https://altizure.github.io/sdk.examples/1-5-background)
* 2.2.2 插入 Marker 范例
    * [插入 Altizure 项目](https://altizure.github.io/sdk.examples/2-1-add-project)
        * [设置水面](https://altizure.github.io/sdk.examples/2-1-add-project-water)
    * [插入自定义标签](https://altizure.github.io/sdk.examples/2-2-add-tag)
    * [插入多边形和体块](https://altizure.github.io/sdk.examples/2-3-add-polygon)
    * [插入折线](https://altizure.github.io/sdk.examples/2-4-add-polyline)
    * [插入 obj 模型](https://altizure.github.io/sdk.examples/2-5-add-obj-model)
    * [插入文字标签](https://altizure.github.io/sdk.examples/2-6-add-textTag)
    * [插入带标签折线](https://altizure.github.io/sdk.examples/2-7-add-label-line)
    * [插入圆柱形折线](https://altizure.github.io/sdk.examples/2-8-polycylinder)
    * [插入 canvas 标签](https://altizure.github.io/sdk.examples/2-9-add-canvasTag)
* 2.2.3 交互事件
    * [鼠标事件](https://altizure.github.io/sdk.examples/3-1-mouse-events)
    * [解绑事件](https://altizure.github.io/sdk.examples/3-2-event-off)
* 2.2.4 获取坐标
    * [获取地球表面坐标](https://altizure.github.io/sdk.examples/4-1-earth-pickpoint)
    * [获取模型表面坐标](https://altizure.github.io/sdk.examples/4-2-project-pickpoint)
    * [窗口坐标获取地球坐标](https://altizure.github.io/sdk.examples/4-3-window-to-lnglatalt)
    * [地球经纬度转换窗口坐标](https://altizure.github.io/sdk.examples/4-4-window-from-lnglatalt)
    * [读取高程](https://altizure.github.io/sdk.examples/4-5-lnglat-to-alt)
* 2.2.5 相机操作
    * [相机姿态设置](https://altizure.github.io/sdk.examples/5-1-camera-pose)
    * [相机飞行设置](https://altizure.github.io/sdk.examples/5-2-camera-fly)
    * [设置相机移动限制](https://altizure.github.io/sdk.examples/5-3-camera-range)
    * [控制相机移动](https://altizure.github.io/sdk.examples/5-4-camera-control)
    * [设置相机矩阵](https://altizure.github.io/sdk.examples/5-5-camera-mat)
* 2.2.6 其他
    * [裁剪项目](https://altizure.github.io/sdk.examples/6-1-crop-project)
    * [体积测量](https://altizure.github.io/sdk.examples/6-2-measurement-volume) -->

## 3. 常见问题

可以访问[常见问题](jssdk-faq.md)了解更多常见问题解答。

[演示应用](jssdk-demo.md)页面展示了更加复杂的 Altizure JavaScript 3D SDK 应用范例。

访问[详细文档](ref://docs/user_docs/web/)了解更多细节。

## 4. 了解更多

* [ThreeJS](https://threejs.org/)
* [WebGL](https://www.khronos.org/webgl/)
* [OpenGL](https://www.opengl.org/)
* [Vulkan](https://www.khronos.org/registry/vulkan/)
*  OpenGL 坐标变换详解 [OpenGL Transformation](http://www.songho.ca/opengl/gl_transform.html)

—

该文档最后修改于 {{ file.mtime }}

# Altizure Javascript SDK

这是一个以 Javacript 为开发语言的 SDK。提供了丰富的三维浏览和编辑的功能。SDK 的主要目的是：

* 简化加载和渲染海量三维数据的开发工作
* 简化各种数据源的数据在实景三维底图上的整合和高效显示
* 简化实景三维数据和行业应用的开发工作

使用 Altizure Javascript 3D SDK 并结合 Electron 和 React Native 等混合开发的工具，开发者可以轻松开发出高质量的实景三维桌面和移动应用，助力你的商业应用。

## 1. 快速开始指南

##### 引用 SDK

在网页的 head 部分，引用我们的 SDK。

```html
<!-- 设置编码，确保 utf8 字符的正确显示 -->
<meta charset="utf-8">
<!-- 设置 viewport，确保移动端的正确渲染 -->
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
<!-- 引用sdk -->
<script type="text/javascript" src="https://beta.altizure.com/sdk"></script>
```

其中我们提供两个版本的 sdk 引用链接：

* 最新版：`<script type="text/javascript" src="https://beta.altizure.com/sdk"></script>`
* 稳定版：`<script type="text/javascript" src="https://www.altizure.com/sdk"></script>`

##### 创建三维显示容器

我们的 sdk 会完全接管三维数据的下载和渲染，用户需要创建一个 `div` 指定相关用于渲染的容器的位置和大小。

```html
<body>
  <div id="page-content"></div>
</body>
```

##### 创建三维引擎对象

我们的三维引擎是以最新的 Altizure 地球的引擎作为基础，新建对象时需要把它附着在一个作为显示容器的 `div` 里。

```js
// 创建一个参数配置对象
let options = {
  altizureApi:{
    // 填入您的 app key
    key: 'your-app-key'
  }
}

// 创建地球渲染引擎对象，附着在 page-content 这个 div 上
let earth = new altizure.Earth('page-content', options)
```

其中 `'page-content'` 是上面创建三维显示容器的 `div` 的 id。`options` 用于配置新建的引擎对象，更多参数可以参考下面的范例和详细文档。

##### 小结

所有代码组合起来就是：

```html
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
  <script type="text/javascript" src="https://beta.altizure.com/sdk"></script>
</head>
<body>
  <div id="page-content"></div>
  <script>
    let options = {
      altizureApi:{
        // 填入您的 app key
        key: 'your-app-key'
      }
    }

    let earth = new altizure.Earth('page-content', options)
  </script>
</body>
</html>
```

可以访问[[演示页面](https://altizure.github.io/sdk-demo/1-1-altizure-earth/index.html)](https://altizure.github.io/sdk.examples/1-1-altizure-earth/index.html)观看这段代码的实际效果。

只需要简单几行代码，我们便可以创建出一个可以加载全球实景三维模型的视图。惊不惊喜？激不激动？

接下来我们直接通过范例代码来学习 sdk 的丰富功能。

## 2. 范例

您可以直接访问 [altizure.github.io/sdk.examples/examples.sdk.html](https://altizure.github.io/sdk.examples/examples.sdk.html) 来直接尝试各种范例的效果。

**概念释义**

以下我们简单解释一下出现在范例里的元素的概念

* Sandbox \(沙盒\)： altizure.Sandbox \(沙盒\) 是整个三维应用的核心，它负责管理整个三维场景的数据和绘制。通过对沙盒进行定制和添加数据，可以定制出非常强大的三维应用。这是编写三维应用的主要入口。
* Earth \(地球\)：altizure.Earth \(地球\) 是负责渲染管理 Altizure 地球的核心，通常它是作为沙盒的底图。我们提供丰富的选项来方便您定义这个地球的外观。一般来说，如果创建了 Sandbox 就无需再创建一个 Earth 对象。

您可以参考 [altizure.github.io/sdk.examples](https://altizure.github.io/sdk.examples) 的教程把这范例代码下载下来，在本地建立服务器进行尝试。您只需要对其中的部分函数做些简单修改便可以和您现有的系统进行整合。

对范例和使用方法有任何疑问可以在 [issue page](https://github.com/altizure/sdk.examples/issues) 进行提问和交流。

## 3. 详细文档

Coming soon...

## 4. 了解更多

* [ThreeJS](https://threejs.org/)
* [WebGL](https://www.khronos.org/webgl/)
* [OpenGL](https://www.opengl.org/)
* [Vulkan](https://www.khronos.org/registry/vulkan/)
* 详解 OpenGL 坐标变换 [OpenGL Transformation](http://www.songho.ca/opengl/gl_transform.html)




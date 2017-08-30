# Altizure Javascript SDK

这是一个以 Javacript 为开发语言的 SDK。提供了丰富的三维浏览和编辑的功能。主要为解决以下几个问题而设计：

* 如何简化加载和渲染海量三维数据的开发工作
* 如何把各种数据源的数据在实景三维底图上进行整合和高效显示
* 如何简化实景三维数据和行业应用的开发工作

使用 Altizure Javascript 3D SDK 并结合 Electron 和 React Native 等混合开发的工具，开发者可以轻松开发出高质量的实景三维桌面和移动应用，助力你的商业应用。

## 1. 基本使用方法

##### 引用 SDK

在网页的 head 部分，引用我们的 sdk js 文件。

```
<!— 设置编码，确保 utf8 字符的正确显示 —>
<encoding=“utf8”>
<!— 设置 viewport，确保移动端的正确渲染 —>
<viewport ...>
<!— 引用sdk —>
<script type=“script/javascript” src=“”></script>
```

##### 创建三维显示容器

我们的 sdk 会完全接管三维数据的下载和渲染，用户需要提供一个 `div` 指定相关用于渲染的容器的位置和大小。

```
<div id=“page-content”></id>
```

##### 创建三维引擎对象

我们的三维引擎是以最新的 Altizure 地球的引擎作为基础，新建对象时需要把它附着在一个作为显示容器的 `div` 里。

```
let config = {
  Did: “”,
  Did: “”
}
let earth = altizure.Earth(“page-content”, config)
```

其中 page-content 是上面创建三维显示容器的 div 的 id。config 用于配置新建的引擎对象。

##### 小结

所有代码组合起来就是：

```
```

只需要几行代码，我们便可以创建出一个可以加载全球实景三维模型的视图。惊不惊喜？激不激动？

接下来我们直接通过范例代码来学习 sdk 的丰富功能。

## 2. 范例

Coming soon

## 3. 详细文档

Coming soon

## 4. 了解更多

* [ThreeJS](https://threejs.org/)
* [WebGL](https://www.khronos.org/webgl/)
* [OpenGL](https://www.opengl.org/)
* [Vulkan](https://www.khronos.org/registry/vulkan/)
* 详解 OpenGL 坐标变换 [OpenGL Transforamtion](http://www.songho.ca/opengl/gl_transform.html)

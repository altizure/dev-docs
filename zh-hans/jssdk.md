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

其中我们提供三个版本的 sdk 引用链接：

* 最新版：`<script type="text/javascript" src="https://beta.altizure.com/sdk"></script>`
* 稳定版：`<script type="text/javascript" src="https://www.altizure.com/sdk"></script>`
* 中国版：`<script type="text/javascript" src="https://www.altizure.cn/sdk"></script>`

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

把这段代码保存成一个 html 文件放在一个文件夹如 `<path>\altizure-sdk-tes\earth.html` 中，然后在控制台中键入：

```bash
cd <path>\altizure-sdk-tes\
python -m SimpleHTTPServer
```

再通过浏览器访问 `http://127.0.0.1:8000/earth.html` 就可以加载这个 Altizure 地球了。

你也可以访问[[演示页面](https://altizure.github.io/sdk-demo/1-1-altizure-earth/index.html)](https://altizure.github.io/sdk.examples/1-1-altizure-earth/index.html)观看这段代码的效果。

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

**范例详解**

* Altizure 地球基本加载范例
    * [默认地球加载](https://altizure.github.io/sdk.examples/1-1-altizure-earth)
    * [设置地球加载开场动画](https://altizure.github.io/sdk.examples/1-2-open-animation)
    * [设置地球加载图层](https://altizure.github.io/sdk.examples/1-3-render-items)
    * [设置月球为底图](https://altizure.github.io/sdk.examples/1-4-lunar)
* 插入 Marker 范例
    * [插入 Altizure 项目](https://altizure.github.io/sdk.examples/2-1-add-project)
        * [设置水面](https://altizure.github.io/sdk.examples/2-1-add-project-water)
    * [插入自定义标签](https://altizure.github.io/sdk.examples/2-2-add-tag)
    * [插入多边形和体块](https://altizure.github.io/sdk.examples/2-3-add-polygon)
    * [插入折线](https://altizure.github.io/sdk.examples/2-4-add-polyline)
    * [插入 obj 模型](https://altizure.github.io/sdk.examples/2-5-add-obj-model)
* 交互事件
    * [鼠标事件](https://altizure.github.io/sdk.examples/3-1-mouse-events)
* 获取坐标
    * [获取地球表面坐标](https://altizure.github.io/sdk.examples/4-1-earth-pickpoint)
    * [获取模型表面坐标](https://altizure.github.io/sdk.examples/4-2-project-pickpoint)
* 相机操作
    * [相机姿态设置](https://altizure.github.io/sdk.examples/5-1-camera-pose)
    * [相机飞行设置](https://altizure.github.io/sdk.examples/5-2-camera-fly)
    * [设置相机移动限制](https://altizure.github.io/sdk.examples/5-3-camera-range)

## 3. 常见问题

#### 3.1 使用相关

###### 3.1.1 能否提供测试？

您可以直接访问 [altizure.github.io/sdk.examples/examples.sdk.html](https://altizure.github.io/sdk.examples/examples.sdk.html) 来直接尝试各种范例的效果。把代码仓库 clone 到本地后即可修改其中的代码进行测试。

###### 3.1.2 本地测试时无法访问相关模型？

请检查以下配置是否正确：

* 是否已经启动一个 http 服务器？最方便的方法是参考 [altizure.github.io/sdk.examples/examples.sdk.html](https://altizure.github.io/sdk.examples/examples.sdk.html) 教程中用 python 建立 http 服务器的方法。
* 本地测试请用 `127.0.0.1` 作为地址来访问，而不要使用 `localhost`。

###### 3.1.3 无法访问 sdk script 链接？

如果无法访问 `https://www.altizure.com/sdk` 或 `https://beta.altizure.com/sdk`，请使用中国站点 `https://www.altizure.cn/sdk`。

###### 3.1.4 详细文档在哪儿？

请直接参考范例的代码，里面有详细注释。我们会持续更新相关范例，展示最新功能。

#### 3.2 常见用例

###### 3.2.1 点击模型中某个建筑物，怎么来获取对应的信息，如建筑物的名称？

可以通过鼠标事件获得经纬度，再去相关数据库中查建筑物名称。相关建筑物数据库由开发者自行管理。

###### 3.2.2 能否直接插入 obj 模型？

可以。如果网络下载带宽不高，过大的 obj 文件可能导致下载时间过长。而且因为受限于浏览器的性能，过大的 obj 也会导致浏览器崩溃。我们一般推荐 obj 模型连同纹理文件不要超过 2 MB。

obj 模型需要满足以下要求：

* obj 模型需要由开发者自行找网络空间存储并获取直接访问的 https 链接。
* 其中 obj 对应的 mtl 文件内的纹理路径需要是相对路径。
* obj 只有三角形面。
* obj 模型里没有非2-流形的点和边，并且没有面积为0的面。

###### 3.2.3 如果需要更换一个标签的click事件，应该怎么操作？需要把前一个绑定事件解绑吗？

最好解绑，用 `.off(event, func)`

###### 3.2.4 如何实现分图层显示不同的标签及其他的模型？

可以在打开和关闭图层的时候从图层数据库中读取相关信息，然后动态将相关标签插入到 Sandbox 或者从中删除。如果不想每次开关图层反复插入和删除相关标签，可以用 `marker.visible=true` 或者 `marker.visible=false` 控制每个标签显示与否。

###### 3.2.5 如何实现测量距离？

通过鼠标事件分别获取两次点击的坐标点，然后求两点距离。

###### 3.2.6 如何移动标注，或者绑定 GPS 设备的坐标？

只需要修改标注的坐标即可移动标注。需要开发者通过客户端或者服务器和不同设备通信获取设备的 GPS 坐标，便可直接把该坐标设做相关标注的坐标，便确保标注反映了设备的 GPS 位置。

###### 3.2.7 项目如果没有camera的参数是不是没办法在https://altizure.github.io/sdk.examples/2-1-add-project/这里显示出来

这里的camera参数，是指sandbox初始化的时候填的相机位置。它可以通过sdk得到，参考範例 5.1。camera的参数是以经纬度，高度定义的。经纬度可以从谷歌/百度地图拾取，或者更简单的，从範例 4.1拾取，点击想要的地方，就会显示了。console里有log, 要离地面近一点也能看到文字标签。
（可选）如果您也在使用Altizure API, project那个函数中有存地理位置的参数。在 geoInfo 里的 centerLat, centerLong， 可以分别赋值给 lat, lng。高度你可以自己定义，比如1000(米)。

###### 3.2.8 sandbox 里的 pid 于 project那里的 id 不是同一个东西吗？

是一个东西。pid 是 project id 的简写。 浏览Altizure的url （例如， https://www.altizure.com/project/59fe68cebb619d03c446fe85/model）里面的 59fe68cebb619d03c446fe85 也是pid。

###### 3.2.9 平台支持BIM格式的文件吗？

目前不支持，有指定需要再开发

###### 3.2.10 创建的标签，有没有方法修改position坐标/同一个标签，不销毁重建的情况下，修改其位置/通过鼠标点击地图来设置标签的位置？

marker.setPose (position, orientation, scale)。这里 position: {lng, lat, alt}, orientation: {x, y, z, w}, scale: number。
如果只改position,另外两个可以设undefined

###### 3.2.12 ObjMarker导入的obj文件有什么要求？

如果网络下载带宽不高，过大的 obj 文件可能导致下载时间过长。而且因为受限于浏览器的性能，过大的 obj 也会导致浏览器崩溃。我们一般推荐 obj 模型连同纹理文件不要超过 2 MB。
obj 模型需要满足以下要求：obj 模型需要由开发者自行找网络空间存储并获取直接访问的 https 链接。其中 obj 对应的 mtl 文件内的纹理路径需要是相对路径。obj 只有三角形面。

###### 3.2.12 将obj转成server端的金字塔（LOD）数据，有什么要求？

obj需要符合一些数学规则，才可以做LOD。包括：obj 只有三角形面。obj 模型里没有非2-流形的点和边，并且没有面积为0的面。详情需联系技术人员测试。

## 4. 了解更多

* [ThreeJS](https://threejs.org/)
* [WebGL](https://www.khronos.org/webgl/)
* [OpenGL](https://www.opengl.org/)
* [Vulkan](https://www.khronos.org/registry/vulkan/)
* 详解 OpenGL 坐标变换 [OpenGL Transformation](http://www.songho.ca/opengl/gl_transform.html)

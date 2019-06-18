# Altizure Javascript 3D SDK

Altizure Javascript 3D SDK allows you to integrate rich 3D experience with our realistic 3D models to your business workflow.

* Simplify the loading and rendering of large-scale realistic 3D models.
* Simplify the fusion and rendering data from different sources.
* Simplify the development of integrating realistic 3D models to different business workflows.

Combined with tools like Electron and React Native, you can easily develop high quality 3D applications with realistic models for desktop and mobile apps.

## 1. Quick Start

##### Include SDK

In the `<head>` section of the html page, include our SDK as

```html
<!-- Set the encoding to make sure that utf8 character is shown correctly -->
<meta charset="utf-8">
<!-- Set the viewport to make the page look correct on mobile -->
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
<!-- Include SDK -->
<script type="text/javascript" src="https://beta.altizure.com/sdk"></script>
```

Here we provide three links for our SDK.

* Latest: `<script type="text/javascript" src="https://beta.altizure.com/sdk"></script>`
* Stable: `<script type="text/javascript" src="https://www.altizure.com/sdk"></script>`
* Latest for Mainland China: `<script type="text/javascript" src="https://beta.altizure.cn/sdk"></script>`
* Stable for Mainland China: `<script type="text/javascript" src="https://www.altizure.cn/sdk"></script>`

##### Create a div as a container for 3D rendering

Our SDK will take over the downloading and rendering of realstic 3D models. Developers should create a `div` and attach a sandbox object to it. This div specifies where 3D contents will be rendered.

```html
<body>
  <div id="page-content"></div>
</body>
```

##### Create a sandbox object

We now create a sandbox object and attach it to the div we created to hold this sandbox. Then the sandbox object will render all 3D contents in such a div.

```js
// Create an option for configuring the sandbox
let options = {
  altizureApi:{
    // your app key
    key: 'your-app-key'
  }
}

// Create a sanbox object and attach it to the div page-content.
let sandbox = new altizure.Sandbox('page-content', options)
```

`'page-content'` is the id of `div` where the 3D contents are rendered. `options` is used to configure the sandbox. Please refer to our sample section for more information about how to configure a sandbox.

##### Summary

All codes can be put together as:

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
        // your app key
        key: 'your-app-key'
      }
    }

    let sandbox = new altizure.Sandbox('page-content', options)
  </script>
</body>
</html>
```

Save this code fragment to `<path>/altizure-sdk-test/earth.html`. Then start a http server in your console by typing

```bash
cd <path>/altizure-sdk-test/
python -m SimpleHTTPServer
```

This page can be accessed at `http://127.0.0.1:8000/earth.html` to load Altizure Earth

You can check this [demo](https://altizure.github.io/sdk.examples/1-1-altizure-earth/index.html) on our site to see how it looks.

In the following, you can learn more about our SDK via samples and demos.

## 2. Samples



#### 2.1 Concepts

Here we start with some concepts in our SDK.

* Sandbox: altizure.Sandbox is the core of the 3D engine. It is the entry point of the development and handles all 3D rendering and data management.

#### 2.2 List of Samples

Up-to-date live samples are at [altizure.github.io/sdk.examples/examples.sdk.html](https://altizure.github.io/sdk.examples/examples.sdk.html).

The source code of these samples can be downloaded at [github.com/altizure/sdk.examples](https://github.com/altizure/sdk.examples/). You can easily setup your server and run these samples following the tutorial.

Any questions and bugs, please feel free to write on our [issue page](https://github.com/altizure/sdk.examples/issues).

<!-- #### 2.2 List of Samples

* 2.2.1 Sandbox setting
    * [Default loading](https://altizure.github.io/sdk.examples/1-1-altizure-earth)
    * [Loading animation](https://altizure.github.io/sdk.examples/1-2-open-animation)
    * [Sandbox customization](https://altizure.github.io/sdk.examples/1-3-render-items)
    * [Planet setup](https://altizure.github.io/sdk.examples/1-4-lunar)
    * [Background setting](https://altizure.github.io/sdk.examples/1-5-background)
* 2.2.2 Marker sample
    * [Altizure project](https://altizure.github.io/sdk.examples/2-1-add-project)
        * [Water setting](https://altizure.github.io/sdk.examples/2-1-add-project-water)
    * [Customized tag](https://altizure.github.io/sdk.examples/2-2-add-tag)
    * [Polygon and polyhedron](https://altizure.github.io/sdk.examples/2-3-add-polygon)
    * [Polyline](https://altizure.github.io/sdk.examples/2-4-add-polyline)
    * [OBJ models](https://altizure.github.io/sdk.examples/2-5-add-obj-model)
    * [Text tag](https://altizure.github.io/sdk.examples/2-6-add-textTag)
    * [Polyline with text label](https://altizure.github.io/sdk.examples/2-7-add-label-line)
    * [Cylinder polyline](https://altizure.github.io/sdk.examples/2-8-polycylinder)
    * [Canvas Tag](https://altizure.github.io/sdk.examples/2-9-add-canvasTag)
* 2.2.3 Interaction
    * [Binding mouse event](https://altizure.github.io/sdk.examples/3-1-mouse-events)
    * [Unbinding event](https://altizure.github.io/sdk.examples/3-2-event-off)
* 2.2.4 Get coordinates
    * [Coordinates on earth](https://altizure.github.io/sdk.examples/4-1-earth-pickpoint)
    * [Coordinates on models](https://altizure.github.io/sdk.examples/4-2-project-pickpoint)
    * [Mapping window coordinates to geo coordinates](https://altizure.github.io/sdk.examples/4-3-window-to-lnglatalt)
    * [Mapping geo coordinates to window coordinates](https://altizure.github.io/sdk.examples/4-4-window-from-lnglatalt)
    * [Get altitude given longitude and latitude](https://altizure.github.io/sdk.examples/4-5-lnglat-to-alt)
* 2.2.5 Camera manipulation
    * [Camera pose](https://altizure.github.io/sdk.examples/5-1-camera-pose)
    * [Camera flight animation](https://altizure.github.io/sdk.examples/5-2-camera-fly)
    * [Camera motion constraint](https://altizure.github.io/sdk.examples/5-3-camera-range)
    * [Camera controls](https://altizure.github.io/sdk.examples/5-4-camera-control)
    * [Camera matrix](https://altizure.github.io/sdk.examples/5-5-camera-mat)
* 2.2.6 Others
    * [Cropping models](https://altizure.github.io/sdk.examples/6-1-crop-project)
    * [Volume measurement](https://altizure.github.io/sdk.examples/6-2-measurement-volume) -->

## 3. FAQ

Please check [FAQ](jssdk-faq.md) page for more information and [demo](jssdk-demo.md) page for more sophisticated demos. Please also check the [Reference](ref://docs/user_docs/web/) documents.

## 4. Learn More

* [ThreeJS](https://threejs.org/)
* [WebGL](https://www.khronos.org/webgl/)
* [OpenGL](https://www.opengl.org/)
* [Vulkan](https://www.khronos.org/registry/vulkan/)
* [OpenGL Transformation](http://www.songho.ca/opengl/gl_transform.html)

---

Last modified at {{ file.mtime }}

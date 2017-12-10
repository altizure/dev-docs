# Frequently Asked Questions

## 1 General Questions

#### 1.1 How to start a testflight on Altizure Javascript SDK?

Please follow the guide [altizure.github.io/sdk.examples/examples.sdk.html](https://altizure.github.io/sdk.examples/examples.sdk.html) to test all samples. The source code can be cloned to your local computer for editing and testing.

#### 1.2 The remote model cannot be loaded when I test the samples on my local computer.

Please make sure that you start a local http server and access the sample page via `127.0.0.1` instead of `localhost`

* Check whether a local http server is setup for testing. The simplest way to start a local http server is to use python and follow the guide at [altizure.github.io/sdk.examples/](https://altizure.github.io/sdk.examples/).
* Use `127.0.0.1` instead of `localhost` to access the sample page hosted on your local computer.

#### 1.3 The link of SDK script cannot be accessed.

If `https://www.altizure.com/sdk` and `https://beta.altizure.com/sdk` are not reachable. Please switch to `https://www.altizure.cn/sdk`。

#### 1.4 Where can I find the reference manual?

Please check our samples and demos. They are detailed documented. We are constantly updating the samples and demos to illustrate the latest features.

#### 1.5 How to get the user token?

Please refer to Section `5. how to get user tokens` on [GraphQL API](api.md).

#### 1.6 In which programming language is the 3D rendering engine on Altizure developed?

We use Javascript. The underlying 3D API is WebGL. But we hardly write raw WebGL codes. Most of the features are developed on top of [ThreeJS](https://threejs.org/).

#### 1.7 Can I implement some elements in three.js and insert it to the scene created using Altizure Javascript SDK?

No, at the moment. We did lots of optimization on memory management to enable fast transfer and rendering of large-scale realistic 3D models, so it is not easy to integrate customized three.js objects to altizure scenes. However, we have plan to do so.

#### 1.8 Do I have to learn about WebGL and computer graphics to use Altizure Javascript SDK?

In general, no, we design the SDK for non-computer graphics experts, anyone with the knowledge of Javascript and HTML should be able to use Altizure Javascript SDK to integrate the realistic 3D models to the business workflow. Nevertheless, it is always a plus if you know some basic knowledge on WebGL and computer graphics.

## 2 Common Use Cases

Coming soon

## 3. Learn More

* [List of samples](https://altizure.github.io/sdk.examples/examples.sdk.html)
* [Demos](jssdk-demo.md) illustrate more sophisticated examples.

—

Last modified at {{ file.mtime }}

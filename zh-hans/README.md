# Altizure 开发平台

欢迎使用 Altizure 开发平台！

在Altizure，您可以享受全球领先的自动三维建模服务。从图像到三维模型，一键式建模。您还可以通过我们的线上浏览和应用技术，轻松分享和使用您的模型。Altizure三维建模在为您带来无限乐趣的同时，也引领着行业技术变革。其自主研发的三维建模技术和手机应用，极大简化了图像采集和三维建模的流程，提高了作业效率，并推动了实景三维模型的普及。

然而，正如很多科研产品一样，如何将技术与行业用户的实际需求结合成为一大难点。由于三维相关的编程开发有一定门槛，所以目前市场上符合要求的开发人员较少。此外，实景三维模型通常包含海量数据，如何让这些三维数据快速显示和传输，也非常困难。为解决这些难题，经过团队的不懈努力，我们推出了Altizure开发平台，为用户提供了更多的建模、浏览和编辑 功能，但同时又极大降低了三维平台开发门槛，让定制三维成为可能。

现在，加入Altizure开发平台，您不仅可以使用世界一流的三维建模技术，还可以将这些平台功能与您的业务进行更深入的集成。第三方模型导入并融合、多个Altizure模型的不同组合展示、多样化标注、视点相机运动和位置的控制及坐标读取等各种功能，都可以通过Altizure开发平台实现。

**开发语言和技术路线**
实景三维显示部分的开发语言是 Javascript。底层三维接口使用WebGL。不过，对于开发平台绝大部分功能的开发，程序员无需懂得WebGL。
数据查询API 接口的规范为GraphQL，使用标准的HTTP Post Request 进行网络通信，使用jQuery 或者Request 等标准的Javascript 开发包即可调用。
开发者只需熟悉javascript 和html 网页编程，即可在平台上进行开发，有效降低行业应用开发的成本。

**支持平台**
支持主流浏览器：Safari, 谷歌浏览器，火狐浏览器，Webkit 内核浏览器，IE 11, IE Edge。
支持平台：任何支持 webview 网页渲染的平台客户端均可使用我们的开发平台进行集成。这包括Windows，Android，iOS，macOS 和Linux。
结合React-native 或 Electron 即可轻松开发高质量的实景三维的手机应用和桌面应用。

让我们开始实景三维世界的探险吧，释放三维数据的无限可能。


* [基本概念](concepts.md)
* [开发者账号申请](dev-account.md)
* [GraphGL API](api.md)
  * [三维重建](api-reconstruction.md)
  * [上传图像](upload.md)
  * [API 文档](https://api.altizure.cn/graphql)
  * [API 更新日志](api-changelog.md)
* [Javascript SDK](jssdk.md)
  * [演示应用](jssdk-demo.md)
  * [常见问题](jssdk-faq.md)
  * [SDK 文档](ref://docs/user_docs/web/)
  * [SDK 更新日志](jssdk-changelog.md)


更多了解 Altizure 欢迎访问：

* 探索 Altizure 的三维世界：[altizure.cn/explore](https://altizure.cn/explore)
* 关注微信公众号：altizure_info
* 关注官方博客：[blog.altizure.cn](https://blog.altizure.cn)
* 离线文档：[pdf](https://altizure.github.io/dev-docs-site/download/altizure-dev-docs_zh-hans.pdf), [epub](https://altizure.github.io/dev-docs-site/download/altizure-dev-docs_zh-hans.epub)


联系我们 [support@altizure.com](mailto:support@altizure.com)

---

该文档最后修改于 {{ file.mtime }}

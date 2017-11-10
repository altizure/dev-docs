# Altizure JavaScript SDK 演示应用

这里我们会演示如何用 Altizure Javascript SDK 解决一些实际应用场景的问题，让 Altizure 的实景模型可以更好地结合到你的商业场景重，发挥实景三维模型的无穷潜力。

您对这些演示有任何问题都欢迎到 [issue page](https://github.com/altizure/experimental-demo/issues) 留言，我们会尽力解答。

# 2. 演示应用

#### 2.1 时间轴

时间轴可以非常直观地展示一个场景按照时间的变化。这是工程进度管理等任何与时间相关的应用都必不可少的工具。下面我们就通过几个应用演示几种可视化时间轴的方法。

* 2.1.1 格状平铺时间轴 [在线演示链接](https://altizure.github.io/experimental-demo/timeline.html)。范例里对一个工地的施工过程超过20个不同时间点的三维模型进行了格状的平铺展示。每个模型带有相关的时间文字标签。
* 2.1.2 滑动条时间轴 [在线演示链接](https://altizure.github.io/experimental-demo/timeline-slider.html)。范例里通过一个滑动条让用户可以任意选取一个工地的施工过程一个时间点的三维模型进行浏览和检视。用户还可以按时间先后循序播放这个工地不同时间段的施工状况。范例里也提供了一个自动环绕飞行的功能，方便用户在展示时自动环绕兴趣点循环播放。

# 3. 如何获取这些演示的代码

这些演示应用都是开源的，您可以通过以下简单的命令把代码复制到您的电脑查看并运行。

```bash
git clone https://github.com/altizure/experimental-demo.git
cd experimental-demo
python -m SimpleHTTPServer
```

打开您的浏览器，访问 `http://127.0.0.1:8000/` 便可运行和查看这些演示应用。

# 4. 了解更多

* [Altizure Javascript SDK](altizure.github.io/dev-docs-site)
* [Altizure Javascript SDK 常见问题](jssdk-faq.md)
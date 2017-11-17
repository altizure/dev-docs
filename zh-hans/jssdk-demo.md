# Altizure JavaScript SDK 演示应用

这里我们会演示如何用 Altizure Javascript SDK 解决一些实际应用场景的问题，让 Altizure 的实景模型可以更好地结合到你的商业场景重，发挥实景三维模型的无穷潜力。

您对这些演示有任何问题都欢迎到 [issue page](https://github.com/altizure/experimental-demo/issues) 留言，我们会尽力解答。

# 1. 时间轴

时间轴可以非常直观地展示一个场景按照时间的变化。这是工程进度管理等任何与时间相关的应用都必不可少的工具。下面我们就通过几个应用演示几种可视化时间轴的方法。

#### 1.1 格状平铺时间轴

* 演示链接：[altizure.github.io/experimental-demo/timeline.html](https://altizure.github.io/experimental-demo/timeline.html)
* 演示重点：多个 Altizure 模型加载，文字标签设置，模型位置调整
* 演示简介：范例里对一个工地的施工过程超过20个不同时间点的三维模型进行了格状的平铺展示。每个模型带有相关的时间文字标签。

#### 1.2 滑动条时间轴

* 演示链接：[altizure.github.io/experimental-demo/timeline-slider.html](https://altizure.github.io/experimental-demo/timeline-slider.html)
* 演示重点：模型可见性修改，实景三维内容与 html 界面交互，相机环绕动画，模型动态加载和销毁
* 演示简介：范例里通过一个滑动条让用户可以任意选取一个工地的施工过程一个时间点的三维模型进行浏览和检视。用户还可以按时间先后循序播放这个工地不同时间段的施工状况。范例里也提供了一个自动环绕飞行的功能，方便用户在展示时自动环绕兴趣点循环播放。

# 2. 传感器

现代的手持设备里有着各种各样的传感器，测量用户的位置、设备姿态、运动速度等等。这个章节的演示会展示如何结合这些传感器信息让你的三维模型更加具有互动性。

#### 2.1 GPS 轨迹记录

* 演示链接：[altizure.github.io/experimental-demo/gps-tracker.html](https://altizure.github.io/experimental-demo/gps-tracker.html)
* 演示重点：图片标签加载，标签位置移动，相机跟随动画，地理坐标与屏幕坐标转换，Canvas 二维元素与实景三维元素结合，获取模型表面高程。
* 演示简介：该演示推荐用手机打开。在演示中，你可以打开轨迹记录，这样你的位置就会以演示中的模型的中心点为基准点，实时以一个 Altizure 图标的形式显示在实景三维模型中。同时您的移动轨迹也会用折线显示出来。移动轨迹的折线的渲染模式可以在三维渲染或者 canvas 二维渲染模式之间切换。您还可以打开相机跟踪模式，让相机在您移动的过程中使用跟随你移动。

# 3. 性能测试

* 演示链接：[altizure.github.io/experimental-demo/performance-test.html](https://altizure.github.io/experimental-demo/performance-test.html)
* 演示重点：文字标签加载和删除，测试三维渲染性能，获取模型表面高程
* 演示简介：演示默认加载 1000 个文字标签。可以通过修改标签数目，并点击 `Generate` 生成不同数目的标签。可以同时显示的标签数目越多，说明您的电脑的渲染能力越强。


# 4. 如何获取这些演示的代码

这些演示应用都是开源的，您可以通过以下的命令把代码复制到您的电脑查看并运行。

```bash
git clone https://github.com/altizure/experimental-demo.git
cd experimental-demo
python -m SimpleHTTPServer
```

打开您的浏览器，访问 `http://127.0.0.1:8000/` 便可运行和查看这些演示应用。

# 5. 了解更多

* [Altizure Javascript SDK](jssdk.md)
* [Altizure Javascript SDK 常见问题](jssdk-faq.md)

—

该文档最后修改于 {{ file.mtime }}

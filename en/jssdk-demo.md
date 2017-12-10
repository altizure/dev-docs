# Altizure JavaScript SDK Demo

Here we show how to use Altizure Javascript SDK to solve some real applications to demonstrate how to integrate realistic 3D models to business application.

If you have any questions, please feel free to write on our [issue page](https://github.com/altizure/experimental-demo/issues).

# 1. Timeline

时间轴可以非常直观地展示一个场景按照时间的变化。这是工程进度管理等任何与时间相关的应用都必不可少的工具。下面我们就通过几个应用演示几种可视化时间轴的方法。
Timeline is very useful for presenting a time series of a changing site. This is a essential tool for monitoring the progress of construction. We show several variation of timeline visualization.

#### 1.1 Timeline in Grid Style

* Demo link: [altizure.github.io/experimental-demo/timeline.html](https://altizure.github.io/experimental-demo/timeline.html)
* Keywords: Loading and setting multiple Altizure projects, text tags.
* Brief introduction: In this demo, a series of 3D models of a construction site are laid out in grid style. Each model is attached with a text tag to show the time stamp of the construction site.

#### 1.2 Timeline with Sliders

* Demo link: [altizure.github.io/experimental-demo/timeline-slider.html](https://altizure.github.io/experimental-demo/timeline-slider.html)
* Keywords: Visibility of markers, interaction, camera flight, marker loading and destruction.
* Brief introduction: In this demo, a series of 3D models of a construction site are laid out with a slider. Users can drag the slider to switch the models in different time. The demo also shows how to control the camera flight animation to help users to fly around 3D models.

# 2. Sensors

Modern handheld mobile devices contain lots of sensors, measuring positions, poses, and velocities. In this section, we demonstrate how to integrate the information of sensors with 3D models to make the scenes more interactive.

#### 2.1 GPS 轨迹记录

* Demo link: [altizure.github.io/experimental-demo/gps-tracker.html](https://altizure.github.io/experimental-demo/gps-tracker.html)
* Keywords: Image tag, tag position, camera following, coordinate transformation, canvas with 3D elements, altitude reading.
* Brief introduction: This demo is only on mobile phones. After you press tracking, the demo will track your GPS location and show your track with aspect to the center of the scene. Your position is shown at realtime as an Altizure logo.

# 3. Performance Benchmark

* Demo link: [altizure.github.io/experimental-demo/performance-test.html](https://altizure.github.io/experimental-demo/performance-test.html)
* Keywords: Text tag, Rendering benchmark, Altitude reading.
* Brief introduction: The demo renders 1000 text tags by default. Users can change the number of text tags and click `Generate` to generate a new scene. The more tags can be rendered smoothly, the more powerful is your system.


# 4. How to Get the Code?

All the demos are open source. You can get the codes by running:

```bash
git clone https://github.com/altizure/experimental-demo.git
cd experimental-demo
python -m SimpleHTTPServer
```

Open your browser and access `http://127.0.0.1:8000/` to run and check the demos.

# 5. Learn More

* [Altizure Javascript SDK](jssdk.md)
* [Altizure Javascript SDK FAQ](jssdk-faq.md)

—

Last modified at {{ file.mtime }}

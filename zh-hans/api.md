# Altizure Graphql API

GraphQL API 是一组以 [GraphQL](http://graphql.org/learn/) 为协议提供的在线 API。这套 API 提供了获取和修改 Altizure 上基础数据的能力。

您如果在找如何快速加载和渲染 Altizure 上的三维数据，请查看我们的 [Javascript SDK](jssdk.md) 页面。

## 1. 使用前准备

* Altizure 开发者账号 (必须)
* 应用令牌 (App key) (必须)
* 用户令牌 (User token) (部分调用需要)

## 2. API 网址和文档

API 调用和文档的入口：
* 国际站 [api.altizure.com/graphql](https://api.altizure.com/graphql) 。
* 中国站 [api.altizure.cn/graphql](https://api.altizure.cn/graphql) 。

## 3. 在浏览器中测试 API

在浏览器中测试 API，可以在浏览文档的同时测试，提高开发效率。确定数据正确后，才把相关的调用复制到代码中集成，过程轻松简单。

这里的教程以谷歌 Chrome 浏览器为例子，其他支持插件的浏览器也可以用类似的方法做测试。

##### 安装插件

安装一个可以修改 http 访问请求 header 的插件。这里我们以 ModHelper 为例。在谷歌 Chrome 扩展商店里面搜索 `ModHelper`，并点击安装即可。

![安装插件](img/install_extension.png)

##### 设置插件修改 http header

在 http request header，添加`key`字段，填入应用令牌 (App key)。

![设置应用令牌](img/set_key.png)

设置完成后访问 [api.altizure.cn/graphql](https://api.altizure.cn/graphql)，可以看到以下界面，集成了“查询区”，“查询结果”和“文档”三个模块。

试着在查询区输入一下字段查询现在公开的项目的 ID 和名字。

```
query {
  allProjects {
    edges {
      node {
        id
        name
      }
    }
  }
}
```

并按查询按钮，便可获得查询结果。

![API 界面](img/api_ui.png)

## 4. 在代码中集成 API 调用

您可以使用任何可以发起 http post request 的程序库来调用 GraphQL API。

例如：

*JQurey in Javascript*

```
$.ajax({
    type: 'POST',
    url: 'https://api.altizure.cn/graphql',
    headers: {
      altitoken: '用户令牌',
      key: '应用令牌'
    },
    data: 'query=' + 'GraphGL的查询字符串'
  })
```

## 5. 获取用户令牌

您需要通过 OAuth 2.0 的标准流程来获取用户令牌。

其中调取 OAuth 窗口的链接为:
``` js
`https://api.altizure.cn/start?client_id=${appKey}&response_type=token&redirect_uri=${redirect_uri}`
```

其中 **appKey** 是您的应用令牌，**redirect_uri** 是您注册该令牌时绑定在上面的域名。

您的应用/网页需要在客户端调出浏览器或者 WebView 来访问这个链接。接下来一个授权窗口会呈献给用户用于输入用户名和密码以便授权您的应用访问该用户的信息。您的应用的说明信息会被现实在这个窗口，便于用户识别开发者的身份。

用户授权之后，登录窗口会重新想到 **redirect_uri** 。重新向的链接会包含一个用户令牌 **access_token**。您既可以在客户端页面处理这个令牌，也可以实现一个服务器端的路由在服务器端接收这个令牌。

对于移动应用，**redirect_uri** 应该填入您的应用的识别符 application bundle identifier name (iOS) 或者包名 package name (android)。这些信息都必须在申请应用令牌时提供给 Altizure 以便记录在册。

您可以访问这个网址 [here](https://github.com/altizure/api-demo-minimal/blob/master/index.html) 查看一个极简的登录实现。

## 6. 常见问题

###### 6.1 国际站和中国站如何选择？

请选择与您链接最快的一个。可以在程序中做些自动判断，如果一个站点掉线了可以切换成另外一个。

###### 6.2 GraphQL API 详细文档在哪儿？

请直接用浏览器参照以上教程访问 [api.altizure.cn/graphql](https://api.altizure.cn/graphql)，即可直接看到所有查询接口的文档。


## 7. 了解更多

* 深入学习 [GraphQL](http://graphql.org/learn/)
* 通过 [Altizure Javascript SDK](jssdk.md) 实现丰富的三维浏览编辑功能
* 更多 GraphQL 相关工具 [Awesome GraphGL](https://github.com/chentsulin/awesome-graphql)

---

该文档最后修改于 {{ file.mtime }}

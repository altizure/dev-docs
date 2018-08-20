# Altizure Graphql API

GraphQL API 是一组以 [GraphQL](http://graphql.org/learn/) 为协议提供的在线 API。这套 API 提供了获取和修改 Altizure 上基础数据的能力。

**您如果在寻找如何快速加载和渲染 Altizure 上的三维数据，请查看我们的 [JavaScript SDK](jssdk.md) 页面，可以方便您快速上手。**

## 1. 使用前的准备

* Altizure 开发者账号 （必须）（参考[开发者账号](dev-account.md)）
* 应用令牌 (App Key) （必须）（参考[开发者账号 2.2](dev-account.md)）
* 用户令牌 (User token) （部分调用需要）


API 调用效果和文档的入口，您可以在这里查询 API 的具体用法和使用效果：
* 国际站 [api.altizure.com/graphql](https://api.altizure.com/graphql) 。
* 中国站 [api.altizure.cn/graphql](https://api.altizure.cn/graphql) 。

## 2. 在浏览器中测试 API

您可以在以上站点中直接执行查询语句来察看查询的效果，部分查询方法需要您使用应用令牌 (App Key)和用户令牌 (User token) ，以下将介绍如何通过修改浏览器的 http header 使用您自己的应用令牌和用户令牌来进行查询。

在浏览器中测试 API，可以在浏览文档的同时对效果进行测试，提高开发效率。确定数据正确后，再把相关的调用复制到代码中集成，过程轻松简单。

这里的教程以谷歌 Chrome 浏览器为例子，其他支持插件的浏览器也可以用类似的方法进行测试。

#### 2.1 安装插件

安装一个可以修改 http 访问请求 header 的插件。这里我们以 ModHeader 为例。在谷歌 Chrome 扩展商店里面搜索 `ModHeader`，并点击安装即可。

![安装插件](img/install_extension.png)

#### 2.2 设置插件修改 http header

在 http request header 中，添加 `key` 字段，填入应用令牌 (App Key)。
有的查询和调用也需要添加 `altitoken` 字段，填入用户令牌 (User token)。

![设置应用令牌](img/set_key.png)

设置完成后访问 [api.altizure.cn/graphql](https://api.altizure.cn/graphql)，可以看到以下界面，集成了“查询区”，“查询结果”和“文档”三个模块。

试着在查询区输入一下字段查询一个组图像的 GP 数。

```
query {
  utility {
    sizeToGigaPixel(width: 4000, height: 3000, numImg: 100)
  }
}
```

按查询按钮，便可获得查询结果。在这个样例中 API 调用会计算 100 张 4000&times;3000 的图像的总 GP 数。

![API 界面](img/api_ui.png)

## 3. 在代码中调用 API 

您可以使用任何可以发起 http post request 的程序库来调用 GraphQL API。

例如使用 *JQurey in JavaScript* 及如下代码调用 API：

JQurey 的[安装](https://jquery.com/download/)和在 [Node.js 调用](https://stackoverflow.com/questions/1801160/can-i-use-jquery-with-node-js)。

```
$.ajax({
    type: 'POST',
    url: 'https://api.altizure.cn/graphql',
    headers: {
      altitoken: '用户令牌',
      key: '应用令牌'
    },
    data: 'query=' + 'GraphQL的查询字符串（即上文中的 query 部分）'
  })
```

## 4. 获取用户令牌

您需要通过 OAuth 2.0 的标准流程来获取用户令牌。

其中调取 OAuth 窗口的链接为:
``` js
`https://api.altizure.cn/auth/start?client_id=${appKey}&response_type=token&redirect_uri=${redirect_uri}`
```

其中 `appKey` 是您的应用令牌，`redirect_uri` 是您注册该令牌时绑定在上面的域名。

您的应用/网页需要在客户端调出浏览器或者 WebView 来访问这个链接。接下来一个授权窗口会呈献给用户用于输入用户名和密码以便授权您的应用访问该用户的信息。您的应用的说明信息会被现实在这个窗口，便于用户识别开发者的身份。

用户授权之后，登录窗口会重新向到 `redirect_uri`。重新向的链接会包含一个用户令牌 `access_token`。您既可以在客户端页面处理这个令牌，也可以实现一个服务器端的路由在服务器端接收这个令牌。

对于移动应用，`redirect_uri` 应该填入您的应用的识别符 application bundle identifier name (iOS) 或者包名 package name (android)。这些信息都必须在申请应用令牌时提供给 Altizure 以便记录在册。

您可以访问这个网址 [here](https://github.com/altizure/api-demo-minimal/blob/master/index.html) 查看一个极简的登录实现。

## 5. 常见问题

#### 5.1 国际站和中国站如何选择？

请选择与您链接最快的一个。可以在程序中做些自动判断，如果一个站点掉线了可以切换成另外一个。

#### 5.2 GraphQL API 详细文档在哪儿？

请直接用浏览器参照以上教程访问 [api.altizure.cn/graphql](https://api.altizure.cn/graphql)，即可直接看到所有查询接口的文档。


## 6. 了解更多

* 深入学习 [GraphQL](http://graphql.org/learn/)
* 通过 [Altizure JavaScript SDK](jssdk.md) 实现丰富的三维浏览编辑功能
* 更多 GraphQL 相关工具 [Awesome GraphQL](https://github.com/chentsulin/awesome-graphql)

---

该文档最后修改于 {{ file.mtime }}

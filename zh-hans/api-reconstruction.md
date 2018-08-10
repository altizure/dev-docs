# 如何通过 API 调用三维重建引擎

## 概况

Altizure 的三维重建引擎是通过一个个项目的形式来调用的。开发者需要创建一个项目以启动相关的三维重建运算。每个用户可以创建许多个项目。但每个项目只能由一个用户来拥有。为了获得创建项目的权限，必须让用户登录后授权给开发者的 App 获取用户令牌，才能创建项目。

## 1. 新建项目

调用 `createProject` 这个 mutation 便可以建立一个新的项目。调用这个 mutation 的时候，必须在 http header 设定应用令牌和用户令牌 (当前操作的用户的用户令牌，不一定是开发者账号的用户令牌)。这个 mutation，接受两个参数，一个是项目名称 (同一个用户的项目可以重名)，另一个是项目类型 (免费或者专业)。无论是创建免费还是专业项目，本身是不需要使用 Alticoin 的。但是专业项目在启动三维重建的时候，必须有足够的 Alticoin 支付相关费用。

如果项目创建成功了，API 会返回一个项目类型的对象，否则返回 `null`。通过这个返回的对象，可以通过里面的 id 成员来获取项目的 ID。这个 ID 非常重要，在所有后续的项目相关的调用中都需要使用。

__样例 GraphQL 语句__
```js
mutation {
  createProject(name: "sample project", type: free) {
    id
  }
}
```

## 2. 上传图像

创建完一个项目后，便可以让用户上传图像。请参考[上传图像](upload.md)的教程了解如何通过 API 调用上传图像。
图像上传完成后，三维重建便可以准备开始了。

## 3. 开始重建

发送 `startReconstructionWithError` 这个 mutation 来启动三维重建任务。这个 GraphQL mutation 需要输入 project id (项目 ID，必填输入) 和 coupon id (优惠券代码，可选输入)。其中项目 ID 是刚才 `createProject` 的 API 调用返回的对象可以查询到，或者可以通过 `my.projects` 来查询。另外的 coupon 可以通过 `my.coupons` 来查询。如果是专业项目，这一步就需要用户账号里有足够的余额或者足够的优惠券才能成功。

如果这个调用成功了，一个新的 task object (任务对象) 会被创建并返回。否则会返回一个错误代码。关于错误代码的详细解释，请参考 [API Reference](https://api.altizure.cn/graphql) 中 `startReconstructionWithError` 相关的文档。

__样例 GraphQL 语句__
```js
mutation {
  startReconstructionWithError(id: "54ed8e5741fbfa3e1967fe9b") {
    error {
      code
    }
    task {
      id
      state
    }
  }
}
```

## 4. 查询项目状态和进度

当一个三维重建任务开始后，您便可以通过 `project` 这个查询来查看其运行状态和其他信息。

---

Last modified at {{ file.mtime }}

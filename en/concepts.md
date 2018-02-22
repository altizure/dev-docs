# Concepts

Before you start to develop with Altizure, here we introduce a few concepts that are useful in the development. As our platform is designed to be easy-to-use, it would be a cakewalk for you to understand these commonly-used concepts if you had tried on some other online development platforms like facebook app or github sdk.

## 1. Developer account

If you do not have an Altizure account yet, please register at the [sign up page](https://www.altizure.com/signup/china?lang=zh-cn) and get one for free.

Then you can apply for [developer account](dev-account.md). All development tools and privileges will be linked to this account. Please keep this account safe and secure.


## 2. App

App is the basic unit of application management on Altizure Development Platform. Each application also has it own unique app key, app secret, and authority level.

It would be better for developers to create differnt Apps and assign them to separate businesses and workflows respectively.


##### App key

App key is the unique identifier of each app on Altizure Development Platform. The information of the developers of an app will be shown to users when the app is asking an authorization from users in order to access the information of users. Users can identify an app by its App key and revoke the authorization anytime if users are not comfortable with the app.

##### App secret

The app secret is used to verify that the call to API comes from a corresponding developer account.
Please do not leak the App secret in frontend web development. Just use it only on the server-side development.


## 3. User token

The user token is the kind of access token that the app obtains after a user authorizes the application. With this token, an authorized app can fetch user's information on Altizure. Altizure provides an authentication workflow based on OAuth 2.0. Hence, users' passwords are safe and never passed to any third party apps. An app should save user token if it wants to keep the login status, but it should not never induce other users to give password and save it for their own needs. On the user side, users can revoke a user token anytime to prevent the app from accessing personal information.


## 4. GraphQL API

Altizure GraphQL API is a set of API in the syntax of [GraphQL](http://graphql.org/learn/). The API allows developers to fetch and modify the data on Altizure. Learn more at [GraphGL API](api.md)

## 5. Javascript SDK

Altizure Javascript SDK allows you to integrate rich 3D experience with our realistic 3D models to your business workflow. Learn more at [Javascript SDK](jssdk.md)

---

Last modified at {{ file.mtime }}

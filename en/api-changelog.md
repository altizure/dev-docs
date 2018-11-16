# Changelog of Altizure GraphQL API

### 1.10.1

__Release data:__
November. 16th, 2018

__New features:__
* Added super/sales query/mutation for getting/setting weekly recommended projects

__Fixes:__
* Caught invalid project flight id when querying Project.flight

### 1.10.0

__Release data:__
November. 9th, 2018

__New features:__
* Added User.language for storing the preferred display language
* Added GET handler (api.altizure.com/subscribe/news?email=abc@gmail.com&locale=zh_tw) for subscribing promotional emails

__Change:__
* Added new args: language in mutation: updateMyProfile

__Fixes:__
* Fixed releasing incorrect number of membership coupons
* Fixed auto-starting stalled projects created in mobile apps

### 1.9.9

__Release data:__
November. 2nd, 2018

__New features:__
* Added new user setting for subscribing promotional emails

__Change:__
* Updated the design of user verification and reset password emails

__Fixes:__
* Fixed infinite pending of processing imported model
* Fixed long waiting time for setting thumbnail via CN api

### 1.9.8

__Release data:__
October. 19th, 2018

__New features:__
* Added super mutation: removeProject

__Change:__
* .com returns cloudfront paths of thumbnails for non-logined user, while .cn returns ali-cdn
* Lowered the minimum size of image from ~8 MegaPixel to ~2 MegaPixel for calculating the GP usage, effectively lowering the cost of projects with small images

### 1.9.7

__Release data:__
October. 12th, 2018

__New features:__
* Added new fields: error and errorCode in Project for giving the error of reconstruction or model conversion

__Improvements:__
* Non China staff-picked or paid projects are available in Cloudfront

__Change:__
* Changed type: ProjectDiagnostic.error as a list of errors instead of a single error

__Fixes:__
* Fixed getting user.freeGPQuota in super query

### 1.9.6

__Release data:__
October. 5th, 2018

__Fixes:__
* Fixed default value of `range` of geoNearProjects

### 1.9.5

__Release data:__
September. 14th, 2018

__New features:__
* Added mutations: browseProject + unbrowseProject for tracking which projects are browsed
* Added query: my.browsingHistory for listing all the projects that have been viewed

__Change:__
* Hide Chinese projects if user's country is not China, Hong Kong, Taiwan, Macao and Singapore

__Fixes:__
* Fixed getting the correct values of Project.initialCamPos, instead of zero values
* Fixed normalizing phone number, all non-digit characters are stripped, e.g. +852-123456789 is equivalent to 852123456789

### 1.9.4

__Release data:__
September. 7th, 2018

__New features:__
* Added new field: importedModels in Project for querying all of the imported models of a project
* Added Search.sandboxes for searching sandbox by names
* Supported signing in by verified phone number and one time password sent via SMS
* Added mutation: requestLoginCode for getting one time password over SMS
* Added mutation: getUserTokenByLoginCode for getting self-issued user token from verified phone and one time password

__Change:__
* Each mobile phone number could only be associated with one account
* Allowed setting logo for sandbox
* Allowed setting visibility and logo for imported projects
* Mutation: getUserToken would not throw GraphQL error if credentials are incorrect, would only return null instead

__Fixes:__
* Fixed type errors of Project.onEarch, SandboxEntity.pid, SandboxEntity.tid
* Fixed sandbox mutations by respecting related membership plan

### 1.9.3

__Release data:__
August. 31th, 2018

__New features:__
* Added new type of membership plan for upgrading between plans
* Added trial state in user.developer.status
* Added query: support.developerProgram for showing the details of developer program
* Added mutation: payDeveloperBraintree for paying developer program via Braintree
* Added mutation: createAliPayDeveloperOrder for paying developer program via Alipay

__Change:__
* Added args: filter in query: support.membershipPlans for querying `Normal` or `Upgrade` or `All` plans
* Updated mutation: uploadImageS3 so that the `image` field no longer needed to be queried for creating the `ProjectImage`, only the url is required now
* Updated mutation: uploadMetaFileS3 so that the `file` field no longer needed to be queried for creating the `ProjectMetaFile`, only the url is required now

__Fixes:__
* Fixed undefined error when querying User.membershipState if no user token is provided

### 1.9.2

__Release data:__
August. 24th, 2018

__New features:__
* Added initialCamPos in Project.modelTransform, for getting the initial position when rendering a project
* Added input argument: initialCamPos in mutation.setProjectProperties for setting initial camera position
* Added input argument: maxPolarAngle in mutation.setProjectProperties for setting maximum polar angle
* Added input argument: onLoadTrans in mutation.setProjectProperties for setting on load transform of model
* Added mutation: setProjectCropMask for setting crop mask
* Added mutation: setProjectWaterMask for setting water mask
* Added private fields: phone + phoneVerified in User object
* Added mutation: requestPhoneVerification for sending SMS to registered phone
* Added mutation: verifyPhone for verifying SMS code
* Supported sending notification alerts via SMS to verified phone

__Change:__
* Allowed setting user phone number + whether to receive sms alert in mutation: updateMyProfile

__Fixes:__
* Fixed setting membership plan name

### 1.9.1

__Release data:__
August. 17th, 2018

__New features:__
* Added support for paying coins or membership plan via Alipay web and mobile
* Added transaction types: AlipayBuyMembership
* Added super/sales query: refundAliPay
* Added super/sales query: allGQLEvents

__Change:__
* Renamed mutation: createAliPayOrder to createAliPayCoinsOrder

__Fixes:__
* Fixed setting OAuth apps domains to not to include the protocol

### 1.9.0

__Release data:__
August. 10th, 2018

__New features:__
* Added options: taskType in mutation: startReconstructionWithError, for starting different task types
* Automatically create thumbnail for every newly imported model
* Added new fields: assetStorage, visibility, coupon and modelPerProject etc in MembershipInfo in User object, to query current membership details
* Added query: support.membershipPlans for querying membership plans information
* Added new field: savePaymentMethod in User object, to indicate whether to store the payment method in Braintree or not
* Added new args: savePaymentMethod in mutation: updateMyProfile, to remove any existing payment methods stored
* Added query: Sandbox.collaborators relay connection
* Added super query: userTransactions
* Added new field: lastDoneGP in Project
* Added mutation: payMembershipBraintree to pay for membership plan via Braintree

__Change:__
* Allowed renewing membership without extending existing period in super/sales api
* Added args: sortBy + search in query my.favouriteProjects and my.favouriteSandboxes

__Fixes:__
* Fixed setting the correct GP as last done GP in project upgrade transaction, instead of the current GP

### 1.8.6

__Release data:__
July. 27th, 2018

__New features:__
* Supported custom notification description by offering tokenized description arguments `descArgs` in type: Notification

__Change:__
* Allowed any user to set thumbnail of Sandbox

### 1.8.5

__Release data:__
July. 20th, 2018

__New features:__
* Added query: My.allProjects, for querying native and imported model projects at the same time
* Added mutation: makeScreenshot to make a server side rendered screenshot with specific dimension and camera pose
* Added mutation: removeScreenshot to remove a screenshot of a project

__Fixes:__
* Fixed empty importedModelType error

### 1.8.4

__Release data:__
July. 13th, 2018

__New features:__
* Added fields: animation + texture in type: SandboxEntity
* Added args: planet + background in SandboxMutation.create + update

__Fixes:__
* Fixed setting uploaded image as `Invalid` if client and server side checksums mismatch

### 1.8.3

__Release data:__
July. 6th, 2018

__New features:__
* Added query: my.favouriteProjects / my.favouriteSandboxes for querying favourite projects with descending created time
* Added sorting options for sandbox apis
* Added super/sales query: userProjectList to output all the projects as CSV of a user

__Change:__
* Removed deprecated query: version, User.thumb, getGeoIPInfo.suggestedBuckets
* Removed deprecated mutation: startReconstruction, upgradeProject,

### 1.8.2

__Release data:__
June. 22th, 2018

__New features:__
* Added query: search.user(username) for searching the account unique username

### 1.8.1

__Release data:__
June. 15th, 2018

__New features:__
* Supported changing the imported model type via mutation: setProjectProperties(importedModelType)

__Change:__
* For query: project.cropMask, if crop mask does not exist, return a default mask instead of null

__Fixes:__
* Fixed issues of translating original image names to hashed image names in meta files if same image is uploaded multiple times
* Fixed changing project.importedState of imported-model-project to `Pending` immediately after a new upload URL is signed

### 1.8.0

__Release data:__
May. 25th, 2018

__New features:__
* Supported Minio object storage server
* Added mutation: uploadImageMinio, to upload image to our private Minio server
* Added mutation: downgradeProject, for downgrading pro and non-done-once project to free project

__Fixes:__
* Fixed issue of pre-processing images indefinitely triggered from mobile apps, projects that have timeout images will be auto-started

__Change:__
* Changed SandboxEntity's name from required to optional.
* Changed domains of cdn of various sandbox thumbs according to the region of api server

### 1.7.0

__Release data:__
May. 18th, 2018

__New features:__
* Added mutation: transferProject for transferring ownership of projects to other user
* Added mutation: transferCoins for transferring coins to other user
* Added mutation: transferCoupon for transferring unused and non-expired timed coupons to other user

__Breaking Change:__
* Allowed zero transaction for starting reconstruction / upgrading project.
(Previously, if total value of timed coupon used is bigger than required,
no transaction will be conducted. Now, a transaction of zero amount will be carried out
with relevant information such as the coupons used in the transaction.)

### 1.6.2

__Release data:__
May. 11th, 2018

__New features:__
* Added type: frame in sandbox's animation

__Fixes:__
* Fixed setting project as modified if an image is removed
* Fixed missing message of 'Authentication Error' in various mutations

### 1.6.1

__Release data:__
May. 4th, 2018

__New features:__
* Added transaction types: [
    BraintreeBuyCoin,
    AlipayBuyCoin,
    WechatBuyCoin,
    DepositCoinCoupon,
    Reconstruction,
    ProjUpgrade,
    Refund,
    SpecialCharge
  ] in type: Transaction
* Supported custom transaction description by offering tokenized description arguments `descArgs` in type: Transaction
* Added ids of coupons used in relevant transaction
* Added sales mutation: refundProject and specialChargeUser

__Fixes:__
* Fixed issue of not refunding a pro project if it is stopped within 15 minutes

### 1.6.0

__Release data:__
April. 27th, 2018

__New features:__
* Added mutation: sandbox.storyboard.{createStory + updateStory + removeStory + createStoryScene + removeStoryScene}
* Supported image file name that contains space(s), e.g. 'abc def ghi.JPG' in metafile (despite space is being used as delimiter)

__Improvements:__
* Reduced the latency of all the query (especially in China) with geo-distributed replica set

__Fixes:__
* Fixed typo of metafile filename to accept `group.txt` instead of `groups.txt`

__Breaking Change:__
* All images that are not in state: `Ready(Strong)` or `Invalid` will be forcefully switched to `Invalid`
if their last `modifiedDate` is older than 65 minutes

### 1.5.1

__Release data:__
April. 20th, 2018

__New features:__
* Supported markdown format in sales query: sendEmail
* Added mutation: setSandboxThumb for setting progressive sandbox thumbnails
* Added sales mutation: addUserNote and removeUserNote
* Added new buckets: Beijing, Virginia and London in enum: BucketS3Model, used in mutation: uploadModelS3
* Added new query: getGeoIPInfo.nearestModelBuckets to get the nearest buckets for uploading obj model

### 1.5.0

__Release data:__
April. 13th, 2018

__New features:__
* Added field: importedModelType in Project, to indicate the imported model type
* Added field: developer.level in User, to store the base level of subsequent apps
* Allowed sales api to get/set developer base level and individual apps level
* Added sales api to send email

__Fixes:__
* Fixed setting default materials for imported models
* Allowed sales to query private coupon fields
* Enforced expiring developer status and all of his apps
* Properly handled the case when project image is removed when it is still in excited state

__Breaking Change:__
* Changed the definition of User.freeGPQuota to {free global quota + staff picked bonus + membership quota}, instead of just {free global quota + staff picked bonus}
* project.allMaterials were set as public, instead of private

### 1.4.0

__Release data:__
April. 6th, 2018

__New features:__
* Added 2 new filters: ActiveUsed + ActiveUnused in FILTER_COUPON_TIME_STATE, which is used in query.my.coupons
* Added query.sandbox.sandbox + query.sandbox.allSandboxes + query.my.sandboxes
* Added mutation.sandbox
* Supported importing CAD, photogrammetric and point-cloud models

__Fixes:__
* Fixed status 500 server error if no user token is provided in any query
* Fixed handling pre-starting non-existing project
* Fixed unhandled promise rejection error when registering new user with empty fields

__Breaking Change:__
* Mutation: createProject accepts an additional arg: modelType for indicating the imported model type.

### 1.3.1

__Release data:__
March. 29th, 2018

__New features:__
* Added resendVerificationEmail in query.support
* Added args: type in query.my.transactions to filter credit or debit transactions
* Added new field: MembershipInfo in User object

__Fixes:__
* Fixed issues of translating original image names to hashed image names in meta files
* Fixed issues of user login via OAuth

### 1.3.0

__Release data:__
March. 23th, 2018

__New features:__
* Supported accepting multiple time based coupons in a single operation
* Added sales API

__Fixes:__
* Fixed redeem coupon link in http server mode
* Fixed ProjectImage's 'resized' ValidatorError when calling mutation: hasImage
* Fixed mis-judging 'Invalid' image as 'ReadyStrong'

__Breaking Change:__
* Mutation: upgradeProjectWithError, startReconstructionWithError and preStartReconstruction accept a list of coupon ids, instead of a single coupon id.

### 1.2.0

__Release data:__
March. 16th, 2018

__New features:__
* User registration: send an email verification upon user registration
* Added query: project.allMaterials for getting all materials
* Added mutation: addProjectMaterial + updateProjectMaterial + removeProjectMaterial

__Breaking Change:__
* Mutation: PreStartProject will start the reconstruction task if all the images are in either 'Ready' or 'Invalid' state.
So PreStartProject should be called after all images are uploaded.
Previously, it is supposed to be called before all images are 'Ready' or 'Invalid'.

### 1.1.0

__Release data:__
Feb. 12th, 2018

__New features:__
* Make endpoint: `/graphql` browsable without app key
* Added query: support.projectDoctor for diagnostic information
* Added super query: approveDeveloper

__Improvements:__
* Used provider pattern for selecting cloud providers upload services

__Bug fixes:__
* Fixed query: suggestedBuckets return values

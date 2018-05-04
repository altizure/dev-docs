# Changelog of Altizure GraphQL API

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

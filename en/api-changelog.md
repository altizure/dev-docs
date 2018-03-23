# Changelog of Altizure GraphQL API

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

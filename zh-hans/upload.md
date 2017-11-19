# 如何使用 GraphQL API 上传用三维重建的图像

## 概况

为了获得最佳的上传速度，用于三维重建的图像将直接从客户电脑传输到我们的亚马逊或者阿里云的存储空间里。
传输和存储中，你的图像将被严格保密，其他任何人都不可以读取和修改你的图像。
所以上传开始前需要开发者通过我们的 API 获取一个临时的鉴权令牌。

As filename is the only identifier in the buckets, the image is required to be uploaded to a specific url (S3) or prefix (OSS) so that Altizure knows which image is which.

### 1. 选择最近的 bucket

开发者可以通过 `GeoIPInfo.nearestBuckets` 这个查询来获取当前用户最近的 Bucket 用于上传，以达到最快的上传速度。

### 2. 计算图像校验码

为了保证图像上传的稳定性和数据的一致性。在上传每张图像前开发者必须

* 计算的图像的 **sha1sum** 校验码
* 调用 mutation `hasImage(pid, sha1sum)` 检查图像是否已经项目 `pid` 里存在。
* 如果图像存在则跳过该图像无需上传；如果图像不存在则上传图像。

### 3. 上传

##### 3.1 上传到阿里云的OSS

If an OSS bucket is chosen, obtain STS and the related meta image info (e.g. id and hashed filename) by calling mutation `uploadImageOSS(pid, bucket, filename, type, checksum)`. STS is a temporary (1 hour) security token for the write only permission on the `/pid` prefix.
If it has expired, renew with the same mutation. Otherwise, only request the `image` gql fragment from the result, and re-use the same STS for performance reason. As signing from Aliyun is slow, one should not sign a new STS for each image.

Given the STS, images could be uploaded via any compatible protocol or library to OSS. It is required to upload with the specific hashed filename according to the image info returned from the `uploadImageOSS` mutation. Specifically, it is required to be put to the path `${pid}/${image.filename}` inside the bucket.

In order to keep track of the state, just before an image is uploaded, call mutation `startImageUpload(id)` to signal the start of the process. When the upload is done, call mutation `doneImageUpload(id)`.


##### 3.2 上传到亚马逊的S3

If a S3 bucket is chosen, uploading is much simpler.
For each image, call the mutation `uploadImageS3(pid, bucket, filename, type, checksum)` to obtain a temporary (3 hours) signed url and the related meta image info.

Given the signed url, use the standard HTTP put to put the file to this url with `Content-type: JPEG` or other formats accordingly.

Just before each upload, it is required to call mutation `startImageUpload(id)`. There is no need to signal the end of uploading.

### 4. 等待图像预处理

Uploaded images will be copied, verified and processed. Eventually, the image state will become either `Ready` or `Invalid`.
If the total count of `Ready` matches the desired number, you may call mutation `startReconstructionWithError(id, options)` to start the reconstruction. Otherwise, you may consider re-uploading any outstanding image as indicated by the mutation `hasImage`.

If you do not concern about a few number of missing images and want to start the reconstruction immediately once all the images are ready, you could call mutation `preStartReconstruction(id, options)`.

## 了解更多

* 了解更多关于 [STS](https://www.alibabacloud.com/help/doc-detail/31953.htm?spm=a3c0i.o31952en.b99.284.7ab2aa72OYaf6D) 的信息

---

Last modified at {{ file.mtime }}

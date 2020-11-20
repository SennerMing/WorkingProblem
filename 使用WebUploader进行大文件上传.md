#### 一、选择文件后自动开启上传任务：

##### 		

##### 		上传文件之前，调用checkFile接口：

​			请求示例：

![image-20201113153604309](D:\LXRSelf\progress\问题整理\images\checkFile.png)

​		请求FormData中包含了文件的基本信息，名称、大小及MD5校验码。

​		后台拿到基本信息，判断此次要上传的文件是否上传过，如果上传过则获得上传状态，上传完毕则返回“已上传”，未上传完毕则将最后一次上传chunk位置返	回，从未上传过该文件，则在redis中记录此次上传信息，包括上传文件的所有者，当前上传位置为0，并将记录信息返回到前端。



##### 上传文件，调用upload_do接口：

​	请求示例：

​			![image-20201113154647653](D:\LXRSelf\progress\问题整理\images\upload_do_first.png)

​			![image-20201113154731420](D:\LXRSelf\progress\问题整理\images\upload_do_secondly.png)

​			开始上传，将webuploader为文件生成的ID，文件类型，最后修改时间，所占空间大小，分块个数(chunks)，前端记录的当前上传块(chunk)，MD5校验码，分块大小以及分块的二进制文件。后台接收到前端传来的字节文件，进行数据的追加写入。某次写入失败，则抛出相应异常信息，不进行chunk写入的记录。

​			
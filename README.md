# SealRTC-Android 

## 项目功能说明
项目源码是基于RongRTCLib实现的音视频会场模型。主要包括以下功能

1、两端输入同样的房间号，可进行音视频通话

2、观察者模式： 以观察者身份加入会场，代表着不发布任何资源，只订阅其他人资源

3、基于here white实现的白板功能

4、发布自定义音频/视频，内置默认音频和视频文件。

5、发布USB摄像头视频，基于UVCCamera实现。

6、美颜/水印功能，基于GPUImage方式实现。


## 项目集成说明
1、在融云官网注册开发者账号，并获取AppKey。
>修改源码UserUtils.java中的APP_KEY为获取到的appkey。

2、源码提供的是基于短信验证方式获取token，用户自己集成体验，流程与demo不一样，不需要以短信验证的方式获取token，而是需要在融云官网开发者平台生成token，详细请参考[IMLib SDK 开发指南](https://www.rongcloud.cn/docs/android_imlib.html)

>获取到token后，直接修改MainPageActivity中onClick方法的 case R.id.connect_button:下的逻辑，注释掉多余代码，只保留 RongIMClient.connect(token, callback)方法的相关调用即可。

3、Demo的业务逻辑代码集中在MainPageActivity.java(登录页面)和CallActivity.java(通话页面)中

4、水印的源码请参考watersign目录

5、白板源码请参考whiteboard目录

6、如果不需要发布自定义音频/视频功能，请删除assets文件夹下的mp3和mp4文件，以减少项目的体积。

7、如果不需要USB Camera功能，可以删除UVCCamera相关类库和代码
>app\libs下只保留RongRTCLib_xx.jar和各个架构文件夹中的lib_RongRTC_so.so即可，并且删除源码usbcamera文件夹

更多详细的集成步骤和API接口介绍，请参考[音视频 SDK 文档](https://www.rongcloud.cn/docs/android_rtclib.html)
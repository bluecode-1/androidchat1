## WildFire IM Solution

WildFire IM is a professional-grade instant messaging and real-time audio/video solution, maintained and supported by Beijing WildFire Wireless Network Technology Co., Ltd.

Key features include: secure and reliable private deployment, powerful performance, comprehensive functionality, full platform support, high open-source rate, simple deployment and operation, developer-friendly for secondary development, easy integration with third-party systems or embedding into existing systems. For more details, please refer to the [online documentation](https://docs.wildfirechat.cn).

Main projects include:

| [GitHub Repository (Main)](https://github.com/wildfirechat)      | [Gitee Repository (Mirror)](https://gitee.com/wfchat)        | Description                                                                                      | Notes                                           |
| ------------------------------------------------------------ | ----------------------------------------------------- | ----------------------------------------------------------------------------------------- | ---------------------------------------------- |
| [im-server](https://github.com/wildfirechat/im-server)       | [server](https://gitee.com/wfchat/im-server)          | IM Server                                                                                 |                                                |
| [android-chat](https://github.com/wildfirechat/android-chat) | [android-chat](https://gitee.com/wfchat/android-chat) | WildFire IM Android SDK and App source code                                               | Easy for secondary development or integration into existing applications |
| [ios-chat](https://github.com/wildfirechat/ios-chat)         | [ios-chat](https://gitee.com/wfchat/ios-chat)         | WildFire IM iOS SDK and App source code                                                   | Easy for secondary development or integration into existing applications |
| [pc-chat](https://github.com/wildfirechat/vue-pc-chat)       | [pc-chat](https://gitee.com/wfchat/vue-pc-chat)       | PC client based on [Electron](https://electronjs.org/)                                    |                                                |
| [web-chat](https://github.com/wildfirechat/vue-chat)         | [web-chat](https://gitee.com/wfchat/vue-chat)         | WildFire IM Web client, [Demo](http://web.wildfirechat.cn)                               |                                                |
| [wx-chat](https://github.com/wildfirechat/wx-chat)           | [wx-chat](https://gitee.com/wfchat/wx-chat)           | Mini-program Demo (supports WeChat, Baidu, Alipay, ByteDance, QQ and other mini-program platforms) |                                                |
| [app server](https://github.com/wildfirechat/app_server)     | [app server](https://gitee.com/wfchat/app_server)     | Application server                                                                        |                                                |
| [robot_server](https://github.com/wildfirechat/robot_server) | [robot_server](https://gitee.com/wfchat/robot_server) | Robot server                                                                              |                                                |
| [push_server](https://github.com/wildfirechat/push_server)   | [push_server](https://gitee.com/wfchat/push_server)   | Push server                                                                               |                                                |
| [docs](https://github.com/wildfirechat/docs)                 | [docs](https://gitee.com/wfchat/docs)                 | WildFire IM documentation, including design, concepts, development, and usage instructions, [View online](https://docs.wildfirechat.cn/) |                                                |


## Description

This project is the WildFire IM Android App. During development, we fully considered secondary development and integration needs. It can be integrated as an SDK into other applications or directly used for secondary development.

Developing an IM system is really challenging. Please give us a star to support us to keep going 🙏🙏🙏🙏🙏

## About Package Name/ApplicationId
1. When developing specific products, please do not directly use the package name/applicationId of this demo, as we will modify it from time to time
2. It is forbidden to use this product for illegal purposes. Once discovered, we will stop any form of technical support
3. When modifying the package name, it may cause compilation failure. You need to synchronously modify the `package_name` field in `google-services.json` and `agconnect-services.json` files. When integrating push services, you need to regenerate the corresponding `google-services.json` and `agconnect-services.json` files
4. If you need to modify the package name of `client`, `mars-core-release` or `avenginekit.aar`, please contact us

## Development and Debugging Instructions
1. JDK: 17
2. We use the latest stable version of Android Studio and corresponding gradle for development. For older IDE versions, we have not tested them, and you need to resolve compilation issues yourself

## Special Instructions for minSdkVersion Set to 21 - Debug APK May Not Support Audio/Video Calls
1. When obfuscation is disabled, debug version apk generated via command line `./gradlew clean aDebug` or in Android Studio via `Build App Bundle(s)/APK(s) -> Build APK(s)` does not support audio/video calls. For the specific reason, please refer to [useFullClasspathForDexingTransform](https://issuetracker.google.com/issues/333107832)
2. When obfuscation is enabled, debug version apk works normally. Set `chat/build.gradle#buildTypes#debug#minifyEnabled` to true to enable obfuscation for debug version
3. Release version apk generated via command line `./gradlew clean aR` or in Android Studio via `Generate Signed App Bundle/APK...` works normally

## Secondary Development Instructions
WildFire IM uses Bugly as a log collection tool. When doing secondary development, be sure to replace the ```bugly id``` in ```MyApp.java``` with your own. Otherwise, error logs will come to us, you won't be able to collect error logs, and we will be interfered with

## Obfuscation Instructions
1. Ensure that the ```lifecycle``` version you depend on is 2.2.0 or above
2. Refer to ```chat/proguard-rules.pro``` for configuration

## Security Instructions
To facilitate developers' deployment and testing, `HTTP` network requests are allowed by default. To improve security, before going live, please perform the following operations:
1. Configure `HTTPS` support for `app-server` and set `APP_SERVER_ADDRESS` to the `HTTPS` address
2. If you support the open platform, configure `HTTPS` support for the development platform and set `WORKSPACE_URL` to the `HTTPS` address
3. If you support organizational structure, configure `HTTPS` support for the organizational structure service and set `ORG_SERVER_ADDRESS` to the `HTTPS` address
4. Set `android:usesCleartextTraffic` in `chat/src/main/AndroidManifest.xml` to `false`
5. For more security instructions, please refer to [Is WildFire Secure](https://docs.wildfirechat.cn/blogs/%E9%87%8E%E7%81%AB%E5%AE%89%E5%85%A8%E5%90%97.html)

## Sensitive Permission Instructions
1. `android.permission.PROCESS_OUTGOING_CALLS`, allows regular phone calls to interrupt audio/video calls, not requested by default
2. `android.permission.SYSTEM_ALERT_WINDOW`, allows audio/video call windows to be minimized and float above other windows
3. `android.permission.BLUETOOTH`, `android.permission.BLUETOOTH_ADMIN`, allows using Bluetooth headsets during audio/video calls

## Android 4.x Instructions
Please use the [api-19](https://github.com/wildfirechat/android-chat/tree/api-19) branch. If compilation fails, it may be because the 4.x version protocol stack has not been updated in time. Please contact `wfchat` on WeChat for updates

### Contact Us

> For business cooperation, please use email to contact us first. For technical issues, please post on the [WildFire IM Forum](http://bbs.wildfirechat.cn/)

1. heavyrain.lee  Email: heavyrain.lee@wildfirechat.cn  WeChat: wildfirechat
2. imndx  Email: imndx@wildfirechat.cn  WeChat: wfchat

### Q&A

1. If you find bugs, please submit an issue on GitHub
2. For other questions, please go to the [WildFire IM Forum](http://bbs.wildfirechat.cn/) for discussion and learning
3. WeChat Official Account

<img src="http://static.wildfirechat.cn/wx_wfc_qrcode.jpg" width = 40% height = 40% />

> We strongly recommend following our official account. We will notify everyone through the official account when there are new releases or major updates. We also regularly publish technical introductions about WildFire IM

## Demo Experience
We provide a demo experience. Please scan the QR code with WeChat to download and install

![WildFire IM](http://static.wildfirechat.cn/download_qrcode.png)

## App Screenshots
[Click to view Android Demo video](https://static.wildfirechat.cn/wf-android-demo-live.mp4)

<img src="https://static.wildfirechat.cn/wf-android-demo-1.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-2.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-3.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-4.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-5.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-6.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-7.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-8.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-9.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-10.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-11.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-12.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-13.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-14.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-15.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-16.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-17.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-18.jpg" width = 40% height = 40% />

<img src="https://static.wildfirechat.cn/wf-android-demo-19.jpg" width = 40% height = 40% />


## Integration
1. For the client part, download the code yourself and import the client module into your own project
2. For the uikit part, download the code yourself and import the uikit module into your own project
3. For the push part, download the code yourself and import the push module into your own project

## Push Notifications
When the app is in the background, different phone manufacturers have different background policies, which may quickly or eventually freeze and kill the app. At this time, receiving messages requires the manufacturer's push notification service. Please deploy the push service. The push service code can be downloaded from [Github](https://github.com/wildfirechat/push_server) and [Gitee](https://gitee.com/wfchat/push_server). For specific usage, please refer to the instructions on the push service project

## Contribution
Pull requests are welcome to build a better open-source IM together

## Acknowledgments
1. [LQRWeChat](https://github.com/GitLqr/LQRWeChat) Image selector and emoji in this project are developed based on this
2. [butterKnife](https://github.com/JakeWharton/butterknife)
3. OkHttp and other excellent open-source projects
4. All icons used in this project are from [icons8](https://icons8.com), we thank them
5. GIF images are from the Internet, we thank the creators

If anything infringes on your rights, please contact us to delete it 🙏🙏🙏

## License

1. Under the Creative Commons Attribution-NoDerivs 3.0 Unported license. See the [LICENSE](https://github.com/wildfirechat/android-chat/blob/master/LICENSE) file for details.

# Xcode7.0DeviceSuppot


对于Xcode8的发布，苹果也是来了个大的跳跃，默认最低支持的iOS版本为8.0，当然也并不是说8.0以下就直接放弃了，虽然表现出来的是这样，毕竟使用8.0以下系统的还是大有人在的，老项目要兼容iOS8以下也是可以另辟蹊径的。

首先我们要找到Xcode是通过什么来兼容iOS版本的，请打开以下路径：/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/DeviceSupport，在文件夹中我们能够看到Xcode支持的iOS版本，从8.0开始，唯独没有8.0以下的，所以我们第一步要做的就是把需要支持的iOS版本的配置包放进来，博主这里支持到7.0，包括7.1，下载配置包地址请看：真机配置包下载，下载下来后拖进去。

到这里并没有结束，接下来需要配置Xcode，打开以下路径：/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS.sdk 
，在这里我们要改点东西，但是在这个文件夹里的东西是锁定的，首先右键‘空白部分’，点击显示简介，滑动到最下面，点击小锁打开权限，需要输入管理员密码，接着把所有的权限改为读写，第一步完成，接下来，右键SDKSettings.plist文件夹，和上面同样的操作，打开读写权限，然后双击打开SDKSettings.plist文件，如图： 

DefaultProperties -> DEVELOPMENT_TARGET_XXXXXXX -> 增加7.0 7.1

在这个下面添加7.0和7.1，按照从小到大的顺序排好。接着重启电脑即可，结束的时候别忘了把刚才改的权限都改回去以防不小心动了不该动的。 
看Xcode里面： 

已经可以看到7.0和7.1了，如果需要支持更低的版本，跟上面同样的方法，只需要添加对应的配置文件即可。

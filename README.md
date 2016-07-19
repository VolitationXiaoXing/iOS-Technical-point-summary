# iOS-Technical-point-summary
##iOS技术点思路汇总,iOS面试必备神器,iOS面试题

##软件常用构架	2
##即时通讯(XMPP)	2
##地图	2
##CoreData与SQLite	2
##支付	2
##三方登录与分享	2
##推送	2
##本地推送实现思路:	2
##远程推送:	3
##原生推送:	3
##三方推送:	4
##换肤(夜间模式)	4



##软件常用构架
##即时通讯(XMPP)
##地图
##CoreData与SQLite
##支付
##三方登录与分享
##推送
##本地推送实现思路:
###关键字: UILocalNotifcation
 	1.0创建UILocalNotifcation对象
 	1.1设置触发时间 fireDate
 	1.2设置内容 alertBody
 	1.3设置声音 soundName
 	1.4设置图标红点数量 applicationIconBadgeNumber
	1.5设置先要传递的信息 userInfo
 	
	2.0将UILocalNotifcation加入到本地推送调度池中
 	(iOS8以上需要授权)在授权 UIUserNotificationSettings

	3.0 授权的时候,可以设置分类(推送的分类指的是接受到了推送消息后向下划得时候的按钮的集合)  UIMutableUserNotificationCategory 分类,需要注意的是在这里分类的设置id需要跟设置推送的分类id一致.
UIMutableUserNotificationAction 分类中的行为

	4.0 接受到推送消息分为三种情况:前台,后台(程序没有被杀死),没有开启程序,在前台和后台的时候会调用didReceiveLocalNotification方法,如果输没有开启程序,通知的信息是存在didFinishLaunchingWithOptions中的option参数中.
	4.1 如过设置了分类事件,在handleActionWithIdentifier方法中处理事件.实现页面跳转可以将页面跳转信息存放在userinfo中在处理.

远程推送思路:
远程推送可以选择使用原生推送也可以使用三方SDK(极光推送为例)
0.0需要开发者账号
0.1需要生成远程推送的证书
原生推送:
	原生远程推送实现思路: 


三方推送:
	三方推送实现思路:
换肤(夜间模式)

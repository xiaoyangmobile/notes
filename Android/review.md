click event dispatch
activity.dispatchTouchEvnet
PhoneWindow.superDispatchTouchEvent
DecorView.superDispatchToutcheEvent
FrameLayout.dispatchToucheEvent
GroupView.dispatchTouchEvent

if (child) child.dispatchTouchEvent
else View.dispatchEvent

view
if (onTouch) else onTouchEvent

Service
service and IntentServcie
IntentService: 在service中实现了Thread，所有操作都会放到service的thread中进行操作

startService 和 bindService
startService: onCreate onStartCommand onDestroy
bindService: onCreate onBind unBind onDestroy
startService: 生命周期与其他无关，调用stopService停止
bindService: 和绑定的组件生命周期相关，unBind后停止并销毁
如何保证service不被杀死？
不被杀死和杀死后重启
不被杀死：
manifest中设置优先级
设置为前台service
杀死后重启：
设置应用persistent=true，保证开机启动和被杀死重启
在onStartCommand中设置START_STICKY
在onDestroy中发送一个私有广播重启service
监听系统广播判断service状态
广播注册的两种方法：
生命周期不一样：静态广播app生命周期；动态执行完任务
优先级不一样：静态广播优先级低；动态高
静态注册还有启动app功能
注册时间点不一样：静态是安装app时，动态是动态注册

Message
* Message.obtain
* Activity:handler.sendMessage
* Hander: messageQueue.enqueue

Handler:
* Looper: Looper.myLooper()
* messageQueue: looper.messageQueue;
messageQueue.enqueue(Message)

Looper:
myLooper: ThreadLocal.get()
prepare: ThreadLocal.set(new Looper());
ThreadLocal: 
* set: currentThread.ThreadLocalMap.set(ThreadLocal, looper); Looper
* get: currentThread.ThreadLocalMap.get(ThreadLocal); Looper
new Looper(): new MessageQueue(); 
messageQueue:


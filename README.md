# Demo
启动游戏后，无论切后台还是关闭屏幕，‘AudioMix '一直未释放，Google后台的Android Vitals提示【部分唤醒锁定操作卡住（后台）】问题持续存在。

[attach]24817[/attach]

Native版本：2.6.0
复现方式：
1、手机连接usb调试
2、启动demo游戏
3、关闭手机屏幕或切换后台
4、执行 adb shell dumpsys power 命令查看
会看到：
Wake Locks: size=1
  PARTIAL_WAKE_LOCK              'AudioMix' (uid=1013, pid=0, ws=WorkSource{10357})
一直得不到释放!
此外，游戏不播放声音这个问题也一样存在。

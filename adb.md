### 1 获取系统版本（Android 9 返回 9）：
```
adb shell getprop ro.build.version.release
```
### 2 获取系统 api 版本（API 28 返回 28）：
```
adb shell getprop ro.build.version.sdk
```
### 3 截屏
```shell
adb shell screencap -p /sdcard/screencap.png
```
### 4 录制视频
```shell
adb shell screenrecord /sdcard/screenrecord.mp4
```
更多截屏和录制视频查看[参考链接](https://blog.csdn.net/gdutxiaoxu/article/details/69802895)
### 5 获取手机当前显示的 Activity 名称
```shell
adb shell dumpsys window w | grep \\/ | grep name=
```
### 6 查看当前栈顶的 Activity 的 Fragment
```shell
adb shell dumpsys activity top
```
#### 安装应用，卸载应用
* adb install /path/to/the/apk*.apk
* adb uninstall com.packagename.**

#### 启动Activity

adb shell am start packagename/activity_name

* example
adb shell am start -n com.test.jkwang/com.test.jkwang.helloactivity

#### 获取屏幕
adb shell screencap -p | perl -pe 's/\x0D\x0A/\x0A/g' > screen.png

#### 向设备发送解锁命令
adb shell input keyevent 82

#### 按标签过滤输出日志
adb logcat -s TAG_NAME1 TAG_NAME2

#### 显示特定优先级的日志
adb logcat "*:W"  // adb logcat W


#### 按标签和优先级过滤
adb logcat -s TAG_NAME : PRIORITY // adb logcat -s TEST: W

#### 清楚logcat缓冲区
adb logcat -c

#### 序列号,bug报告
adb get-serialno bugreport

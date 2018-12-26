##Logcat命令速查##

    1、window下中文输出乱码解决方法：cmd内输入 chcp 65001,执行即可

    2、根据tag标记和级别过滤日志输出：
    仅输出TAG为“ActivityManager”且优先级大于等于“Info”和TAG为“PowerManagerService”并且优先级大于等于“Debug”的日志：adb logcat ActivityManager:I PowerManagerService:D *:S （*：S代表其他标签不输出消息）

    3、adb 进入shell，使用grep命令过滤
    logcat | grep String #logcat | grep -i string 忽略大小写

    4、adb 查看进程id
    adb shell ps | grep com.package.name 
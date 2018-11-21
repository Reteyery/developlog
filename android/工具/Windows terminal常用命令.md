##Windows terminal常用命令##

    1、 文件目录操作

        返回根目录  cd \
        返回上一级目录 cd ..
        清屏 cls

    2、adb shell 命令

        查看当前所有进程： adb shell ps
        根据条件筛选进程： adb shell ps | findstr ""
        安装apk: adb install com.reteyery.starlord.apk
        卸载apk: adb uninstall com.reteyery.starlord 
        安装和卸载的区别在于安装需要带有.apk后缀，卸载不需要后缀

        查看前台 Activity adb shell dumpsys "activity | grep mFocusedActivity"
    
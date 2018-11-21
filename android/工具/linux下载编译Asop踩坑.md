##Linux下载编译Asop踩坑##

	1、获取终端 ctrl + alt + t

	2、root 账户登录

		启用root账号：sudo passwd root（按照提示设置root账号密码）
		切换到root登录：sudo -s -H
		编辑 vi /usr/share/lightdm/lightdm.conf.d/50-ubuntu.conf 在文件最后面添加 greeter-show-manual-login=true
		重启linux（sudo -s -H切换到root）

	3、vi编辑器上下左右键变ABCD的解决方法

		首先卸载旧版本的vi编辑器：$sudo apt-get remove vim-common
	　  然后安装新版vi即可：sudo apt-get install vim

	4、下载Asop

		1、apt-get install git-core curl #下载git 和 curl 个工具
		2、下载 repo 工具
			mkdir ~/bin
			PATH=~/bin:$PATH
			curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo ( curl https://mirrors.tuna.tsinghua.edu.cn/git/git-repo -o repo )
			chmod a+x ~/bin/repo
			坑：https://storage.googleapis.com/git-repo-downloads/repo 会报错，此处使用tuna的git-repo镜像
			curl https://mirrors.tuna.tsinghua.edu.cn/git/git-repo -o repo
		3、下载Asop源码
			wget https://mirrors.tuna.tsinghua.edu.cn/aosp-monthly/aosp-latest.tar # 下载初始化包
			tar xf aosp-latest.tarcd AOSP   # 解压得到的 AOSP 工程目录# 这时 ls 的话什么也看不到，因为只有一个隐藏的 .repo 目录
			repo sync # 正常同步一遍即可得到完整目录# 或 repo sync -l 仅checkout代码

	5、 root登陆状态下回收站无法手动清空，命令行执行清空回收站

		rm -rf /home/reteyery/.local/share/Trash reteyery为用户名

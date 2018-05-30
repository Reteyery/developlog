1、handler泄露问题

    常规写法（会提示内存泄露问题）：
    private Handler mHandler = new Handler() {  
        @Override  
        public void handleMessage(Message msg) {  
            super.handleMessage(msg);  
        }  
    };  

    建议：
    private Handler mHandler = new Handler(new Handler.Callback() {  
        @Override  
        public boolean handleMessage(Message msg) {  
            // TODO Auto-generated method stub  
            return false;  
        }  
    }) ;

2、Windows下安装Cygwin ssh访问Linux服务器总结
    
    tips:
    1、以管理员的身份运行程序
    2、管理-Cygwin sshd，选择属性-登录身份-本地账户（否则连接net start sshd提示无权限）
    3、ssh连接linux命令， ssh leeyang@192.168.25.21

3、repo使用流程

    repo镜像安装访问 https://mirror.tuna.tsinghua.edu.cn/help/AOSP/
    安装完成后，建立工作目录，在目录下repo init
    最后 repo sync -c 完成代码同步
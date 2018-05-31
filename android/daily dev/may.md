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

4、linux打包命令

    FileNAme为压缩后的名称， DirName为原始文件夹名称
    .tar
    压缩：tar cvf FileName.tar FileName
    解压：tar xvf FileName.tar
    --------------------------------------------- 
    .gz
    解压1：gunzip FileName.gz 
    解压2：gzip -d FileName.gz 
    压缩：gzip FileName 
    .tar.gz 
    解压：tar zxvf FileName.tar.gz 
    压缩：tar zcvf FileName.tar.gz DirName 
    --------------------------------------------- 
    .bz2 
    解压1：bzip2 -d FileName.bz2 
    解压2：bunzip2 FileName.bz2 
    压缩： bzip2 -z FileName 
    .tar.bz2 
    解压：tar jxvf FileName.tar.bz2 
    压缩：tar jcvf FileName.tar.bz2 DirName 
    --------------------------------------------- 
    .bz 
    解压1：bzip2 -d FileName.bz 
    解压2：bunzip2 FileName.bz 
    压缩：未知 
    .tar.bz 
    解压：tar jxvf FileName.tar.bz 
    压缩：未知 
    --------------------------------------------- 
    .Z 
    解压：uncompress FileName.Z 
    压缩：compress FileName 
    .tar.Z 
    解压：tar Zxvf FileName.tar.Z 
    压缩：tar Zcvf FileName.tar.Z DirName 
    --------------------------------------------- 
    .tgz 
    解压：tar zxvf FileName.tgz 
    压缩：未知 
    .tar.tgz 
    解压：tar zxvf FileName.tar.tgz 
    压缩：tar zcvf FileName.tar.tgz FileName 
    --------------------------------------------- 
    .zip 
    解压：unzip FileName.zip 
    压缩：zip FileName.zip DirName 
    --------------------------------------------- 
    .rar 
    解压：rar a FileName.rar 
    压缩：rar e FileName.rar 

5、git操作命令

    checkout过程输入完整路径
    
    checkout远程分支
    查看分支 git branch -a
    同步分支 git checkout -b 远程分支
    删除分支 git branch -D 分支名称
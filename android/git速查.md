1、新建本地分支推送到远程仓库

    mkdir gitTest
    cd gitTest
    touch README
    git add README
    git config --global user.name "joker"
    git config --global user.email "729239206@qq.com"
    ssh-keygen -t rsa -C "729239206@qq.com" #将生成的密钥放到github或者其他代码托管工具，否则没有权限推送
    git remote add origin git@github.com:Reteyery/git.git #添加远程仓库git地址
    git push -u origin master #推送到远程仓库

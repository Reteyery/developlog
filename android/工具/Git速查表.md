##Git速查##

    mkdir gitTest
    cd gitTest
    touch README #创建文件
    cat README #查看文件内容
    git add README
    git config --global user.name "joker"
    git config --global user.email "729239206@qq.com"
    ssh-keygen -t rsa -C "729239206@qq.com" #将生成的密钥放到github或者其他代码托管工具，否则没有权限推送
    git remote add origin git@github.com:Reteyery/git.git #添加远程仓库git地址
    git push -u origin master #推送到远程仓库

    git push origin --delete 远程分支名称 #删除远程分支
    git log --pretty=oneline #查看近期提交记录
    git reflog #查看分支操作记录（在版本回退时，方便根据commit id回退）
    git log --graph --pretty=oneline --abbrev-commit #查看分支合并记录
    git reset --hard commit_id #版本回退
    git reset HEAD <file> #把暂存区的修改撤销掉（unstage），重新放回工作区

    ps:
    1.分支合并默认使用Fast forward模式，在这种模式下，删除分支后会丢失分支信息，禁用该模式，git会在merge时产生一个新的commit，分支历史信息会保留 eg: git merge --no-ff 被合并分支名称

    合并后 git log --graph --pretty=oneline --abbrev-commit #查看分支合并记录

    2.当手头工作没有完成，且遇到新的紧急任务比如修复bug，把工作现场git stash一下，然后修复bug，修复完成后，git stash pop回到工作现场（修复bug，一般创建新的bug分支进行修复，然后合并，最后删除分支）

    stash:将工作区的修改暂存起来 通过git stash pop恢复现场

    3.如果git pull提示no tracking information，则说明本地分支和远程分支的链接关系没有创建，用命令
    git branch --set-upstream-to origin/<branch-name> <branch-name> 

    
    
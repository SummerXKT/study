# 一，Git的概念
    Git是一个免费的，开源的，分布式版本控制系统,可以处理各种从小型到大型的项目。
    Git易于学习，占地面积小，性能极快，他具有廉价的本地库，方便的暂存区域和多个工作流分支等特性。
## 1.1，版本控制概念介绍
    版本控制是一种记录文件内容变化，以便将来查询特定版本修订情况的系统。最重要的就是记录文件的修改记录，方便查看历史版本和版本切换。
## 1.2，为什么使用版本控制
    方便团队多人开发
## 1.3，版本控制工具
* 集中式版本控制工具
    CSS，SVN，VSS
    这种工具是一个单一的集中管理的服务器，用来保存所有文件的修订版本，而协同工作的人需要通过客户端连接到这台服务器来实现文件的更新
    优点：每个人都可以在一定程度上看到项目中的其他人在做什么，对于管理员可以轻松的掌握每个开发人员的开发权限。
    缺点：如果服务器宕机，那么在这期间内，所有人都无法提交更新，无法协同工作
* 分布式版本控制工具
    Git
    客户端提取的不是最新版本的文件快照，而是把代码仓库完整的镜像过来，这样任何一处的协同工作的文件发生故障，事后都可以用其他用户的本地仓库进行恢复
    优点：服务器断网的情况下也可以进行开发（因为版本控制是本地进行的）；每个用户保存的都是完整的项目

## 1.4，Git的工作原理
    工作区（写代码）——>git add ——> 暂存区 ——> git commit ——>  本地库（历史版本）代码进入本地库就会生成历史版本，无法删除 ——> git push ——> 远程仓库
## 1.5，Git与代码托管中心
    代码托管中心是基于网络服务器的远程代码仓库，一般称为远程库
* 局域网
    GitLab
* 互联网
    GitHub（外网），Gitee 码云（国内网站）
# 二，Git常用的命令
    git config --global user.name 用户名         设置用户签名
    git config --global user.email 邮箱          设置用户签名
    git init                                    初始化本地库
    git status                                  查看本地库的状态
    git add 文件名                              将文件添加到暂存区
    git commit -m "日志信息" 文件名              提交到本地库
    git reflog    /log                              查看历史记录
    git reset -hard 版本号                       版本穿梭
## 3.1，设置用户签名
    git config -global user.name 用户名         设置用户签名
    git config -global user.email 邮箱          设置用户签名
    说明：签名的作用是区分不同操作者的身份，用户的签名信息在每一个版本的提交信息中能够看到，以此确认本次提交是谁做的。Git首次安装后必须设置一下用户签名，否则无法提交
    --》这里与将来登录GitHub或者其他代码托管中心的账号是没有关系的
## 3.2，初始化本地库
    基本语法:git init
    说明：将该文件目录的管理权限赋予Git本地仓库，生成的.git文件系统默认是隐藏的
## 3.3，查看本地库的状态
    基本语法:git status
    结果：On branch master --》说明当前提交在master分支下
         No commits yet   --》 说明还未提交
        Untracked files:
        (use "git add <file>..." to include in what will be committed)
                "git\345\210\206\346\224\257"
                "git\345\221\275\344\273\244"       --》说明文件仍然处于工作区，未被Git追踪


    提交完成后查看状态：$ git status
                        On branch master
                        nothing to commit, working tree clean
## 3.6，修改文件
修改完代码后：  
    $ git status
    On branch master
        hanges not staged for commit:
        (use "git add <file>..." to update what will be committed)
        (use "git restore <file>..." to discard changes in working directory)
                modified:   "git\345\221\275\344\273\244"            ————》这行为红色代表这次修改还未添加到暂存区
    此时需要重复添加暂存区，提交操作即可
    $ Git reflog
    41a900e (HEAD -> master) HEAD@{0}: commit: Git命令学习——提交至本地仓库-第一次修改      ————》此时指针指向第三次修改
    405e4bc HEAD@{1}: commit: Git命令学习——提交至本地仓库
    2e669d3 HEAD@{2}: commit (initial): Git命令学习——提交至本地仓库
## 3.7,版本穿梭
### 1，查看历史版本
    git reflog 查看版本信息
    git log    查看脚本详细信息
### 2，版本穿梭
    基本语法：git reset --hard 版本号
    结果：$ git reset --hard 405e4bc7957c27f67ca067ca10028c7db0cc67cd
            HEAD is now at 405e4bc Git命令学习——提交至本地仓库
        $ git log git分支
        commit 405e4bc7957c27f67ca067ca10028c7db0cc67cd (HEAD -> master)     此时已经变成了之前的版本
        Author: XC <2213065152@qq.com>
        Date:   Mon Jan 30 14:00:16 2023 +0800

        Git命令学习——提交至本地仓库

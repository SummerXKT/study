# 一，团队协作的机制
    团队内协作  
    跨团队协作
# 二，GitHub操作
## 2,1，创建远程仓库
    登录GitHub官网创建即可
## 2.2，远程仓库操作
    git remote -v               查看当前所有远程地址别名
    git remote add 别名 远程地址    起别名
    git push 别名 分支              推送本地分支的内容至远程仓库
    git clone 远程地址              将远程仓库的内容克隆到本地
    git pull 远程仓库地址别名 远程分支名    将远程仓库对于分支最新内容拉下来后与当前本地分支直接合并
### 2.2.1,创建远程仓库别名
    基本语法：git remote add 别名 远程地址 
    结果：$ git remote add GitHub-GitStudy https://github.com/SummerXKT/GitStudy.git

        $ git remote -v
        GitHub-GitStudy https://github.com/SummerXKT/GitStudy.git (fetch)
        GitHub-GitStudy https://github.com/SummerXKT/GitStudy.git (push)    代表fetch和push都可以用这个别名
### 2.2.2，推送本地库到远程库
    基本语法：$ git push GitHub-GitStudy master
    结果：
### 2.2.3，拉取远程库至本地库
    基本语法：git pull GitHub-GitStudy master
    结果：remote: Enumerating objects: 5, done.
        remote: Counting objects: 100% (5/5), done.
        remote: Compressing objects: 100% (3/3), done.
        remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
        Unpacking objects: 100% (3/3), 678 bytes | 45.00 KiB/s, done.
        From https://github.com/SummerXKT/GitStudy
        * branch            master     -> FETCH_HEAD
        78661f6..445ca2e  master     -> GitHub-GitStudy/master
        Updating 78661f6..445ca2e
        Fast-forward
        "git\345\210\206\346\224\257" | 4 +++-
        1 file changed, 3 insertions(+), 1 deletion(-)
### 2.2.4，克隆远程库到本地
    基本语法：git clone https://github.com/SummerXKT/GitStudy
    结果：Cloning into 'GitStudy'...
                remote: Enumerating objects: 19, done.
                remote: Counting objects: 100% (19/19), done.
                remote: Compressing objects: 100% (14/14), done.
                remote: Total 19 (delta 4), reused 15 (delta 3), pack-reused 0
                Receiving objects: 100% (19/19), 5.00 KiB | 5.00 MiB/s, done.
                Resolving deltas: 100% (4/4), done.
    clone干了三件事：1，拉取代码；2，初始化本地仓库；3，创建别名
        $ git remote -v
        origin  https://github.com/SummerXKT/GitStudy (fetch)
        origin  https://github.com/SummerXKT/GitStudy (push)


# 三，SSH免密登录
    基本语法：ssh-keygen -t rsa -C 2213065152@qq.com                  -t是指定用哪种加密算法；-C是描述
    结果：$ ssh-keygen -t rsa -C 2213065152@qq.com
        Generating public/private rsa key pair.
        Enter file in which to save the key (/c/Users/V0082049/.ssh/id_rsa):
        Created directory '/c/Users/V0082049/.ssh'.
        Enter passphrase (empty for no passphrase):
        Enter same passphrase again:
        Your identification has been saved in /c/Users/V0082049/.ssh/id_rsa
        Your public key has been saved in /c/Users/V0082049/.ssh/id_rsa.pub
        The key fingerprint is:
        SHA256:yaklW/oghqGPBwBXKef8f4AHJPkbxc8tQ5ttlPHA8Hk 2213065152@qq.com
        The key's randomart image is:
        +---[RSA 3072]----+
        |   ..o .  .ooo   |
        |. o = . o ..++   |
        |.. = + . + *o E  |
        |.   o +. oB +.   |
        |. .  ..=S  +     |
        |.. o  +Bo        |
        |... o =o .       |
        | o.. . o. .      |
        |...     ..       |
        +----[SHA256]-----+

生成.ssh文件：其中id_rsa是私钥，id_rsa.pub是公钥
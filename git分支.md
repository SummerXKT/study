# 一，什么是分支
    在版本控制的过程中，同时推送多个任务，我们此时就可以为每个任务创建其单独的分支，使用分支就意味着可以将自己的开发任务从开发主线中分离出来，开发自己的任务时不会影响主线分支的运行；可以理解为每个分支都是一个单独的副本。（分支的底层也是指针的引用）
# 二，分支的好处
    同时并行推进多个功能开发，提高开发效率
    各个分支在开发的过程中，如果某一个功能开发失败，不会对其他分支有任何的影响，失败的分支删除重新开始即可
# 三，分支的操作
    git branch 分支名               创建分支
    git branch -v                  查看分支
    git checkout 分支名             切换分支
    git merge 分支名                把制定的分支合并到当前分支

## 3.1,查看分支
    基本语法：git branch -v
    结果：$ git branch -v
        * master 405e4bc Git命令学习——提交至本地仓库     （*代表当前所在的分区）
## 3.2，创建分支
    基本语法:git branch xxq
    创建后查看结果：$ git branch -v
        * master 405e4bc Git命令学习——提交至本地仓库        （*代表当前所在的分区）
        xxq    405e4bc Git命令学习——提交至本地仓库
## 3.3，切换分支
    基本语法：git checkout xxq
    结果：$ git checkout xxq
            Switched to branch 'xxq'
            M       "git\345\221\275\344\273\244"
## 3.4，分支合并
    基本语法：git merge xxq 
    结果：
    11
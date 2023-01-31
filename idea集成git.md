# 一，在idea中集成git
## 1.1，忽略文件
   查看暂存区的文件---->git ls-files
   创建忽略文件————>.gitignore
   删除暂存区指定的文件夹————>git rm -r -f --cached .idea
## 1.2,idea中git的使用
   红色代表：文件未被追踪
   绿色代表：文件尚未提交本地库
   蓝色代表：文件与本地库不同
   蓝色的文件可以直接添加本地库
### 1.2.1，切换版本
   选中想要切换的版本，右击选择Checkout revision
### 1.2.2，Idea中如何使用分支
   创建和切换分支：右击项目选择Git，找到Repository里面，点击Branches
   合并分支：
    正常合并：(合并操作前需要先提交代码)找到Branches，切换当前分支为需要合并到的分支
            ，在Branches里选中需要合并的分支，右击选中merge into current
    冲突合并：11
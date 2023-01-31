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
    冲突合并：按照正常合并，出现冲突弹窗时点击Merge，手动合并代码即可
# 二，在idea中设置Github账号
   在setting中找到version control ，点击GitHub，添加账号，使用token登录
   这样需要在GitHub账号中设置token（Developer setting）
## 2.1，使用idea提交代码
   在VCS中找到share project on github 
   报错：Successfully created project 'study' on GitHub, 
        but initial push failed: unable to access 'https://github.com/SummerXKT/study.git/': 
        SSL certificate problem: unable to get local issuer certificate
   报错解决方式：：在Settring -> VersionControl ->GitHub中去掉：“Clone git repositories using ssh”即可
   这样的操作可以在远程仓库自动创建管理仓库
   提交代码至远程仓库时，需要将变更的代码提交到本地仓库，然后提交远程
   使用GitHub提交建议选择SSH的方式
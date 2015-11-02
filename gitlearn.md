##本地使用Git,并备份到Github
###在现有目录中初始化仓库
> $git init
###添加文件进行跟踪
> $git add *
###提交第一个版本
> $ git commit -m '第一个初始版本'
 “`
注意,在此之前，请一定要确认还有什么修改过的或新建的文件还没有git add ，否则提交的时候不会记录这些还没暂存起来的变化。这些修改过的文件只保留在本地磁盘。所以，每次准备提交前，先用git status看下，是不是都已暂存起来了， 后再运行提交命令git commit
 “`
###跳过使用暂存区域
$ git commit -a -m 'added new benchmarks'
git commit 加上-a 选项，Git 就会自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过git add 步骤

###如果要重命名文件(尚未提交加--cached)
> $git rm gitlearn.md --cached
或者用:
> $git mv gitlearn.md gitlearn01.md

###Git Status 中文乱码解决
> $git config --global core.quotepath false
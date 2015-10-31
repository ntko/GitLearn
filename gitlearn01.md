##本地使用Git,并备份到Github
###在现有目录中初始化仓库
> $git init
###添加文件进行跟踪
> $git add *
###提交第一个版本
> $ git commit -m '第一个初始版本'
###如果要重命名文件
> $git rm gitlearn.md --cache
或者用:
> $git mv
###Git Status 中文乱码解决
> $git config --global core.quotepath false
### Git相关资源
* <https://indepth.dev/becoming-a-git-pro-part-1-internal-git-architecture/>
* [使用git和github进行协同开发流程](http://segmentfault.com/a/1190000002413519)  
* [使用git和github管理自己的项目---基础操作学习](http://segmentfault.com/a/1190000003728094)  
* [使用git和github管理自己的项目---真实开发环境的策略](http://segmentfault.com/a/1190000003739324)  
* [廖雪峰的git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
* [GIT 的常规操作](http://www.cnblogs.com/wang_yb/p/3867221.html)
* [Git回滚远程版本](http://www.cnblogs.com/Alandre/p/5370274.html)
* [git rebase简介(基本篇)](https://blog.csdn.net/hudashi/article/details/7664631)
* [git rebase 使用详解](https://blog.csdn.net/chenansic/article/details/44122107)

### 本地使用Git,并备份到Github
#### <i class="icon-file"></i>在现有目录中初始化仓库
> git init
#### <i class="icon-file"></i>添加文件进行跟踪
> git add *
#### <i class="icon-file"></i>提交第一个版本
> git commit -m '第一个初始版本'  

注意,在此之前，请一定要确认还有什么修改过的或新建的文件还没有git add ，否则提交的时候不会记录这些还没暂存起来的变化。这些修改过的文件只保留在本地磁盘。所以，每次准备提交前，先用git status看下，是不是都已暂存起来了， 后再运行提交命令git commit
 
#### <i class="icon-file"></i>跳过使用暂存区域
> git commit -a -m 'added new benchmarks'
git commit 加上-a 选项，Git 就会自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过git add 步骤

####如果要重命名文件(尚未提交加--cached)
> git rm gitlearn.md --cached

或者用:
> git mv gitlearn.md gitlearn01.md

上面的语句相当于:

> mv README.md README  
> git rm README.md  
> git add README

#### <i class="icon-file"></i> Git Status 中文乱码解决
> git config --global core.quotepath false

#### <i class="icon-file"></i>查看提交历史

> git log  
> git log --pretty=oneline --abbrev-commit //可以简化输出为一行并简化id

一个常用的选项是-p，用来显示每次提交的内容差异。你也可以加上-2 来仅显示最近两次提交：
> git log -p -2 (注意需要按q退出命令模式)

#### <i class="icon-file"></i>提交到Github仓库

在注册了Github仓库之后,可以把我们的本地仓库和远程仓库进行同步.  
首先创建一个develop分支:  
> git checkout -b develop //创建并切换到develop分支  
然后提交本文件的修改:  
> git commit -a -m "测试提交最后修改到develop分支"  
添加一个到Github远程仓库的引用:  
> git remote add origin git@github.com:ntko/GitLearn.git  
然后运行如下命令推送:  
> git push -u origin develop  
结果报错了: ! [rejected]        develop -> develop (fetch first)  

根据提示fetch是不行的.因为fetch只是提取,但是并不合并到当前分支.因此需要用
git pull命令获取并自动合并:
> git pull -u origin develop

然后再次提交:
> git push -u origin develop  

显示成功了.这时,可以登录Github,从develop分支提交Pull request请求,然后再通过管理端合并到master分支.这样,就可以在Github帐户中的master分支中看到全部结果了.

最后,我们可以从master分支重新获取到当前本地仓库.
> git checkout master  
> git pull -u origin master  



<!-- git start -->
git 创建项目 并把内容提交到github上

如何用命令将本地项目上传到git
1、（先进入项目文件夹）通过命令 git init 把这个目录变成git可以管理的仓库

git init
2、把文件添加到版本库中，使用命令 git add .添加到暂存区里面去，不要忘记后面的小数点“.”，意为添加文件夹下的所有文件

git add .
3、用命令 git commit告诉Git，把文件提交到仓库。引号内为提交说明

git commit -m 'first commit'
4、关联到远程库

git remote add origin 你的远程库地址
补充： 目前提交需要个人令牌， 需要创建号自己的个人令牌（token）
如：
git remote add origin https://github.com/githubusername/demo.git
git remote add origin https://token@github.com/githubusername/demo.git
5、获取远程库与本地同步合并（如果远程库不为空必须做这一步，否则后面的提交会失败）

git pull --rebase origin master
6、把本地库的内容推送到远程，使用 git push命令，实际上是把当前分支master推送到远程。执行此命令后会要求输入用户名、密码，验证通过后即开始上传。

git push -u origin master
*、状态查询命令

git status
备：详细请参考 http://www.cnblogs.com/tugenhua0707/p/4050072.html

提交的时候如果报错
fatal: Couldn't find remote ref master 翻译过来就是：致命的：无法找到远程参考主，也就是报错的意思。错误的提示内容意思是找不到需要连接的对象。
解决方法有以下几种：
0.如果是新建的仓库（ repositories ）的话在pull代码的时候，出现这个提示，可以忽略不计，直接提交就可以。

1.检查本地GIT的配置

git config user.name/git config --global user.name

git config user.email/git config --gloabl user.email

使用以上命令来检查本地的用户名和邮箱是否填写正确

2.检查远程仓库配置

git remote -v
如果远程仓库信息有误，则删除本地仓库配置，并且设置相关地址

git remote rm origin
git remote add origin XXXX   
然后就可以提交成功了
<!-- git end -->
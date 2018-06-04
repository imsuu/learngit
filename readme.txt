Git is a version control system.
Git is free software.

创建版本库repository
1.首先，选择一个合适的地方，创建一个空目录
$ mkdir learngit
$ cd learngit
$ pwd
pwd命令用于显示当前目录

2.通过git init命令把这个目录变成Git可以管理的仓库
$ git init
如果你没有看到.git目录，那是因为这个目录默认是隐藏的，用ls -ah命令就可以看见

3.把文件添加到版本库
建议使用标准的UTF-8编码，所有语言使用同一种编码
第一步，用命令git add告诉Git，把文件添加到仓库：
$ git add readme.txt
使用命令git add <file>，注意，可反复多次使用，添加多个文件
第二步，用命令git commit告诉Git，把文件提交到仓库：
$ git commit -m "wrote a readme file"
git commit命令，-m后面输入的是本次提交的说明


git status命令查看仓库当前的状态
git diff 命令查看具体修改内容
$ git status
$ git diff readme.txt 

提交修改和提交新文件是一样的两步
第一步是git add
$ git add readme.txt
可查看状态
$ git status ；将要被提交的修改包括readme.txt
$ git commit -m "add distributed"
$ git status ;当前没有需要提交的修改，而且，工作目录是干净（working tree clean）的
。
Git is free software distributed under the GPL.
Git has a mutable index called stage.
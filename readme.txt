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
git log命令显示从最近到最远的提交日志
git log --pretty=oneline
在Git中，用HEAD表示当前版本上一个版本就是HEAD^，上上一个版本就是HEAD^^，当然往上100个版本写HEAD~100
$ git reset --hard HEAD^
$ cat readme.txt   ；查看内容

$ git reset --hard 1094a  ；1094a commit id 版本号 版本号没必要写全，前几位就可以了

Git提供了一个命令git reflog用来记录你的每一次命令
$ git reflog
e475afc HEAD@{1}: reset: moving to HEAD^
1094adb (HEAD -> master) HEAD@{2}: commit: append GPL
e475afc HEAD@{3}: commit: add distributed
eaadf4e HEAD@{4}: commit (initial): wrote a readme file

前面 commit id

工作区 add 暂存区
命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销，这里有两种情况：
一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
一种是readme.txt已经添加到暂存区后，再作了修改，现在，撤销修改就回到添加到暂存区后的状态。
总之，就是让这个文件回到最近一次git commit或git add时的状态。


命令git reset HEAD <file>可以把暂存区的修改撤销掉（unstage），重新放回工作区
git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用HEAD时，表示最新的版本。
再用git status查看一下，现在暂存区是干净的，工作区有修改
git checkout -- readme.txt 丢弃工作区的修改

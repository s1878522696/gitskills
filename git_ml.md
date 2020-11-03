#  git常用命令总结
## 基础篇(创建版本库和提交)
* `mkdir learngit`  创建一个文件夹learngit
* `pwd` 显示当前目录
* `git init` 把当前目录变成Git可以管理的仓库
* `git add` 告诉Git，把文件添加到仓库(可反复多次使用，添加多个文件)；
* `git commit -m` 告诉Git，把文件提交到仓库  `-m`后面加本次提交的说明
* `git status` 时刻掌握仓库当前的状态(暂存区的状态)
* `git diff`  后面加当前状态有变化的文件名，可以看到哪里修改过了
* `cat` +文件名 可以看到当前文件的内容(必须是提交过得文件才可以---- add)最起码在暂存区

## (版本回退)
* `git log`  提交历史，历史记录查看(显示从最近到最远的提交日志)
* `git reset --hard commit_id`  (git reset)回退当前版本，上一个版本就是HEAD^，
上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100。
commit_id 版本ID (唯一标识号)
* `git reflog` 命令历史，记录你的每一次命令(提交记录，版本回退等)
* `git diff HEAD -- files` 查看files文件夹，工作区和版本库的区别；
* `git checkout -- files` 当你改乱了工作区某个文件的内容，可以撤销或者返回的命令
* `git reset HEAD files` 当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，
想丢弃修改命令；
* `git rm `  +`git commit `文件夹名字  删除一个文件夹

## 远程仓库
* `git remote add origin git@server-name:path/repo-name.git` 本地库要关联一个远程库的命令，
{git@server-name:path/repo-name.git}仓库地址
* `git push -u origin master` 第一次推送master分支的所有内容
* `git push origin master` 后面可以用此命令推送
* `git clone` +地址 克隆一个本地库
* `ls` 输出当前文件内的文件名

## 分支管理
* `git branch` 查看分支
* `git branch <name>` 创建分支
* `git check <name>` 或者 `git switch <name>` 切换分支
* `git checkout -b <name` 或者 `git switch -c <name>` 创建+切换分支
* `git merge <name>` 合并某分支到当前分支
* `git branch -d <name>` 删除分支
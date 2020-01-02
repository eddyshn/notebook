# 版本回退

## reset

**适用场景:** 如果想恢复到之前某个提交的版本，且**那个版本之后提交的版本我们都不要**了

在Git中，用**HEAD**表示**当前版本**，上一个版本就是**HEAD^**，上上一个版本就是**HEAD^^**，当然往上100个版本写100个^比较容易数不过来，所以写成**HEAD~100**。

git reset --hard <目标版本>

git reset --hard HEAD^^

git reset --hard HEAD~100

参考 [简书](https://www.jianshu.com/p/c2ec5f06cf1a)

## revert

**适用场景:** 如果我们想撤销之前的某一版本，但是又**想保留该目标版本后面的版本**，记录下这整个版本变动流程。

**git revert -n 版本号**

[参考](https://blog.csdn.net/yxlshk/article/details/79944535)

# 撤销修改

## git checkout -- file

- 一种是`readme.txt`自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

- 一种是`readme.txt`已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。
- git checkout -- *.*
- `git checkout -- *.*`

## git reset(mixed) HEAD <file>

把暂存区的修改回退到工作区

git reset --hard

# 分支管理

- 创建分支 `git branch <branch>`
- 删除会支 `git branch -d <branch>`
- 查看本地和远程的所有分支`git branch -a`
- `git branch`
- `git bracn -r`

# git diff

# git log(--graph --pretty=oneline --abbrev-commit)

- 查看指定文件的历史记录
  - git log --pretty=oneline `<file>`

# 远程仓库

- git pull origin  <远程分支名>:<本地分支名> --rebase
- git push origin <本地分支名>:<远程分支名>
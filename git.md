[toc]



# 1. 分支管理

## 1.1 创建分支

## 1.2 合并分支

1. 更新要合并的两个分支到最新
2. `git merge <source branch> --no-ff -m 'log message'`

> --no-ff 禁用`Fast forward`模式, Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。

## 1.3 删除分支

1. 删除本地分支

   `git branch -d <branch_name>`

2. 删除远程分支

   `git push origin -d <branch_name>`



# 2. 标签管理

## 2.1 创建标签

```
git tag <name>
git tag <name> <commit id>
git tag -a <tag-name> -m <tag message> <commit id(optional)>
```



## 2.2 查看标签

```
git tag
git show <tagname>
```

## 2.3 删除标签

```
git tag -d <tag-name>
```



# 3. 版本回退

参考 [简书](https://www.jianshu.com/p/c2ec5f06cf1a) [CSDN](https://blog.csdn.net/yxlshk/article/details/79944535)

## 3.1 未add

```
git checkout -- <file>
git checkout .
git checkout *.*
```

> git restore 是git 2.23中的新命令， 这里和checkout做用一样。

## 3.2 已add未commit

```
git reset
git reset --mixed
git reset HEAD
git reset HEAD <file>

```

> reset 不加参数(mixed)：保留工作目录，并清空暂存区。也就是说，工作目录的修改、暂存区的内容以及由 **reset** 所导致的新的文件差异，都会被放进工作目录。简而言之，就是「把所有差异都混合（mixed）放在工作目录中」。

## 3.3 恢复到之前某个提交的版本

```
git reset --hard <目标版本>
git reset --hard HEAD^^
git reset --hard HEAD~100
```

> 适用场景: 如果想恢复到之前某个提交的版本，且**那个版本之后提交的版本我们都不要**了
>
> 当你在 **reset** 后面加了 **--hard** 参数时，你的stage区和工作目录里的内容会被完全重置为和**HEAD**的新位置相同的内容。换句话说，就是你的没有**commit**的修改会被***全部擦掉***。
>
> > 在Git中，用**HEAD**表示**当前版本**，上一个版本就是**HEAD^**，上上一个版本就是**HEAD^^**，当然往上100个版本写100个^比较容易数不过来，所以写成**HEAD~100**。



## 3.4 撤销某个特定版本的修改

`git revert -n <commit id>`

> 适用场景: 如果我们想撤销之前的某一版本，但是又**想保留该目标版本后面的版本**，记录下这整个版本变动流程。



# git diff

# git log(--graph --pretty=oneline --abbrev-commit)

- 查看指定文件的历史记录
  - git log --pretty=oneline `<file>`

# 远程仓库

- git pull origin  <远程分支名>:<本地分支名> --rebase
- git push origin <本地分支名>:<远程分支名>



# git tag

1. 创建标签

   ```
   git tag <name>
   git tag <name> <commit id>
   git tag -a <tag-name> -m <tag message> <commit id(optional)>
   ```

   

2. 查看标签

   ```
   git tag
   git show <tagname>
   ```

3. 删除标签

   ```
   git tag -d <tag-name>
   ```

   




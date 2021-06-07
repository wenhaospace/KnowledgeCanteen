# Git 手册 - 50必知的Git命令

**Git 是一个分布式版本控制系统，可帮助开发人员在各种规模的项目上进行协作。**



Linux 内核的开发者 Linus Torvalds 在 2005 年创建了 Git，以帮助控制 Linux 内核的开发。



## 什么是分布式版本管理系统?

分布式版本控制系统是一种帮助您对项目中 *文件所做更改*  进行跟踪的系统。

此更改历史记录保存在您的本地计算机上，让您可以轻松地恢复到项目的先前版本，以防出现问题。

Git 让协作变得简单。团队中的每个人都可以保留他们在本地机器上工作的存储库的完整备份。然后，借助像 BitBucket、GitHub 或 GitLab 这样的外部服务器，他们就可以安全地将存储库存储在一个地方。

这样，团队的不同成员可以将其复制到本地，并且每个人都可以清楚地了解整个团队所做的所有更改。

Git 有许多不同的命令可供您使用。而且我发现这 50 个是我最常使用的（因此记住它们对工作很有帮助）。

所以我把它们写下来，并认为最好与社区分享它们。我希望你觉得它们有用——享受吧。



## 如何检查您的 Git 配置：

下面的命令返回有关您的 git 配置的信息列表，包括用户名和电子邮件：



```git
git config -l
```



## 如何设置您的 Git 用户电子邮件：



```
git config --global user.name "yourname"
```



## 如何在 Git 中缓存您的登录凭据：

您可以将登录凭据存储在缓存中，这样您就不必每次都输入它们。只需使用此命令：



```
git config --global credential.helper cache
```



## 如何初始化 Git 存储库：

一切从这里开始。第一步是在您的项目根目录中本地初始化一个新的 Git 存储库。您可以使用以下命令执行此操作：



```
git init
```



## 如何在 Git 中将文件添加到暂存区：

下面的命令将向暂存区添加一个文件。只需将 f`ilename_here` 替换为要添加到暂存区的文件的名称。



```
git add filename_here
```



## 如何在Git中将所有文件添加暂存区:

如果要将项目中的所有文件添加到暂存区，可以使用通配符 `.`并且将为您添加每个文件。



```
git add .
```



## 如何仅将某些文件添加到 Git 中的暂存区:

使用下面命令中的星号，您可以将所有以“fil”开头的文件添加到暂存区。



```
git add fil*
```



## 如何在 Git 中检查存储库的状态：

此命令将显示当前存储库的状态，包括暂存、未暂存和未跟踪文件。



```
git status
```



## 如何在 Git 的编辑器中提交更改：

此命令将在终端中打开一个文本编辑器，您可以在其中编写完整的提交消息。

提交消息由`更改情况的简短摘要`、`一个空行`和`更改的完整描述`组成。



```
git commit
```



## 如何在 Git 中使用message的方式提交更改：

您可以在不打开编辑器的情况下添加提交消息。此命令仅允许您为提交消息指定简短摘要。



```
git commit -m "your commit message here"
```



## 如何在 Git 中提交更改（并跳过暂存区）：

您可以使用 `-a` 和 `-m` 选项使用单个命令添加和提交被跟踪的文件。



```
git commit -a -m"your commit message here"
```



## 如何在 Git 中查看你的提交历史：

此命令显示当前存储库的提交历史记录：



```
git log
```



## 如何查看您的提交历史记录，包括 Git 中的更改：

此命令显示提交的历史记录，包括所有文件及其更改。



```
git log -p
```



## 如何在 Git 中查看 某一次的提交 记录：

此命令显示某次特定的提交。
将 `commit-id` 替换为您在提交历史中找到的在单词 commit 之后的 ID。



```
git show commit-id
```



## 如何在 Git 中查看日志统计信息：

此命令将 显示Git 日志中有关每次提交中更改的一些统计信息，包括更改的行和文件名。



```
git log --stat
```



## 如何在 Git 中使用“diff” 来在提交更改之前 查看 当前所做的更改：

git diff 默认仅显示未暂存的更改。



您可以将文件名作为参数传递以来查看特定文件的更改。



我们可以使用 `--staged` 选项调用 diff ，来查看任何阶段性更改。



```
git diff
git diff all_checks.py
git diff --staged
```



## 如何使用“git add -p”查看更改：

此命令会打开一个提示并询问您是否要暂存更改，并包括其他选项。



```
git add -p
```



## 如何从 Git 中的当前工作树中删除跟踪的文件：

此命令需要提交消息来解释文件被删除的原因。



```
git rm filename
```



## 如何在 Git 中重命名文件：

此命令会暂存更改，而且它需要提交消息说明。



```
git mv oldfile newfile
```



## 如何忽略 Git 中的文件：

创建一个 .gitignore 文件并将需要忽略的文件名写进该文件。



## 如何在 Git 中恢复未暂存的更改：

```
git checkout filename
```



## 如何在 Git 中恢复阶段性的更改：

您可以使用 `-p` 选项标志来指定要重置的更改。



```
git reset HEAD filename
git reset HEAD -p
```



## 如何在 Git 中修改最近的提交：

`git commit --amend` 允许您修改和添加对最近提交的更改。



```
git commit --amend
```



!!注意!!：使用`amend`修复本地提交很棒，您可以在修复后将其推送到共享存储库。但是你应该避免修改已经公开的提交。



## 如何回滚 Git 中的最后一次提交记录：

`git revert` 将创建一个与给定提交中的所有内容相反的新提交。

我们可以使用像这样的 head 别名来恢复最新的提交：



```
git revert HEAD
```



## 如何在 Git 中回滚到旧的提交记录：

您可以使用其`commit id` 还原旧提交。该操作将会打开编辑器，以便您可以添加提交消息。



```
git revert comit_id_here
```



## 如何在 Git 中创建新分支：

默认情况下，您有一个分支，即主分支。使用此命令，您可以创建一个新分支。 Git 不会自动切换到它 — 您需要使用如下命令进行手动切换。



```
git branch branch_name
```



## 如何在 Git 中切换到新创建的分支：

当您想使用不同的或新创建的分支时，您可以使用以下命令：



```
git checkout branch_name
```



## 如何在 Git 中列出所有分支：

您可以使用 `git branch` 命令查看所有创建的分支。它将显示包含所有分支的列表，并用星号标记当前分支并以绿色突出显示。



```
git branch
```



## 如何在 Git 中创建一个分支并立即切换到它：

在如下单个命令中，您可以立即创建并切换到新分支。



```
git checkout -b branch_name
```



## 如何在 Git 中删除分支：

当您完成一个分支的工作并合并它时，您可以使用以下命令将其删除：

```
git branch -d branch_name
```



## 如何在 Git 中合并两个分支：

要将当前所在分支的历史记录与目标分支(branch_name)合并，您需要使用以下命令：



```
git merge branch_name
```



## 如何在 Git 中将提交日志以图形的形式显示：

我们可以使用 `--graph` 来获取提交日志以显示为图表。以及-`-oneline` 来将提交消息限制为一行。



```
git log --graph --oneline
```



## 如何将提交日志显示为 包含Git 中所有分支的图表：

与上面的命令相同，但这是对所有分支使用。



```
git log --graph --oneline --all
```



## 如何中止 Git 中的冲突合并：

如果要放弃合并并重新开始，可以运行以下命令：



```
git merge --abort
```



## 如何在 Git 中添加远程存储库：

此命令将远程存储库添加到您的本地存储库（只需将 `https://repo_here` 替换为您的远程存储库 URL）。



```
git add remote https://repo_here
```



## 如何在 Git 中查看远程 URL：

您可以使用以下命令查看本地存储库的所有远程存储库：



```
git remote -v
```



## 如何在 Git 中获取有关远程存储库的更多信息：

只需将 `origin` 替换为获得的远程存储库的名称，并运行 git remote -v 命令。



```
git remote show origin
```



## 如何在 Git 中将更改推送到远程存储库：

当您的所有工作都准备好保存在远程存储库中时，您可以使用以下命令推送所有更改：



```
git push
```



## 如何从 Git 中的远程存储库中拉取更改：

如果其他团队成员正在您的存储库上工作，您可以使用以下命令拉去对远程存储库所做的最新更改：



```
git pull
```



## 如何查看 Git 正在跟踪的远程分支：

此命令显示 当前Git所跟踪存储库的所有远程分支的名称：



```
git branch -r
```



## 如何在 Git 中获取远程仓库更改：

此命令将从远程存储库下载更改，但不会在本地分支上执行合并（因为 `git pull` 会这样做）。



```
git fetch
```



## 如何在 Git 中检查远程仓库的当前提交日志：

在每一次提交后，Git 会建立一个日志。您可以使用以下命令查找远程存储库日志：



```
git log origin/main
```



## 如何在 Git 中将远程仓库与本地仓库合并：

如果远程存储库有您想要与本地合并的更改，则此命令将为您执行此操作：



```
git merge origin/main
```



## 如何在不自动合并的情况下，在Git中获取远程分支的内容：

这使您可以更新远程分支而无需将任何内容合并到当地分支机构。注意您可以调用 `git merge` 或 `git checkout` 来进行合并。



```
git remote update
```



## 如何在 Git 中将新分支推送到远程仓库：

如果要将分支推送到远程存储库，可以使用以下命令。请记住添加 `-u` 以创建上游分支：



```
git push -u origin branch_name
```



## 如何在 Git 中删除远程分支：

如果您不再需要远程分支，可以使用以下命令将其删除：



```
git push --delete origin branch_name_here
```



## 如何使用 Git rebase:

您可以使用 git rebase 将完成的工作从一个分支转移到另一个分支。



```
git rebase branch_name_here
```



如果您没有正确执行 Git Rebase，它会变得非常混乱。在使用这个命令之前，我建议你重新阅读[这里](https://git-scm.com/book/it/v2/Git-Branching-Rebasing)的官方文档。



## 如何在 Git 中以交互方式运行 rebase：

您可以使用 `-i`选项 标志以交互方式运行 git rebase。它将打开编辑器并显示一组您可以使用的命令。



```
git rebase -i master
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
# d, drop = remove commit
```



## 如何在 Git 中强制推送请求：

此命令将强制推送请求。这通常适用于拉取请求分支，因为其他人不会克隆这些分支。但这适用于在公共仓库上使用。



```
git push -f
```



## 总结
这些命令可以显着提高您在 Git 中的工作效率。您不必全部记住它们——这就是我编写此手册的原因。将此页面加入书签以备将来参考或根据需要打印。
























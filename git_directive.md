| 命令                                                    | 说明                                                         |
| ------------------------------------------------------- | ------------------------------------------------------------ |
| git config --global user.name "Your Name"               | 设置用户名                                                   |
| git config --global user.email "email@example.com"      | 设置邮箱                                                     |
| git init                                                | 初始化一个git仓库                                            |
| git add filename                                        | 添加文件到暂存区                                             |
| git commit -m "description"                             | 提交文件到分支(description是描述,若果描述中含有空格则必须加引号 没有空格可以加引号) |
| git commit --amend                                      | 修改最后一次提交到版本库的注释(也可以将当前git add过的文件放到最后一次提交的版本库里面) 是在vi编辑器里面操作的 |
| git status                                              | 查看状态                                                     |
| git diff [filename]                                     | 查看分支与暂存区的区别(如果传递了文件名则查看具体文件的区别,如果没有穿文件名则查看所有文件的区别) |
| git log                                                 | 查看版本日志信息                                             |
| git log -n                                              | 显示最后第几次提交信息(n是正整数)                            |
| git log --pretty=oneline                                | 显示简洁的日志信息                                           |
| git reflog                                              | 查看所有操作日志信息                                         |
| git reset --hard HEAD^                                  | 恢复到上一个版本 HEAD^^上两个版本 HEAD~100上100个版本        |
| git reset --hard commit_id                              | 恢复到具体版本号                                             |
| git diff HEAD -- filename                               | 查看工作区和版本库最新版本的区别 HEAD指向当前版本(也可以查看具体某个版本的区别 如git diff HEAD-50 -- filename/git diff commit_id -- filename) 在写的时候--也可以省略，如果查看与最后一次版本库的区别也可以简化成git diff filename |
| git checkout -- filename                                | 丢弃工作区最近一次的修改 版本库里面有这个文件才能这样操作    |
| git reset HEAD filename                                 | 丢弃暂存区的文件(修改已经添加到暂存区，想要撤销修改先要在暂存区丢弃，然后在工作区丢失修改) |
| git rm filename                                         | 从版本库删除文件(删除之后还要用 git add 和 git commit指令提交到版本库) |
| git remote add origin git@github.com:nesxiaogu/test.git | 关联远程库 origin是自定义的远程库名 origin后面的是远程库的地址 |
| git push -u origin master                               | 推送本地库内容到远程库 origin远程库名 master主分支 第一次推送加u参数作用的关联本地和远程的master分支 以后每次就不需要加 |
| git clone git@github.com:nesxiaogu/text.git             | 克隆远程库到本地(会连项目目录一起克隆) clone后面的是远程库的地址 |
| git branch name                                         | 创建名为name的分支                                           |
| git branch                                              | 查看所有分支 当前分支前面带 * 号                             |
| git checkout name                                       | 切换到name分支                                               |
| git checkout -b name                                    | 创建name分支并切换到name分支                                 |
| git merge name                                          | 合并name分支到当前分支 将name分支和master合并 合并分支需要在master分支下面合并 |
| git branch -d name                                      | 删除name分支 (远程仓库分支需要手动删) 不能在当前分支删除当前分支 |
| git branch -D name                                      | 强行删除那么分支 用于name分支还没有合并之前                  |
| git push origin :name                                   | 删除远程仓库的name分支                                       |
| git log --graph                                         | 查看分支合并图                                               |
| git log --graph --pretty=oneline --abbrev-commit        | 简化合并图信息                                               |
| git merge --no-ff -m "description" name                 | name分支与当前分支合并，但是禁止使用快速模式 由于会生成一个新的commit记录所以要加m参数和描述 |
| git stash                                               | 存储当前修改不提交(用户一个分支进行到一半的时候调试bug分支存储当前修改) |
| git stash list                                          | 查看存储列表                                                 |
| git stash apply                                         | 恢复当前分支存储内容 stash列表内容不删除                     |
| git stash apply stash@{0}                               | 恢复指定stash                                                |
| git stash drop                                          | 删除当前分支stash列表内容                                    |
| git stash drop stash@{0}                                | 删除stash列表指定stash                                       |
| git stash pop                                           | 恢复当前分支存储内容并删除stash列表内容                      |
| git remote                                              | 查看远程仓库信息                                             |
| git remote -v                                           | 显示详细的远程仓库信息                                       |
| git remote rm origin                                    | 删除已关联的远程库名                                         |
| git tag                                                 | 查看标签                                                     |
| git tag name                                            | 打标签(版本号) name为标签名                                  |
| git tag name commit_id                                  | 给指定的历史打版本                                           |
| git show tagname                                        | 查看标签信息                                                 |
| git tag -a tagname -m "description"                     | -a指定标签名 -m 指定说明文字                                 |
| git tag -s tagname -m "description"                     | 指定PGP签名标签                                              |
| git tag -d tagname                                      | 删除标签                                                     |
| git push origin tagname                                 | 推送标签到远程仓库                                           |
| git push origin --tags                                  | 推送本地所有为推送的标签到远程                               |
| git push origin :refs/tags/tagname                      | 删除远程仓库的标签                                           |
| git pull origin name                                    | 远程库分支或者版本号更新到本地                               |
| git config --global color.ui true                       | 改变git显示文字的颜色                                        |
| git add -f filename                                     | 强制添加忽略文件到git                                        |
| git check-ignore -v filename                            | 检查具体被忽略的规则                                         |
| git config --global alias.st status                     | 配置别名 敲st相当于敲status 别名控制两个单词要加引号         |
| ls                                                      | 查看目录文件 不包含隐藏文件                                  |
| ls -la                                                  | 查看目录及文件 包含隐藏文件                                  |
| rm filename                                             | 删除文件                                                     |
| ssh-keygen -t rsa -C "youremail@example.com"            | 生成ssh秘钥                                                  |

### 忽略文件

```text
.gitignore(设置忽略特殊文件)
格式 #号表示注释
# python:
*.py[cod]
*.so
*.egg
```

### 相关配置文件

```text
当前仓库git配置文件 .git/config
用户git配置文件 /c/Users/Administrator/.gitconfig
```


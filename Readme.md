# 《progit》相关笔记
## git 基础
> 获取Git仓库
1. 在已存在目录中初始化仓库  
   `git init`  
2. 克隆现有仓库  
   `git clone <url>`  
>  记录每次更新到仓库  
1. 检查当前文件状态  
`git status`  
2. 跟踪新文件  
`git add xxx`
3. 状态简览  
   新添加的未跟踪文件前面有 **??** 标记，新添加到暂存区中的文件前面有 **A** 标记，修改过的文件前面有 **M** 标记。
4. 忽略文件  
   需要创建一个名为 **.gitignore** 的文件
5. 提交更新  
   `git commit`  
   commit命令后添加-m选项，将提交信息与命令放在同一行  
   `git commit -m "first commit"`  
6. 跳过使用暂存区域  
   在提交时，给git commit加上-a选项，Git就会自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过git add步骤。但有时这个选项会将不需要的文件添加到提交中。  
7. 移除文件   
   `git rm`  
   如果要删除之前修改过或已经放到暂存区的文件，必须使用强制删除-f选项。  
   让文件保留在磁盘，又不想让Git继续跟踪。（尤其是忘记添加.gitignore文件时）。使用--cached选项  
   `git rm --cached README`  
8. 移动文件  
   在Git中对文件改名  
   `git mv file_from file_to`  
> 查看提交历史  
1. 回顾提交历史  
   `git log`  
   <center> git log 的常用选项  

   | 选项 | 说明 |
   |------|------|
   | -p | 按补丁格式显示每个提交引入的差异。 |
   | --stat | 显示每次提交的文件修改统计信息。 |
   | --shortstat | 只显示 --stat 中最后的行数修改添加移除统计。 |
   | --name-only | 仅在提交信息后显示已修改的文件清单。 |
   | --name-status | 显示新增、修改、删除的文件清单。 |
   | --abbrev-commit | 仅显示 SHA-1 校验和所有 40 个字符中的前几个字符。 |
   | --relative-date | 使用较短的相对时间而不是完整格式显示日期（比如“2 weeks ago”）。 |
   | --graph | 在日志旁以 ASCII 图形显示分支与合并历史。 |
   | --pretty | 使用其他格式显示历史提交信息。可用的选项包括 oneline、short、full、fuller 和 format（用来定义自己的格式）。 |
   | --oneline | --pretty=oneline --abbrev-commit 合用的简写。 |
2. 限制输出长度  
   <center> 限制git log 输出的选项  

   选项|说明
   ---|---
   -n|仅显示最近的 n 条提交。
   --since, --after|仅显示指定时间之后的提交。
   --until, --before|仅显示指定时间之前的提交。
   --author|仅显示作者匹配指定字符串的提交。
   --committer|仅显示提交者匹配指定字符串的提交。
   --grep|仅显示提交说明中包含指定字符串的提交。
   -S|仅显示添加或删除内容匹配指定字符串的提交。

> 撤销操作    
1. 注意：有些操作是不可逆的，使用撤销操作前最好再查一下  
2. 新的提交替换旧的提交 例子如下：  
   `git commit -m 'inital commit' `        
   `git add forgotten_file   `  
   `git commit --amend`    

> 远程仓库的使用  
1. 查看远程仓库  
   `git remote`
2. 添加远程仓库  
   `git remote add <shortname> <url>`
3. 从远程仓库中抓取与拉取
   `git fetech <remote>`
4. 推送到远程仓库  
   `git push <remote> <branch>`  
5. 远程仓库的重命名与移除  
   `git remote rename`  
> 打标签  
1. 列出标签  
   `git tag`  
2. 创建标签  
   创建附注标签：  
   `git tag -a v1.0 "my version 1.0" `  
   创建轻量标签，只需要提供标签名字：  
   `git tag v1.0.0`  
3. 共享标签  
   `git push origin <tagname>`  
   一次性推送很多标签：  
   `git push origin --tags`  
4. 删除标签  
   `git tag -d <tagname>`  
> Git别名  
1. 一些例子：  
   `git config --global alias.co checkout`  
   `git config --global alias.ct commit`  




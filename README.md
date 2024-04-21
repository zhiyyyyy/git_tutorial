# git基本使用总结
## 本地仓库创建
* 初始化仓库  
`git init`
* 检查当前文件状态  
`git status`
* 跟踪新文件到暂存区 **或** 添加已跟踪却被修改过的文件到暂存区，“点”表示所有目标文件但不包含.gitignore里的忽略文件  
`git add .`
* 提交更新  
`git commit -m "commit information"`
* 一步暂存加提交，但未跟踪文件需先add  
`git commit -a -m "commit information`
* 覆盖提交：如果只想修改提交信息则加上括号内容；如果想添加一个新的暂存，根据是否需要修改提交信息选择是否加上括号内容  
`git commit --amend (-m "new commit information“)`
* 查看提交历史，撤销的提交不显示  
`git log`
* 查看引用日志，查看撤销提交记录  
`git reflog`
## .gitignore规则
    # 忽略所有的 .a 文件
    *.a
    # 但跟踪所有的 lib.a，即便你在前面忽略了 .a 文件
    !lib.a
    # 只忽略当前目录下的 TODO 文件，而不忽略 subdir/TODO
    /TODO
    # 忽略任何目录下名为 build 的文件夹
    build/
    # 忽略 doc/notes.txt，但不忽略 doc/server/arch.txt
    doc/*.txt
    # 忽略 doc/ 目录及其所有子目录下的 .pdf 文件
    doc/**/*.pdf
## 撤销操作
* 撤销首次提交  
`git update-ref -d HEAD`
* 取消暂存，不指定文件则取消所有；HEAD可选，但从未提交时会报错；已有提交加不加HEAD都一样  
`git reset (HEAD) (<file>)`
* 从暂存区删除但保留文件，文件变为未跟踪  
`git rm --cached <file>`
* 回退版本：^个数表示回退版本次数，^^^表示回退上上上个版本；或用数字表示 HEAD^^ 等同于 HEAD~2；只回退提交和暂存记录，工作区文件不变；--hard会连同工作区一起回退，**慎用！！！**  
`git reset (--hard) HEAD^`
* 恢复指定文件到最新的提交状态，丢弃所有**未提交**的更改；”点“表示所有  
`git restore <file>` `git restore .`
* 将文件恢复到特定提交commit的状态，用想要的提交版本号替代commit（去掉尖括号）  
`git restore --source=<commit> <file>`
## 删除仓库
`rm -rf .git`

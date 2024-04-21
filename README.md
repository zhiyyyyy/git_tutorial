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
* 一步暂存加提交，未跟踪文件还需先add  
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

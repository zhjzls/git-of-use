# git-of-use
    git安装使用
        1. 初始化项目（建立git仓库）
            git init
        2. 添加新文件后，添加到版本库
            git add <文件名>
        3. 提交最新改动
            git commit -m "备注内容"
        4. 与远程仓库进行关联
            git remote add origin <url>     // url 可以为https的链接 ，也可为git://xx链接，默认的git:// 使用ssh
                (git pull --rebase origin master)
        5. 将本地仓库推送到远端
            git push origin master
            (初次使用：git push -u origin master)
            push时的 -u 参数表示把origin这个主机设置为默认远程主机，以后用 git push 就可以把当前分支推送到这个主机上的对应分支，是一种简化写法。
        6. 修改文件后进行新旧对比
             git diff <文件名>
        7. 查看修改日志
             git log 

    
        8. 版本回退
             git reset --hard HEAD^  // HEAD^表示上一个版本   HEAD^^ 表示上上一个版本  以此类推……
             git reset --hard <版本号>   // commit值 前5位
        9. 查看每一次命令记录
             git reflog
        10. 工作区和暂存区的概念
             工作区表示当前操作区间
             暂存区包含本地版本库的暂存区和默认master分支（后面可能还有其他开发分支）
        11. 跟踪修改
             每次修改，如果不用 git add 将改动添加到暂存区，git commit 提交的时候就不会提交本次修改
             git commit 提交时只看暂存区的数据状态
             git diff HEAD -- <文件名>      // 查看工作区和版本库最新版本的区别 
        12. 撤销修改
             撤销修改分为3个阶段
                1. 修改文件后没有添加到暂存区   
                    git checkout -- <文件名>
                        // git checkout其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。
                2. 修改文件后添加到暂存区（git add <文件名>） 但没有提交本次修改
                    git reset HEAD <文件名>     // 此时暂存区是干净的，但工作区有修改，需要丢弃工作区的修改
                    git checkout --<文件名>
                3. 修改文件后从暂存区提交到分支了(git commit -m "xxx")
                    git reset --hard HEAD^ 
                    或： git reset --hard <版本号>  // 可通过git log 查看对应的版本号，取前5位即可


    ## 分支管理
        
        13. 创建切换分支
             git checkout -b dev    // 创建&&切换分支
            等同于：
                git branch dev      // 创建分支
                git checkout dev      // 切换分支
             git branch     // 查看当前分支
             git merge dev  // 合并分支 （将dev 合并到当前分支）
             git branch -d <分支名>    // 删除分支
    Questions：
        1.每次push都需要重新登录——通过设置ssh公秘钥的方式更方便
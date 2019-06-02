# git-of-use
    git安装使用
        1. 初始化项目（建立git仓库）
            git init
        2. 添加新文件后，添加到版本库
            git add <文件名>
        3. 提交最新改动
            git commit -m "备注内容"
        4. 与远程仓库进行关联
            git remote add origin <url>
                (git pull --rebase origin master)
        5. 将本地仓库推送到远端
            git push origin master
            (初次使用：git push -u origin master)
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
                2. 修改文件后添加到暂存区（git add <文件名>） 但没有提交本次修改
                    git reset HEAD <文件名>     // 此时暂存区是干净的，但工作区有修改，需要丢弃工作区的修改
                    git checkout --<文件名>
                3. 修改文件后从暂存区提交到分支了(git commit -m "xxx")
                    git reset --hard HEAD^ 
                    或： git reset --hard <版本号>  // 可通过git log 查看对应的版本号，取前5位即可

                    test撤销： mk9iiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiiii9i
    Questions：
        1.每次push都需要重新登录——通过设置ssh公秘钥的方式更方便
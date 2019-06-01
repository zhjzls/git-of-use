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
             git reset --hard HEAD

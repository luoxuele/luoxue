# git 
    git config --global user.name "luoxuele"
    git config --global user.emal "993650799@qq.com"
    git config --global -l


    git add .


    git
        add
        commit
        push

        pull


# 创建仓库
    git init xxx    初始化本地仓库
    git clone git@github.com:luoxuele/git_learning.git


# 文件的四种状态
    untracked   未跟踪
    unmodify
    modified
    staged


git status

git add .   把所有未跟踪的文件添加到暂存区
git commit -m   把暂存区的文件添加到本地仓库


# 忽略文件
    .gitignore

    # 注释
    *.txt   忽略所有.txt结尾的文件
    !lib.txt    但lib.txt除外
    /temp       该目录下的所有文件，但子目录除外
    build/      忽略build目录里面的所有文件和子目录
    doc/*.txt   忽略doc目录下的.txt文件，但不包含子目录


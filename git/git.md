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



    git-init - Create an empty Git repository or reinitialize an existing one
    git init [-q | --quiet]  [directory] 
    git init xxx
    git init


    git-add - Add file contents to the index
    git add [<pathspec>...]
    git add .
    git add Documentation/\*.txt
    git add git-*.sh

    git-config - Get and set repository or global options
    git config [<file-option>]  name [value ]
                system
                global
                local   (default)
    git config user.email "993650799@qq.com"
    git config --unset-all  user.email



# 1.本地操作
    git add
        commid
        status
        log
        reset
        diff
        rm
        reflog
        checkout
        reset
        stash
        stash pop
        tag

# 2. 分支操作
    git branch
        switch
        merge

# 3. 远程操作
    git clone
    git remote
    get fetch
    get pull
    get push


# Local Operations
    working directory           工作目录
    staging area                暂存区
    git directory(repository)   本地仓库


# .git目录
    HEAD    记录当前处在哪个分支里
    config  项目的配置信息
    description 项目的描述信息
    hooks/  系统默认钩子脚本目录
    index/  索引文件
    logs/   各个refs的历史信息
    objects/    git本地仓库的所有对象（commits, trees, blobs, tags） 
    refs/   标识每个分支指向了哪个提交（commit）


    git ls-files --stage    查看暂存区的文件


# git对象存储及管理

## 对象
    每个对象包括三个部分： 类型，大小和内容，大小指的是内容的大小，git有四种类型
    blob:   用来存储文件数据，通常是一个文件
    tree:   类似目录，管理tree和blob
    commit: 一个commit只指向一个tree,用来标记某一个特定时间点的状态，包括一些关于
            时间点的元数据，如时间戳，最近一次提交的作者，指向上次提交（commits）的指针等等
    tag:    用来标记某一个提交（commit）的方法


    git show sha1sum 查看blob对象的内容
    git cat-file  (-t | -s | -p)sha1sum
                type size print

    git commit 生成两个对象
        一个commit对象 ,commit对象指向的就是这个tree对象，而这个tree对象就是这次提交时工作区里面素有的目录和文件的指针
                        相当于一个快照，还带有相关的描述信息
        一个tree对象，
        并把HEAD指向这个tree对象

    git ls-tree HEAD 查看当前分支的tree对象内容
    git cat-file -p HEAD 查看当前分支的commit对象

    查看commit对象
    git cat-file -p main   //main是当前分支commit对象的指针
    git log -l --pretty=raw

    创建一个tag对象
    git tag -m "create tag from demo" v1.0
    git tag
    git cat-file -p v1.0

    git commit -a
    git ls-files --stage    //查看.git/index 这个索引文件的内容，


    git diff        //和当前index里面对象的文件比较
    git diff HEAD   //和仓库的文件比较

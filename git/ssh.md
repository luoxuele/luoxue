# 1. 设置git的user name和email
    git config --global user.name "luoxuele"
    git config --global user.email "tianchang1994@gmail.com"
    git config --global -l

# 2. 生成ssh key
    ssh-keygen -t rsa -C "tianchang1994@gmail.com"
    

# 3. github添加ssh key
    github的setting里面

# 4. 测试连接
    ssh -T git@github.com

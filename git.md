# 问题处理

### 1.使用git pull 超时:[来源]()

```shell
git pull
#报错fatal: unable to access 'https://github.com/froggengoing/LinuxLearn.git/': Failed to connect to 127.0.0.1 port 1080: Connection refused
ping github.com
##超时
##怀疑为本地DNS解析异常
##打开C:\Windows\System32\drivers\etc\hosts，末尾添加如下
192.30.255.112  github.com git 
185.31.16.184 github.global.ssl.fastly.net 
```

### 2.使用pull报冲突

```shell
error: Your local changes to the following files would be overwritten by merge
##覆盖本地代码
git reset --hard
git pull origin master
##从服务器更新代码，但不覆盖，add，commit，push 命令即可更新本地代码到服务器
git stash
git pull origin master
git stash pop
```


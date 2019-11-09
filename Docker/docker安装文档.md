
一、在Centos下安装Docker
====

1.如果安装过，先卸载残留文件
-----
>
```
sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```

2.安装依赖包
-----
 * 安装依赖软件包
```
sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
```
 * 设置仓库地址
```
 sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```

3.安装
-----
 * 安装最新版的 Docker Engine-Community 和 containerd
 ```
  sudo yum install docker-ce docker-ce-cli containerd.io
 ```
 > Docker 安装完默认未启动。并且已经创建好 docker 用户组，但该用户组下没有用户。
 * 启动docker
 ```
 sudo systemctl start docker
 ```
 * 通过下载运行 `hello-world` ，查看docker是否安装成功
 ```
 docker run hello-world
 ```
 
 4.分配普通用户权限
 ```
 usermod -G docker username
 ```
 
 欢迎进入我的github，[提出建议](https://github.com/fukeli)<br>
 ---
 

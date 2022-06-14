## 安裝docker
```
yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine

yum install -y yum-utils

yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo

yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

## docker常用指令
```
docker run 鏡像name    # 運行容器
[-it]    # 交互模式運行容器

docker images    # 查看本地的鏡像

docker rmi -f 鏡像name/鏡像id    # 刪除鏡像
docker rmi -f $(docker images -aq)    # 刪除全部鏡像

docker ps    # 查看當前正在運行的容器
[-a]    # 當前+歷史

docker exec -it 容器id    # 從新進程進入容器
docker attach 容器id    # 進入容器

docker rm -f 容器id    # 刪除容器
docker rm -f $(docker ps -aq)    # 刪除全部容器

docker start/restart/stop/kill 容器id    # 啟動和停止容器

[root@localhost jack]# docker run -it centos /bin/bash
[root@a4c65ed195df /]# pwd
/
[root@a4c65ed195df /]# cd /home
[root@a4c65ed195df home]# ls
[root@a4c65ed195df home]# touch test1.txt
[root@a4c65ed195df home]# ls
test1.txt
[root@a4c65ed195df home]# exit
exit
[root@localhost jack]# docker ps -a
CONTAINER ID   IMAGE     COMMAND       CREATED              STATUS                      PORTS     NAMES
a4c65ed195df   centos    "/bin/bash"   About a minute ago   Exited (0) 11 seconds ago             infallible_hugle
[root@localhost jack]# cd /home
[root@localhost home]# ls
jack
[root@localhost home]# docker cp a4c65ed195df:/home/test1.txt /home
[root@localhost home]# ls
jack  test1.txt
[root@localhost home]# 
```

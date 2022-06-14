## 安裝ansible
```
yum install ansible -y

# centos
# 192.168.2.129 centos7-2
# 192.168.2.130 centos7-3
# 192.168.2.131 centos7-4

# centos7-2
gedit /etc/ansible/hosts
# [server1]
# 192.168.2.130

# [server2]
# 192.168.2.131

# [servers]
# 192.168.2.130
# 192.168.2.131
```

## ansiable常用模塊
```
ansible server -m ping # 檢查主機間的通訊
ansible server -m command
ansible server -m script
ansible server -m shell
ansible server -m yum
ansible server -m copy
ansible server -m file
```
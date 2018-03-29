`目录 start`
 
- [Centos](#centos)
    - [安装](#安装)
        - [docker安装](#docker安装)
    - [基础命令](#基础命令)
    - [用户管理](#用户管理)
        - [新增](#新增)

`目录 end` *目录创建于2018-02-02* | 更多: [CSDN](http://blog.csdn.net/kcp606) | [oschina](https://my.oschina.net/kcp1104) | [码云](https://gitee.com/kcp1104) 
****************************************
# Centos
> 主流服务器

## 安装
### docker安装
> [hub的官方镜像](hub.docker.com/_/centos/)

- `docker pull centos` 得到镜像，然后跑起来即可
    - `cat /etc/redhat-release` 查看当前centos版本（适用于redhat centos） [参考博客](www.cnblogs.com/hitwtx/archive/2012/02/13/2349742.html)

- docker 中 centos7systemctl命令失效的解决方案：
	- `docker run --name centos2 --privileged  -ti -e "container=docker"  -v /sys/fs/cgroup:/sys/fs/cgroup  centos  /usr/sbin/init`

## 基础命令
> 采用的是yum rpm 管理包

## 用户管理

### 新增
> 和Ubuntu类似, 但是adduser会新建用户并且建立home目录,而且没有废话的交互, ubuntu就有

`adduser kuang` 新增用户和对应目录
`passwd kuang` 修改密码 , 奇怪的是使用gpasswd就更改成功了用不了



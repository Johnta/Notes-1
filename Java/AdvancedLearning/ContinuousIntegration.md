`目录 start`
 
- [传统部署](#传统部署)
- [持续集成](#持续集成)
    - [Jenkins](#jenkins)
    - [Drone](#drone)
    - [flow.ci](#flowci)
    - [三方平台](#三方平台)
- [代码质量管理](#代码质量管理)
    - [sonarqube](#sonarqube)
        - [小型项目目前使用的方案](#小型项目目前使用的方案)

`目录 end` |_2018-04-08_| [码云](https://gitee.com/kcp1104) | [CSDN](http://blog.csdn.net/kcp606) | [OSChina](https://my.oschina.net/kcp1104)
****************************************
# 传统部署
- 打包成jar或者war，下载JDK或者JRE 绿色解压即用，将jar/war文件复制到bin目录下
    - 后台运行 `start /b java -jar fileName`


# 持续集成
> 参考博客: [持续集成](http://www.ruanyifeng.com/blog/2015/09/continuous-integration.html) | [持续集成服务 Travis CI 教程](http://www.ruanyifeng.com/blog/2017/12/travis_ci_tutorial.html)  
> [廖雪峰 使用Travis进行持续集成](https://www.liaoxuefeng.com/article/0014631488240837e3633d3d180476cb684ba7c10fda6f6000)  
> 目前个人理解: 使用jenkins 结合gradle docker ，一键上传代码之后自动构建得到镜像

> [利用Travis CI更新github page](https://github.com/steveklabnik/automatically_update_github_pages_with_travis_example)
- 使用bitbucket配置私有仓库，在hub上配置docker文件的目录，进行构建，这样就会得到一个可用的镜像
    - 源码是过去了，构建呢，这是个问题，可以使用Jenkins么？
## Jenkins
> [官网](https://jenkins.io/)

[参考博客: 用 Docker, maven, jenkins 完成 CI](http://www.open-open.com/lib/view/open1436922756240.html)

## Drone 
> [官网](https://drone.io/)

## flow.ci
> [官网](https://flow.ci/) | [文档](https://github.com/FlowCI/docs/blob/master/intro_base.md)

## 三方平台
- [appveyor](https://ci.appveyor.com/projects)

# 代码质量管理

## sonarqube
> [官网](https://www.sonarqube.org/)

### 小型项目目前使用的方案
- 在开发机上进行开发，然后使用脚本将war上传scp到指定文件夹下，然后执行docker命令进行构建镜像，然后运行容器

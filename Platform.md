`目录 start`
 
- [代码托管平台](#代码托管平台)
    - [Gitee](#gitee)
        - [URL规则](#url规则)
    - [Github](#github)
        - [URL规则](#url规则)
        - [MarkDown规则](#markdown规则)
    - [Gitea](#gitea)
        - [自建](#自建)
- [综合开发平台](#综合开发平台)
    - [华为云](#华为云)
    - [阿里云](#阿里云)
        - [ECS](#ecs)
        - [ACM](#acm)
        - [OSS](#oss)
    - [百度开发平台](#百度开发平台)
        - [CCE](#cce)
        - [BOS](#bos)
        - [BAE](#bae)
        - [其他应用](#其他应用)
    - [腾讯](#腾讯)
        - [CVM](#cvm)
        - [COS](#cos)
        - [微信公众号](#微信公众号)
- [云存储](#云存储)
    - [坚果云](#坚果云)
    - [七牛云](#七牛云)
- [智能机器人平台](#智能机器人平台)
    - [图灵机器人](#图灵机器人)
- [消息推送](#消息推送)
    - [极光推送](#极光推送)
    - [GoEasy](#goeasy)
- [文档](#文档)
    - [文档托管](#文档托管)
- [测试平台](#测试平台)
- [培训](#培训)

`目录 end` *目录创建于2018-02-27* | 更多: [CSDN](http://blog.csdn.net/kcp606) | [oschina](https://my.oschina.net/kcp1104) | [码云](https://gitee.com/kcp1104) 
****************************************

# 代码托管平台
## Gitee
> 码云,国内的github [帮助文档](http://git.mydoc.io/)

### URL规则
- HTTPS & SSH
    - `HTTPS:` https://gitee.com/kcp1104/MythRedisClient.git
    - `SSH:` git@gitee.com:kcp1104/MythRedisClient.git

***********************************
## Github
> 全球范围的网站

### URL规则
> github仓库的URL规则

- HTTP & SSH
    - `SSH:` git@github.com:Kuangcp/Script.git
    - `HTTPS:` https://github.com/Kuangcp/Script.git

- 目录：
    - https://github.com/用户/项目/tree/分支/相对根目录的目录
- 文本文件：
    -  https://github.com/用户/项目/blob/分支/文件目录
- 二进制文件，例如图片：
    -  https://raw.githubusercontent.com/用户/项目/分支/文件目录
- 例如同仓库下的这个文件`/Linux/Docker.md` 可以直接这样写，方便调用，最好最前面不要加`.`这个表示当前目录的 

### MarkDown规则
> [更多详情>>](/Skills/Document/MarkDown.md#github)

*********************************************
## Gitea
> [官网](https://gitea.io/zh-cn/) 

### 自建
- 使用docker安装比较简单
    - 配置数据库，一定要是外网的。或者容器互联

`/data/gitea/conf/app.ini` 要修改的配置，都是改成对外的配置
```conf
ROOT_URL         = http://git.kuangcp.top/
DOMAIN           = git.kuangcp.top
SSH_PORT         = 10022
SSH_DOMAIN       = kuangcp.top
```

********************************************************
# 综合开发平台
## 华为云
- [CSE微服务相关文档](http://support.huaweicloud.com/devg-cse/cse_03_summary.html)

********************************************
## 阿里云

- 弹性计算  
    - 云服务器 ECS 负载均衡 弹性伸缩 容器服务 容器镜像服务 资源编排 高性能计算 批量计算     函数计算 弹性高性能计算 轻量应用服务器

- 监控与管理  
    - 云监控 访问控制    资源编排    操作审计    密钥管理服务

- 安全（云盾）
    - DDoS高防IP    游戏盾    Web应用防火墙（网络安全）    安骑士（服务器安全）    CA证书服务（数据安全）    移动安全（应安全）    数据库审计（数据安全）    加密服务（数据安全）    数据风控（业务安全）    内容安全（业务安全）    态势感知大据安全）    堡垒机（安全管理）    安全管家（安全服务）    先知（安全服务）    云防火墙    实人认证

- 数据库
    - 云数据库 RDS 版    云数据库 MongoDB 版    云数据库 Redis 版    云数据库 Memcache 版    云数据库HybridDB for ySQL    云数据库 HBase 版    云数据库 POLARDB    高性能时间序列数据库HiTSDB    云数据库 HybridDB for ostgreSQL    云数据库 OceanBase    分析型数据库    数据传输服务DTS    数据管理    数据库备份 DBS

- 应用服务
    - 日志服务    开放搜索    性能测试服务    邮件推送    API网关    物联网套件    消息服务    智能对话分析服务    云效   云AP    云桌面    CodePipeline    云客服    云小蜜    云呼叫中心    Node.js 性能平台

- 域名与网站（万网）
    - 域名    云解析 DNS    云虚拟主机    企业邮箱    标准建站    弹性 Web 托管

- 存储与CDN
    - 对象存储 OSS    文件存储 NAS    表格存储    归档存储    CDN    PCDN    云存储网关    智能云相册    混合云备份   混合云容灾    安全加速 SCDN    智能媒体管理

- 互联网中间件
    - 企业级分布式应用服务 EDAS    消息队列    分布式关系型数据库 DRDS    云服务总线    业务实时监控服务    全局事务服务   应用配置管理

- 云市场
    - 云市场

- 网络
    - 专有网络 VPC    负载均衡   NAT网关    共享流量包    弹性公网 IP   高速通道   VPN网关    共享带宽    CDN    全球速

- 移动服务
    - 移动数据分析   移动推送    HTTPDNS    移动安全（应用安全）    移动测试    移动用户反馈    移动热修复分析    E-MapReduce    云数据库 HybridDB for PostgreSQL    高性能计算    大数据计算服务    分析型数据库    数据集成（旧版）    开放搜索

- 视频服务
    - 媒体处理    视频点播    视频直播

- 云通信
    - 移动推送    消息服务    邮件推送    语音服务    流量服务    短信服务    物联网无线连接服务    号码隐私保护
- 大数据（数加）
    - DataWorks    Quick BI    机器学习    推荐引擎    公众趋势分析    DataV数据可视化    分析型数据库    大数据计算务    智能语音交互    流计算

### ECS
> 阿里云主机, 学生有优惠 9.9每月 1核2g

### ACM
> 应用配置管理 [入门文档](https://help.aliyun.com/document_detail/59964.html?spm=a2c4g.11186623.6.546.yaM0cp)
> [如何用ACM简化你的Spring Cloud微服务环境配置管理](https://zhuanlan.zhihu.com/p/33525168?group_id=942728800581259264)

### OSS
> 对象存储

```
资费项 	    计费项 	       标准型单价 	    低频访问型单价 	归档型单价
存储费用 (注①) 	数据存储 	0.148元/GB/月 	0.08元/GB/月 	0.033/GB/月
流量费用 (注①) 	内/外网流入流量（数据上传到OSS） 	免费 	免费 	免费
	内网流出流量（通过ECS云服务器下载OSS的数据） 	免费 	免费 	免费
	外网流出流量 	00:00-08:00（闲时）：0.25元/GB 8:00-24:00（忙时）：0.50元/GB
	CDN回源流出流量 	0.15元/GB 	0.15元/GB 	0.15元/GB
	跨区域复制流量 	0.50元/GB 	0.50元/GB 	0.50元/GB
请求费用 
	所有请求类型 	0.01元/万次 	0.1元/万次 	0.1元/万次
数据处理费用 (注②)
 	图片处理 	每月0-10TB：免费>10TB：0.025元/GB 	每月0-10TB：免费>10TB：0.025元/GB  	无
	视频截帧 	0.1元/千张 	0.1元/千张 	无
	数据取回 	免费 	0.0325元/GB 	0.06元/GB
```
**************************************
## 百度开发平台

**********
### CCE
> 容器引擎  -> [入门必看](https://cloud.baidu.com/doc/CCE/GettingStarted.html)  
> 其实就是镜像仓库,比阿里云的好用 域名很短

### BOS
> 对象存储 [计价方式](https://cloud.baidu.com/doc/BOS/Pricing.html#.E6.8C.89.E9.9C.80.E8.AE.A1.E8.B4.B9)  
> 关于流量定价中的CDN回源流量, 大致是当你开了CDN加速, 然后CDN为了刷新缓存要去你对象存储源获取最新的文件, 这个消耗的流量  
> 同样支持文件夹  

_存储空间价格_  
```
计费项 	标准存储单价（元/GB/月） 	低频存储单价（元/GB/月） 	冷存储单价（元/GB/月）  
存储空间 	0.128 	0.08 	0.048  
```
_请求次数价格_  
```
计费项 	规格 	标准存储单价（元/万次） 	低频存储单价（元/万次） 	冷存储单价（元/万次）  
写请求次数 	PUT,COPY,DELETE 	0.01 	0.25 	0.5  
读请求次数 	GET Bucket,GET OBJECT及其他所有请求 	0.01 	0.05 	0.1  
```
_数据取回价格_
```
计费项 	规格 	标准存储单价（元/GB） 	低频存储单价（元/GB） 	冷存储单价（元/GB）
数据取回 	- 	NA 	0.03 	0.15
```
_流量价格_
```
计费项 	标准存储 & 低频存储 & 冷存储单价（元/GB）
外网数据流出 	0.6
CDN回源流出 	0.14
跨区域数据流出 	0.6
```
****************
### BAE
> 应用引擎，简单的说就是一个提供了环境，你只需上传打包好的可执行文件就可以运行起来了  
> 本来的话是比较简单容易上手的, 但是现在要备案了, 就玩不了了

- 短期使用收费没有很高，十分灵活，就是前期学习入门 配置略麻烦。适合演示使用，例如毕设。
    - 并且还提供一定免费额度的 MySQL Redis MongoDb （只能BAE的内网访问）
    - 还有自动测试

*******************
### 其他应用
- [百度脑图](http://naotu.baidu.com/)`在线思维导图创作`
- [站内搜索](https://zn.baidu.com/cse/home/index)`不用自己写搜索了`

*******************************************************
## 腾讯
### CVM
> 云服务器  
> 学生优惠是 10元每月1核1g 60则是2核2g

### COS
> 对象存储 [官方文档](https://cloud.tencent.com/document/product/436)  
> 同样的支持文件夹,还可以拖动文件夹上传,算是最好用的一个了  

_免费额度_
```
    资源类型 	资源子类型 	       每月免费额度
    存储空间 	存储空间 	         50 GB
    流量 	     外网下行流量 	     10 GB
    流量 	     腾讯云 CDN 回源流量 	10 GB
    请求 	     读请求 	           100 万次
    请求 	     写请求 	           100 万次
```

### 微信公众号
`2017-12-21 21:41:43`
- 不说了反正都是Shit一样的接口设计和返回值  希望会变好，碰过就不想再弄了！！！


*************************************************
# 云存储
## 坚果云

## 七牛云
> 免费存储额度10g流量额度10g, 但是不能创建文件夹  

****************************************************
# 智能机器人平台
## 图灵机器人

************************************************ 
# 消息推送
## 极光推送
> [官网](https://www.jiguang.cn/) `做Android IOS的消息推送和短信等推送`

## GoEasy
- [示例](http://goeasy.io/cn/started)

*********************************
# 文档
## 文档托管
- [看云](https://www.kancloud.cn/dashboard)

_showdoc_
- [showdoc](https://www.showdoc.cc/web/#/)`开源,也具有Docker方式` | [示例](https://www.showdoc.cc/web/#/demo?page_id=7)
- Docker安装: [官方文档](https://www.showdoc.cc/web/#/help?page_id=65610) `跑起来也就几十M内存占用`
    - `git clone https://github.com/star7th/showdoc`
    - 进入项目目录 然后 `docker build -t showdoc ./`
    - `docker run -d --name showdoc -p 4999:80 showdoc`
    - `http://localhost:4999/install/` 然后为了保险起见进容器删除项目根目录的install目录即可
    - 数据与备份 Sqlite/showdoc.db.php 是数据库; 如果有图片就还要备份图片,所以解耦就还是不上传图片了

************************************************************
# 测试平台
- [自动API测试](https://www.eolinker.com/#/index)
- [吆喝科技](http://www.appadhoc.com/)`A/B测试 灰度上线`

*************************************************
# 培训
- [咕泡](http://www.gupaoedu.com/)`看起来很有深度, 就是有点贵`
- [集智](https://jizhi.im/index)


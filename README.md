# 52pojie_helper
吾爱破解论坛刷吾爱币

### 原理
定时自动回帖，达到刷吾爱币及积分的目的

### 执行流程
每6分钟执行一次
1. 获取精品软件区帖子ID列表
2. 遍历帖子ID列表，判断该帖是否已回过
3. 如果未回过该帖，随机选择一条回复内容，执行回复。如果回过，重新选择下一帖回复
4. 判断回帖结果，如果该帖不存在，重新选择下一帖回复。

### 使用方法
基于Java8，使用前需安装Java运行环境
#### 方式一: 源码启动
1. 启动前修改userconfig.yml文件，配置cookie,formhash等。
2. 启动项目

#### 方式二: jar包启动
1. [下载](https://github.com/AochongZhang/52pojie_helper/releases)jar包
2. 同级目录下增加userconfig.yml文件，配置cookie,formhash等
3. 启动jar包

### 涉及技术
- **SpringSchedul** 用来定时执行任务
- **SpringDataJpa + H2数据库** 用来保存已回复过的帖子ID
- **RestTemplate** 发送HTTP请求

### 计划增加功能
- [ ] 增加管理页面，通过管理页面配置任务，查看执行状态
- [ ] 无可回复帖时自动获取下一页帖子列表
- [ ] 增加登陆功能，无需配置cookie

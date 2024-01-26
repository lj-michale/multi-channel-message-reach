# 多渠道消息触达平台
详细安装教程：https://blog.csdn.net/weixin_52097397/article/details/135738516?csdn_share_tail=%7B%22type%22%3A%22blog%22%2C%22rType%22%3A%22article%22%2C%22rId%22%3A%22135738516%22%2C%22source%22%3A%22weixin_52097397%22%7D
觉得不错就给个`Star`吧~
# 介绍
多渠道消息触达平台是一个为应用开发者提供服务的平台，旨在解决发送消息的需求。
通过与消息触达平台的接口对接，开发者无需自行编写发送消息的代码，从而实现业务逻辑代码和发送消息逻辑代码的解耦。
能够让开发者能够更加专注于核心业务开发，提高开发效率，并且实现了消息发送的统一管理和多渠道的灵活选择。
项目视频演示地址：https://www.bilibili.com/video/BV1Uk4y1S7hR/?vd_source=ea9d3688c968ba55be79c5ce3dc1c5fc

Gitee地址：https://gitee.com/hanabizzx/multi-channel-message-reach

# 项目特性
多渠道消息触达平台具有以下特性：

+ **统一提供多个消息服务渠道**：与多个第三方消息服务API进行对接，包括邮件、短信、钉钉群机器人、APP通知栏（push通知栏）、微信公众号（模板消息）、飞书机器人和企业微信机器人。
+ **高性能消息推送**：基于阻塞队列+消息队列+动态线程池处理消息任务，可处理大量消息任务
+ **推送灵活**：支持自定义消息内容实时、定时单个推送和批量推送
+ **数据可视化**：对每个消息模板的推送情况进行可视化图形展示
+ **扩展灵活**：可对消息发送业务流程进行业务扩展，定制专属推送流程
+ **消息可靠推送**：基于消息确认机制+延迟队列+线程池监控，对进入发送阶段的消息任务全链路追踪
+ **人群文件定时推送**：可上传人群文件对用户定时推送

# 技术选型

+ **动态可监控线程池**：引入该技术来处理各渠道消息发送任务，提高消息发送任务的并发量和处理速度。
+ **Nacos**：用于管理项目中的微服务实例和服务配置，通过动态管理线程池参数，提升系统的灵活性。
+ **Redis**：使用Redis实现消息的链路追踪，对消息的各个阶段进行实时监控、日志记录和消息发送记录，掌控消息的生命周期。
+ **Xxl-job**：用于定时启动定时消息任务，实现消息的定时发送功能。
+ **RabbitMQ**：作为消息中间件，将实时消息发送任务或定时消息任务交给RabbitMQ监听消费，实现消息发送的异步解耦，降低系统的耦合度。
+ **Docker**：用于统一部署各组件，简化系统的部署难度。
+ **RabbitMQ延迟队列**：通过使用延迟队列，处理超时消息任务，提高消息的可靠性（延迟队列默认关闭，需安装延迟插件手动开启）。
+ **Mysql**：作为存储消息发送模板信息和第三方账号配置信息的数据库。
+ **ECharts可视化**：通过使用ECharts，对消息模板下发用户数、今日消息送达率、每天各时间段发送情况以及消息模板用户等数据进行可视化展示，方便进行消息模板的数据分析。
+ **Sentinel限流**：使用Sentinel来对消息发送接口进行限流，保障系统的稳定性。
+ **Redisson分布式锁**：对消息确认机制引入分布式锁减小锁粒度，提高并发量

# 目前支持的渠道消息类型

+ **邮箱**
    - 支持文本、HTML类型
    - 支持网络附件和本地附件推送
+ **短信**
    - 阿里云：支持手机号短信回执拉取
    - 腾讯云：支持手机号短信回执拉取、账号回执拉取
+ **APP通知栏**
+ **微信公众号**
    - 模板消息
+ **钉钉群机器人**
    - 文本
    - Markdown
    - 链接消息
    - 卡片消息
    - FeedCard
+ **飞书机器人**
    - 文本
+ **企业微信机器人**
    - 文本类型
    - Markdown类型
    - 图片类型
    - 图文类型
    - 文件类型
    - 语音类型

# 演示图

<table>
    <tr>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/%E9%A6%96%E9%A1%B5.png"/></td>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/0.png"/></td>
    </tr>
    <tr>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/1.png"/></td>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/2.png"/></td>
    </tr>
    <tr>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/10.png"/></td>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/11.png"/></td>
    </tr>
    <tr>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/3.jpg"/></td>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/4.png"/></td>
    </tr>
     <tr>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/5.jpg"/></td>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/6.png"/></td>
    </tr>
     <tr>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/7.png"/></td>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/8.png"/></td>
    </tr>
     <tr>
        <td><img src="https://github.com/Manzzx/multi-channel-message-reach/blob/master/doc/imgs/9.jpg"/></td>
    </tr>
	
</table>


# 软件架构
api模块：系统接口

common模块：通用模块

gateway模块：网关

modules模块：系统基础功能模块

ui模块：前端

visual模块：系统监控

web模块：消息推送功能模块

# 安装教程
详细安装教程：https://blog.csdn.net/weixin_52097397/article/details/135738516?csdn_share_tail=%7B%22type%22%3A%22blog%22%2C%22rType%22%3A%22article%22%2C%22rId%22%3A%22135738516%22%2C%22source%22%3A%22weixin_52097397%22%7D

#### 运行必需服务
Redis、RabbitMQ、Xxl-job、Nacos、Mysql5.7

#### 必需运行微服务
MetaxAuthApplication
MetaxFileApplication
MetaxGatewayApplication
MetaxSystemApplication
MetaxWebApplication

#### 运行非必需服务
Sentinel、SpringbootAdmin（visual模块）

#### 后端

1. docker安装redis、rabbitMQ、mysql、nacos

2. 需要给调用xxl-job的接口加上@PermissionLimit(limit=false)开放权限(xxl-job下载地址：https://gitee.com/xuxueli0323/xxl-job?_from=gitee_search)

3. 修改各服务组件地址,各服务的bootstrap.yml文件和Nacos配置文件


#### 前端
1. **进入项目目录**

    cd metax-ui

2. **安装依赖**

    npm install 
 
    npm install --registry=https://registry.npmmirror.com

3. **启动服务**

    npm run dev

项目访问地址：http://localhost:78

# 使用说明
1. 管理员账号密码：admin admin123

2. 配置个人渠道账号信息

3. 新增渠道消息模板

4. 发送/启动模板

本项目仅供学习参考，如对你有帮助就给个star吧~


# 第一周笔记

体验地址: [慕课乐高](https://www.imooc-lego.com/)

项目架构

![产品架构](https://class.imooc.com/static/module/marketpage2020/img/intro/fearchitect/section3-main.png)

使用技术栈

![技术栈](https://class.imooc.com/static/module/marketpage2020/img/intro/fearchitect/section7-main.png)

## 架构设计做什么 如何做
> **架构师的核心价值** : 通过技术手段保证技术增长,对业务精准理解
>
> + 需求指导设计,设计指导开发
> + 技术永远是为业务服务的,技术是实现业务增长的工具
> + 整体分析时不需要注意细节
> + 判断可行性,需要适当调研
> + 考虑复杂度,不过度设计
> + **脱离业务的设计就是耍流氓**
> + 需求即业务,无业务不架构
> + 需求闭环 业务闭环

## 前段开发流程

![前段开发流程](https://img.mukewang.com/wiki/5fdac52308c585a310321600.jpg)



## 需求关系图

![需求关系图](https://img.mukewang.com/wiki/5fdac5fd08b94b2514200948.jpg)



# 技术方案设计文档



## 模块设计

![image-20201222012242833](https://gitee.com/lhzhangcode/note-images/raw/master/image-20201222012242833.png)



> h5端: 提供作品展示与分享的功能
>
> 编辑器前端: 提供作品编辑 制作与发布功能
>
> 编辑器服务端: 支持编辑器前端的功能 并将作品持久化到数据库
>
> 后台管理前端: 供管理员使用 用于管理作品与模板 快速下线违规作品 查看运营统计数据
>
> 后台管理服务端: 为后台管理提供接口服务
>
> 组件库: 为h5与编辑器端提供组件服务 并可以通过脚手架工具快速创建和发布组件
>
> 自研统计: 用于统计自定义事件的pv uv等指标
>
> 三方服务:
>
> - 短信服务: 用于注册 登陆以及密码找回等操作需要验证用户身份时使用
> - oss文件存储: 存储静态文件
> - 埋点统计: 用于统计pv uv等常见运营指标
> - 微信sdk: 用于微信分享 便于传播

## 核心数据结构

> + 每个组件尽量符合vnode规范
> + 使用数据来组织数据 有序
> + 尽量使用引用关系 不要冗余

 ```json
{
  work:{
    id:'xxx',
    title:'标题',
    props:{/*全局配置属性*/},
    settings:{/*拓展预留*/},
    components:[
      {
        id:'xxxx',
        name:'文本1',
        tag:'text',
        attrs:{color:red},
        children:[]
      }
    ]
  },
  //当前被选中的组件id
  activeComponentId:'xx'
}
 ```

## 拓展性

+ 增加动画,音效 甚至简单的交互功能
+ 批量选中与批量修改
+ 多人协作 同时编辑

## 研发提效

+ **脚手架: 创建发布**
+ **组件平台**

## 运维保障

+ **线上服务和运维服务**
+ **安全**
+ **监控与告警**
+ **服务拓展性: 基于云服务,可以随时拓展机器和配置**

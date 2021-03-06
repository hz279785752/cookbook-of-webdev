参考链接

[如何实现前端微服务化？]: https://segmentfault.com/p/1210000010459082/read
[如何解构单体前端应用——前端应用的微服务式拆分]: http://baijiahao.baidu.com/s?id=1595295714541106181&amp;amp;amp;amp;wfr=spider&amp;amp;amp;amp;for=pc
[微前端 - 将微服务理念延伸到前端开发中]: https://www.cnblogs.com/zhuanzhuanfe/p/7644846.html
[微前端的那些事儿]: https://github.com/phodal/microfrontends

因为我们团队前端开发技术栈比较统一，也还不存在需要兼容遗留系统的问题，所以采用如下方案：

- 抽取前端项目骨架/工具等公用部分
- 各应用通过 git submodules 或 npm 私有镜像库拉取公用部分到各自代码目录
- 各应用分别打包部署上线
- 做泛域名下单点登录，共享用户登录状态
- 使用 cookie/后端存储共享部分用户数据

对于后端微服务来说，必须要有注册中心来管理各服务访问地址，同样在前端我们通过路由来管理各应用下暴露出来的功能页面。


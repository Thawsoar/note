# 全栈个人博客开发笔记-github授权登录

#### 前端

1. 跳转到github授权页 回调拿到code 
2. 将code传递给前端 

#### ![](https://cdn.jsdelivr.net/gh/Thawsoar/FigureBed@master/img/20200418224757.png) 

#### 后台服务

> https://eggjs.org/zh-cn/tutorials/passport.html

1. 安装包

   ```js
    yarn add egg-passport egg-passport-github
   ```

2. 配置

   ```js
   // config/plugin.js
   module.exports.passport = {
     enable: true,
     package: 'egg-passport',
   };
   
   module.exports.passportGithub = {
     enable: true,
     package: 'egg-passport-github',
   };
   
   // config/default.js
   config.passportGithub = {
     user_info_url: 'https://api.github.com/user', // 用户信息
     access_token_url: 'https://github.com/login/oauth/access_token', // 授权token
     key: '', // GitHub 分配的客户端 id
     secret: '', // GitHub 分配的客户端密钥
     callbackURL: '/passport/github/callback',
     // proxy: false, // 应用部署在 Nginx/HAProxy 之后，需设置插件 proxy 选项为 true
   };
   ```

   

2. 写接口

   - 拿到前端传入的code值 请求token

   - 拿到token 再请求用户信息 返回给前端

     > https://eggjs.org/zh-cn/core/httpclient.html#get

![](https://cdn.jsdelivr.net/gh/Thawsoar/FigureBed@master/img/20200418224421.png)
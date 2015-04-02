#新版本node express搭建microblog
主要参照：https://github.com/nswbmw/N-blog/wiki/%E7%AC%AC1%E7%AB%A0--%E4%B8%80%E4%B8%AA%E7%AE%80%E5%8D%95%E7%9A%84%E5%8D%9A%E5%AE%A2

#环境
node v0.12.0
express v4.12.1
npm v2.7.3

#安装
按照nodejs开发指南安装express，npm
express4.0+版本中将命令工具分出来了，所以可以不安装express，但必须要安装express-generator
node app不管用了，因为建服务器的代码写进了bin/www,你可以用npm start来建服务器，等同于node bin/www，如果你安装了supervisor，可以直接用supervisor .bin/www来运行服务器。

#路由
4.x已经是在index.js里面规划路由就好了，你想添加一个路由控制，直接在app.js后面添加
router.get('/’, function(req, res) {
});或者
router.post('/’, function(req, res) {
});

#连接Mongodb
在package.json里添加依赖包：
    "mongodb": "1.4.15",
    "express-session": "1.9.1",
    "connect-mongo": "0.8.0",
    "bson": "0.2.0",
    "connect-flash": "0.1.1"
<br/>这里我多了bson，之前运行时报错需要module “bson”，所以添加了这个moudle。“connect-mongo”0.1.0 会报错‘setting ttl index on collection’，升级0.8.0问题解决。
<br/>之后按照参考的到了用flash显示注册成功信息时，又报错：“Cannot read property ‘length’ of undefined”，暂时未解决此问题。。。

#2015-4-2 18:29
按照参考的重新安装了express 4.10版本 （npm install express@4.10），安装mongodb6.9版本。重新做。终于没有各种报错了！


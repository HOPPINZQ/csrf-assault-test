# 基于CSRF攻击的盗号实战

<p align='center'>
  <img src="http://hoppinzq.com/static/images/logo/1640338711_113639.png" width='400'/>
</p>

<p align='center'>“攻击”网易云音乐</p>

<p align='center'>
  <a href='http://1.15.232.156/'>
    <img src='https://img.shields.io/badge/-hoppinzq-green?logo=hoppinzq&logoColor=white&color=green'/>
  </a>
</p>

<br>

## 🎤介绍

相信大家都对前段时间的QQ盗号事件有所耳闻。流传的原因有以一个：钓鱼网站伪造了一个LOL活动，受害者通过QQ扫描该网站提供的二维码登录并参与活动。
这就是跨站点伪造请求（CSRF）。该攻击手段非常简单，也不好预防。在我做的[钓鱼网站](http://1.15.232.156/wyy/login.html) 用网易云APP扫描右方的二维码，尝试“被盗”。
> 👉 [演示网站点我](http://1.15.232.156/wyy/login.html)

## ⚓️原理
通过上面的一些操作，你也可以看到，由csrf攻击导致的“盗号”其实就是别人借用“你的名义”，去操作你的账号，
本质并不是真的盗了你的号。 攻击者通过伪造用户的浏览器请求（本站的请求），向访问一个用户自己认证访问过的网站
（本站）发送出去，使目标网站（网易云）服务器接收并误以为是用户的真实操作而去执行命令。 常用于盗取账号、转账、发送虚假消息等。攻击者利用网站对请求的验证漏洞（标志用户的token怎么传）而实现这样的攻击行为，使得被攻击网站能够确认请求确实是用户发起的， 却不能分辨请求是源于真正的用户还是伪造的。
## 📗使用
直接打开login.html即可

## ✏️我的博客和文章

- [✨自己写的博客网站✨](http://1.15.232.156/)
- [👐 手撕一套单点登录系统👐 ](http://1.15.232.156/blog/289870567891320800)
- [🎱浅谈steam攻击者的伎俩🎱](https://mp.weixin.qq.com/s/IQ-lWcjXlflTLU_KMBZzgw)

## 📷截图
#### 🐅登录页面，不想输入手机号/密码的话用网易云APP扫二维码就行

![快来试试吧](http://hoppinzq.com/image/chrome_VrOdnt9xOi.png)

#### 😝我准备好了！
![快来试试吧](http://hoppinzq.com/image/chrome_tJGT2o5RIJ.png)

## 🙏你应该学到
- 👀随着移动设备的兴起，各大产品的移动端应用开发已经是产品开发的首选。二维码因为其便利性成为最伟大的发明之一，
  其本质就是一个具有纠错能力的存储信息的媒介。 所以通过二维码授权或者登录不仅便利，而且易于推广。
  这使得csrf攻击成本变得极低且用户非常容易上当，通过以上案例你会发现，你仅仅是花一点点时间 扫描了一个二维码， 但你并不会感知在扫描之后脚本做了如此多的操作。所以，切勿贪图小便宜扫描街边二维码，尤其是需要授权的。


- 🌀现在很多网站自己的sso（单点登录系统）都有授权第三方登录，比如我网易云音乐可以通过QQ、
  微信、微博、网易邮箱这四个应用提供授权登录。这个功能的实现需要上面 4个应用提供oauth2服务和openapi接口，
  然后由网易云调用oauth2接口申请授权并重定向，然后通过openapi调用用户授权的接口。
  这个时候你就要睁大眼睛看网易云去申请了什么权限。通常而言，获取用户信息的权限是必须要给的，
  因为这个权限给了网易云 就可以拿到你的id，昵称，头像等必要信息用来创建用户及展示，但是其他权限你得看好了。
  比如我的网站要获取gitee下面这些权限是很多人不能接受的（关闭对应的即可）。
  ![图片](http://hoppinzq.com/wyy/static/picture/4ed007e081568e4a01002144dd5d2fa.png)
## 🎬反馈
>  🌷你可以发起 Issue

## 😘感谢
[网易云](https://music.163.com/)

## 📄License

MIT
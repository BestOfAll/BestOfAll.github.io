---
title: 网站管理
date: 2019-05-1 22:05:22
categories: Hexo
tags: [Hexo, 域名, coding, seo]
hide: true


---

目录请看  [Hexo 搭建博客大全](https://calmcenter.club/2019/Complete_works_of_hexo.html)

## 本文主要记载

- 加入 `Coding` 服务器
- 个人域名
- `SEO`  推广

------

<!--more-->

**重点标注：`hexo` 根目录配置文件 `hexo/_config.yml`  下文用 `Hexo 配置文件` 表示，`NexT` 样式配置文件 `hexo/theme/next/_config.yml` 下文用 `NexT 配置文件` 表示一定要分清，它们都叫 `_cpmfig.yml` **

**本文章写于 `2019/5/5` 图片内容可能和您现在看的内容不太一样，但是功能大体是不会变的。**

## 加入 `Coding` 服务器

这里加入`Coding` 服务器的作用主要是访问速度，其次就是由于 `github` 屏蔽百度的爬虫，所以使用 `github page` 服务的站点的链接无法被抓取，可用  `Coding`  的 `page` 服务。

1. 登录 [Coding](https://dev.tencent.com/)

登录 [Coding](https://dev.tencent.com/) ，并创建项目

<img src="https://raw.githubusercontent.com/CalmCenter/picGo/master/pictures/20190505114135.png" style="zoom:50%">

2. 个人设置

首先你需要点击头像，找到个人设置，在个人设置中设置 **密码** 和 **邮箱** 才能设置 **SSH** ，如果你之前设置过 `github` 的 `SSH` 你只需要执行以下命令

```
clip < ~/.ssh/id_rsa.pub
```

然后点击 `SSH`公钥 设置即可，如果没有设置过 `github` 请参考 [Hexo 基础搭建 - 配置 SSH 秘钥部分](https://calmcenter.club/2019/Hexo_bash.html#2-3-%E9%85%8D%E7%BD%AE-SSH-%E5%AF%86%E9%92%A5)

3. 验证

输入以下命令，查看 `SSH` 配置是否成功

```
ssh -T git@git.coding.net
```

4. 添加配置

在  `Hexo 配置文件` 中注释掉之前的，添加 `repo` 中的内容 `SSH` 路径 `,master`

```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  #repository: git@github.com:CalmCenter/calmcenter.github.io.git
  #branch: master
  repo:
    github: git@github.com:CalmCenter/calmcenter.github.io.git,master
    coding: git@git.dev.tencent.com:CalmCenter/calmcenter.coding.me.git,master
    
```

5. 提交

```
hexo clean && hexo g && hexo d
```

6. 打开 `Coding Pages` 服务

`头像 -> 我的主页 -> 项目 -> 代码 -> Pages 服务` 打钩已阅读服务，点击开启即可

会告诉你访问地址，打开如果排版不正常，不要慌，可能是子文件目录问题，设置域名后可解决。

<img src="https://raw.githubusercontent.com/CalmCenter/picGo/master/pictures/20190508105842.png" style="zoom:50%">

## 个人域名

1. 获得域名

首先你得有你自己的域名，几块钱就好~  [腾讯云](https://cloud.tencent.com/act/domainsales?fromSource=gwzcw.2211770.2211770.2211770&utm_medium=cpc&utm_id=gwzcw.2211770.2211770.2211770) 、[阿里云](https://wanwang.aliyun.com/domain/yumingheji) ，然后需要进行实名认证。完成后就可以添加域名解析地址啦~ 

2. 添加解析

这是 [腾讯云](https://cloud.tencent.com/act/domainsales?fromSource=gwzcw.2211770.2211770.2211770&utm_medium=cpc&utm_id=gwzcw.2211770.2211770.2211770) 的域名解析。

**注意：这里域名操作，每次操作完都会有一定缓冲时间，不会立即生效，每次操作完等待 10 分钟左右，再去配置域名** 

<img src="https://raw.githubusercontent.com/CalmCenter/picGo/master/pictures/20190508104813.png" style="zoom:50%">

这是添加的解析，因为添加了 `coding` ，所以有两条，分别将两个访问地址添加到域名解析中，`github` 用于境外访问，`coding` 本想着用于境内，但这里必须设置成默认才行。

2. `github` 域名设置

点击你的博客项目的 `Setting` -> `Options` 下滑找到 `GitHub Pages` 

<img src="https://raw.githubusercontent.com/CalmCenter/picGo/master/pictures/20190508105420.png" style="zoom:50%">

<img src="https://raw.githubusercontent.com/CalmCenter/picGo/master/pictures/20190508105344.png" style="zoom:50%">

这里会提示你站点发布在什么地方，记得开启 `HTTPS` 哦。

3. `Coding` 域名设置

<img src="https://raw.githubusercontent.com/CalmCenter/picGo/master/pictures/20190508105715.png" style="zoom:50%">

自定义域名，将申请好的域名添加上去，点击绑定，然后刷新页面，知道 `SSL/TLS 安全证书` 出现结果，如果错误，请查看解析中 `coding` 线路类型配置是否是默认，如果是默认还不行，请将境外的 `github` 先暂停，再去重新绑定。记得开启 `HTTPS` 哦。

**操作时请留意 个人域名 开头说明的注意事项**

## `HTTPS` 设置



## `SEO`  推广

参考自作者 [EnjoyToShare](https://blog.enjoytoshare.club/article/hexo-do-optimization.html#5) 

###  `SEO` 是什么

刚搭建完博客，可能你会发现你发表的文章在谷歌或者百度都搜索不到，因为需要进行 `SEO` 优化的，什么是 `SEO` ，顾名思义，`SEO` 即 `(Search Engine Optimization)` : 汉译为搜索引擎优化，它可以让自己的博文能在谷歌百度上搜索到。

### 生成 `sitemap`

`sitemap` 用于通知搜索引擎网站上有哪些可供抓取的网页，以便搜索引擎可以更加智能地抓取网站。
安装 `sitemap` 站点地图自动生成插件 `hexo-generator-sitemap` 和 `hexo-generator-baidu-sitemap` 

```
npm install hexo-generator-sitemap --save
```

```
npm install hexo-generator-baidu-sitemap --save
```

然后修改  `Hexo 配置文件` ，**添加**如下内容

```
sitemap:
  path: sitemap.xml
baidusitemap:
  path: baidusitemap.xml
```

并**修改** `url` 为你的域名地址 如 `url: https://blog.calmcenter.club/` 

然后编译代码

```
hexo g
```

就会生成在 `hexo\public` 下生成 `sitemap.xml` 和 `baidusitemap.xml` 一个是给谷歌的，一个给是百度的。

### 添加协议

网站通过 `Robots协议` 告诉搜索引擎哪些页面可以抓取，哪些页面不能抓取。 `robots.txt` 通常存放于网站根目录 ( `public` 目录)。由于我们每次 `hexo clean` 都会清空 `public` ，着实不方便，我们都知道 `source` 目录下的文件通过 `hexo g` 命令会转换成 `public` 中的文件，所以为了方便起见，我们把 `robots.txt` 文件放在`source`目录下，我的 `robots.txt` 内容为：

```
User-agent: *
Allow: /
Allow: /archives/
Allow: /categories/
Allow: /tags/
Allow: /links/
Disallow: /js/
Disallow: /css/
Disallow: /fonts/
Disallow: /vendors/
Disallow: /fancybox/
Sitemap: https://你的域名/sitemap.xml
Sitemap: https://你的域名/baidusitemap.xml
```

其中Allow后面的就是你的menu
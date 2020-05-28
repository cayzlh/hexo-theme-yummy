# Hexo-theme-yummy

> 一次偶然的机会，发现了[Yummy-Jekyll](https://github.com/DONGChuan/Yummy-Jekyll) 这个jekyll主题，这种清爽简约的风格深得我心，于是着手移植到Hexo来。由于不会写前端，所有样式照搬。

- 基于[Hexo 4.2.0](https://hexo.io)
- [预览｜Preview](https://cayzlh.github.io/blog)
- 没有花里胡哨的特效，简洁清爽。

# Features 

- [x] hexo主题基础功能
- [x] 评论系统
- [x] 阅读统计
- [ ] ~文章搜索功能~
- [x] 相关文章推荐
- [x] 博客引流到公众号（观众公众号获得阅读更多的权限）

# TimeLine

[查看更新说明](https://github.com/cayzlh/hexo-theme-yummy/releases)

# 使用说明

[Hexo文档](https://hexo.io)

## 安装

### 安装依赖

```bash
npm install hexo-related-popular-posts --save
npm install  hexo-prism-plugin --save
```

### 安装主题

1. 进入Hexo**站点文件夹**，克隆本主题到`themes/`路径下：

   直接使用master分支，可能不稳定。 。

   ```bash
   # cd your hexo site directory
   git clone https://github.com/cayzlh/hexo-theme-yummy.git themes/Yummy
   ```

   或者下载realease版本：[https://github.com/cayzlh/hexo-theme-yummy/releases](https://github.com/cayzlh/hexo-theme-yummy/releases)

2. 重命名主题中的 `_config.example.yml` 为 `_config.yml`，然后可以使用配置文件配置主题

   ```bash
   cp -f themes/Yummy/_config.example.yml themes/Yummy/_config.yml
   ```

   此时`_config.yml`中是一些默认的配置， 请将相应信息改成自己的。

3. 使用 `hexo-prism-plugin`插件

   **否则代码样式不好看**。**否则代码样式不好看**。**否则代码样式不好看**。

   *安装插件*

   ```bash
   npm install  hexo-prism-plugin --save
   ```

   *根据提示，你可能还需执行*

   ```bash
   npm audit fix
   ```

   修改站点配置文件`_config.yml`，禁用hexo默认的高亮插件，添加`hexo-prism-plugin`高亮插件支持。

   ```yml
   highlight:
     enable: false  # 将系统原来的高亮插件设置为false
     line_number: false
     auto_detect: false
     tab_replace: ''
     wrap: true
     hljs: false
   # 添加以下配置启用prism插件
   prism_plugin:
     mode: 'preprocess'
     theme: 'tomorrow' # 推荐使用这个
     line_number: true    # default false 是否展示行号
     custom_css: '/css/common.css'# 这里要配这个，否则不好看。。
   ```

4. 使用`hexo-related-popular-posts`插件，开启相关文章推荐功能

   ```bash
   npm install hexo-related-popular-posts --save
   ```

5. 启用主题

   修改站点配置文件`_config.yml`，启用Yummy主题

   ```yml
   theme: Yummy
   ```

   

## 主题配置文件

### topbar

配置页面右上角的几个小链接

```yml
topbar:
  homepage:	# 这个字段随便写
    name: 导航页
    url: https://cayzlh.github.io
  github:
    name: GitHub
    url: https://github.com/cayzlh
    target: _blank
  about:
    name: 关于
    url: /about
```

### 菜单配置，支持子菜单

```yml
menu:
  Home: # 这个字段随便写
    url: /
    name: 首页
  Archives:
    url: /archives
    name: 归档
  Tools:
    url: /
    name: 在线工具
    children:
      - name: Json在线工具
        url: https://cayzlh.github.io/tools/online-JSONFormat/
      - name: Markdown在线转换工具
        url: https://cayzlh.github.io/tools/online-markdown/
```


### slogan 和 下面的一排链接

```yml
jumbotron:
  slogan: 记录成长路上的风景
  infos: ## 不配不显示，就是可以配很多个链接～～
    - name: 富强
      url: /
    - name: 民主
      url: /
    - name: 文明
      url: /
    - name: 和谐
      url: /
    - name: 自由
      url: /
    - name: 平等
      url: /
    - name: 公正
      url: /
    - name: 法制
      url: /
    - name: 爱国
      url: /
    - name: 敬业
      url: /
    - name: 诚信
      url: /
    - name: 友善
      url: /
```

### 社交链接配置

Icon和txt字段二选一

```yml
social:
  - url: https://github.com/cayzlh
    target: _blank
    icon: fa-github
    txt:
  - url: https://twitter.com/Q2F5emxo
    target: _blank
    icon: fa-twitter
    txt:
  - url: mailto:chenanyu@cayzlh.com
    target: _blank
    icon:
    txt: 邮
```

显示在页面下方和首页的右侧上方

### favicon

配置站点的favicon icon

```yml
favicon: /favicon.svg  # 支持各种格式
```

### 精选文章

在首页的右侧展示精选文章，相当于置顶🔝，需在文章中添加 `favorite: true` 属性

```yml
favorites:
  enable: true # 是否展示精选文章
  title: 精选文章 # 标题
  num: 3  # 展示多少个， 建议不要太多
```

### 开源项目

在首页右侧展示开源项目，布局在*精选文章*的下面，支持github项目

```yml
openSource:
  enable: false # 是否展示
  title: 开源软件
  username: cayzlh # github用户名，用于展示stars 和 forks数
  repos:
    - url: https://github.com/cayzlh/hexo-theme-yummy
      name: hexo-theme-yummy # repo的名称，一定要填对
      title: hexo-theme-yummy # 展示到页面的名称
      description: 移植自Jekyll的一款hexo主题
```

### 白嫖CDN加速

```yml
jsDelivr:
  enable: true
  url: https://cdn.jsdelivr.net/gh/yourgithubname/yourreponame@master # 记得要替换成你的地址
```

本地调试`js`和`css`的时候需要设置成false

### google站点相关设置

```yml
google:
  analytics:  # google 分析
    enable: false
    id: # google analytics ID
  verification: # 验证
    enable: false
    id: # google 站点验证，填你的
```

### ICP

站点备案号，配置后显示在页脚部分

```yml
ICP: # 京ICP备123456789号
```

### 回到最顶端

```yml
top:
  enable: true # 是否开启回到最上面
```

### rss

```yml
# 是否展示页面左下角的rss区域
rss:
  enable: true
```

### 归档页面设置

```yml
# 自定义归档页面的标题和副标题
archive:
  title: All My Blogs
  subtitle: Record the scenery on the road of growth
```

### 分类页面设置

```yml
# 分类页面设置，用于指定分类页的元素的展示，否则按照默认的文案展示
category:
  enable: false
  Git: # 这个个Key要写对应分类的名称，比如分类为Git的页面就如案例所示配置
    title: Git相关文章
    subtitle: git操作相关的文章
```

### 标签页面设置

```yml
# 标签页面设置，用于指定标签的元素的展示，否则按照默认的文案展示
tag:
  enable: false
  Docker:
    title: Docker~~~
    subtitle: docker~~~
```

### copyright

```yml
# 页面下方copyright设置
copyright:
  enable: true
  name: Q2F5emxo
  since: 2020
```

### 文章结尾版权声明

```yml
# 文章结尾设置
postending:
  enable: true # 是否启用
  image: true # 是否在文章结尾显示一个图片
  declaration: # 是否在文章结尾显示版权声明
    enable: true
    copyright: # 版权声明。不配则用默认的文案。支持html代码片段
```

### busuanzi统计

```yml
# busuanzi统计
busuanzi:
  enable: true
  site: # 站点统计配置
    pv: true # 展示站点访问次数
    uv: true # 展示站点访问人次
  post: # 文章统计配置
    pv: true # 展示文章阅读次数
```

### 评论系统

以下评论插件一支持

- gitalk
- gitment
- valine

配置文件，开启其中一个即可。

```yml
# 评论系统，开启相应的评论系统， 将会在你的文章下方展示评论，也可以用文章属性 comments 来控制
comment:
  enable: false  # 是否开启
  gitalk: # gitalk
    enable: false
    owner: # '你的 GitHub ID',
    repo: # '存储评论的 repo',
    oauth:
      clientId: # '你的 client ID'
      clientSecret: # '你的 client secret',
    admin:
  gitment: # gitment
    enable: false
    owner: # '你的 GitHub ID',
    repo: # '存储评论的 repo',
    oauth:
      client_id: # '你的 client ID'
      client_secret: # '你的 client secret',
  valine: # Valine 评论模块的配置，默认为不激活，如要使用，就请激活该配置项，并设置 appId 和 appKey.
    enable: false
    appId: # 你的appid
    appKey: # 你的appkey
    notify: false
    verify: false
    visitor: true
    avatar: 'mm' # Gravatar style : mm/identicon/monsterid/wavatar/retro/hide
    pageSize: 10
    placeholder: 'just go go' # Comment Box placeholder
    guest_info: nick,link,mail # Comment header info
```

### 相关文章推荐

启用相关文章推荐，在文章结尾处显示相关文章， 根据标签关联。

```yml
popular_posts:
  enable: false
  title: 相关推荐
  max: 6
```

### 博客引流到公众号

```yml
# 公众号引流，需要插件 https://github.com/snowdreams1006/hexo-plugin-readmore
# 需要去 https://my.openwrite.cn 注册一个账号并开通增长工具：博客导流公众号
readmore:
  blogId: # 填写已申请的博客 id
  name:  # 填写已申请的博客名称
  qrcode: # 填写已申请的公众号二维码链接
  keyword: # 填写已申请的公众号回复关键字
```

### 其他

代码过于简单，没啥好说的了。。

# License

[MIT License](https://github.com/cayzlh/cayzlh.github.io/blob/master/LICENSE)

Copyright (c) 2020 Q2F5emxo




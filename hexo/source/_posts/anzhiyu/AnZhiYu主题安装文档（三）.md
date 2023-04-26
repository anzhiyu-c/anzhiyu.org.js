---
title: AnZhiYu主题安装文档（三）
highlight_shrink: false
categories: AnZhiYu
tags:
  - AnZhiYu
  - Hexo
top_img: "https://img02.anzhiy.cn/adminuploads/1/2023/04/10/6434093a75888.webp!topimg"
cover: "https://img02.anzhiy.cn/adminuploads/1/2023/04/10/6434093a75888.webp!cover"
abbrlink: acbc
date: 2023-04-10 21:55:44
comments:
---

{% note warning %}
本教程更新于 2023 年 4 月 24 日，教程的内容针对最新的 anzhiyu 主题(如果你是旧版本，教程会有出入，请留意)
🐟 安知鱼 已经更新到 [1.1.8](https://github.com/anzhiyu-c/hexo-theme-anzhiyu/releases/tag/1.1.8)
{% endnote %}

## Footer 设置

`since` 是一个来展示你站点起始时间的选项。它位于页面的最底部。

```yaml
# Footer Settings
# --------------------------------------
footer:
  owner:
    enable: true
    since: 2020
  custom_text:
  runtime:
    enable: true
    launch_time: 04/01/2021 00:00:00 # 网站上线时间
    work_img: https://npm.elemecdn.com/anzhiyu-blog@2.0.4/img/badge/安知鱼-上班摸鱼中.svg
    work_description: 距离月入25k也就还差一个大佬带我~
    offduty_img: https://npm.elemecdn.com/anzhiyu-blog@2.0.4/img/badge/安知鱼-下班啦.svg
    offduty_description: 下班了就该开开心心的玩耍，嘿嘿~
  # 徽标部分配置项 https://shields.io/
  # https://img.shields.io/badge/CDN-jsDelivr-orange?style=flat&logo=jsDelivr
  bdageitem:
    - link: https://hexo.io/ #徽标指向网站链接
      shields: https://npm.elemecdn.com/anzhiyu-blog@2.1.5/img/badge/Frame-Hexo.svg #徽标API
      message: 博客框架为Hexo_v5.4.0 #徽标提示语
    - link: https://anzhiy.cn/
      shields: https://pan.anzhiy.cn/d/anzhiyu/svg/Theme-AnZhiYu-2E67D3.svg
      message: 本站使用AnZhiYu主题
    - link: https://www.dogecloud.com/
      shields: https://npm.elemecdn.com/anzhiyu-blog@2.2.0/img/badge/CDN-多吉云-3693F3.svg
      message: 本站使用多吉云为静态资源提供CDN加速
    - link: https://github.com/
      shields: https://npm.elemecdn.com/anzhiyu-blog@2.1.5/img/badge/Source-Github.svg
      message: 本站项目由Github托管
    - link: http://creativecommons.org/licenses/by-nc-sa/4.0/
      shields: https://npm.elemecdn.com/anzhiyu-blog@2.2.0/img/badge/Copyright-BY-NC-SA.svg
      message: 本站采用知识共享署名-非商业性使用-相同方式共享4.0国际许可协议进行许可
```

| 参数                        | 解释                                       |
| --------------------------- | ------------------------------------------ |
| owner                       | 页脚网站所有者@2020-当前年份               |
| owner.enable                | 页脚网站所有者是否启用                     |
| owner.since                 | 页脚年份，控制台中打印的运行时间也来自这里 |
| runtime                     | 运行时间                                   |
| runtime.enable              | 运行时间是否启用                           |
| runtime.launch_time         | 网站上线时间                               |
| runtime.work_img            | 页脚上班时间的徽标                         |
| runtime.work_description    | 页脚上班时间的 title 描述                  |
| runtime.offduty_img         | 页脚下班时间的徽标                         |
| runtime.offduty_description | 页脚下班时间的 title 描述                  |
| bdageitem                   | 徽标配置项                                 |
| bdageitem.link              | 徽标配置链接                               |
| bdageitem.shields           | 徽标配置徽标                               |
| bdageitem.message           | 徽标配置徽标 title                         |

![页脚](https://img02.anzhiy.cn/adminuploads/1/2023/04/20/64412c4c08266.png!blogimg)

![页脚你好自动定义文字](https://img02.anzhiy.cn/adminuploads/1/2023/04/20/64412cb6bbbf5.png!blogimg)

## 侧边栏设置 (aside)

可自行决定哪个项目需要显示，可决定位置，也可以设置不显示侧边栏。

修改 `主题配置文件`

```yaml
# aside (侧边栏)
# --------------------------------------

aside:
  enable: true
  hide: false
  button: true
  mobile: true # display on mobile
  position: right # left or right
  display:
    archive: true
    tag: true
    category: false
  card_author:
    enable: true
    type: 2 # 1为使用头像card 2为不使用头像card
    description: <div style="line-height:1.38;margin:0.6rem 0;text-align:justify;color:rgba(255, 255, 255, 0.8);">这有关于<b style="color:#fff">产品、设计、开发</b>相关的问题和看法，还有<b style="color:#fff">文章翻译</b>和<b style="color:#fff">分享</b>。</div><div style="line-height:1.38;margin:0.6rem 0;text-align:justify;color:rgba(255, 255, 255, 0.8);">相信你可以在这里找到对你有用的<b style="color:#fff">知识</b>和<b style="color:#fff">教程</b>。</div>
    button:
      enable: true
      icon: anzhiyu-icon-arrow-circle-right
      text: 了解更多
      link: /about/
  card_announcement:
    enable: false
    content: 欢迎来看我的博客鸭~
  card_weixin:
    enable: true
    face: https://img02.anzhiy.cn/adminuploads/1/2022/09/11/631ddb7c9b250.png
    backFace: https://img02.anzhiy.cn/adminuploads/1/2022/09/11/631ddeb0900b7.png
  card_recent_post:
    enable: true
    limit: 5 # if set 0 will show all
    sort: date # date or updated
    sort_order: # Don't modify the setting unless you know how it works
  card_categories:
    enable: false
    limit: 8 # if set 0 will show all
    expand: none # none/true/false
    sort_order: # Don't modify the setting unless you know how it works
  card_tags:
    enable: true
    limit: 40 # if set 0 will show all
    color: true
    sort_order: # Don't modify the setting unless you know how it works
  card_archives:
    enable: true
    type: monthly # yearly or monthly
    format: MMMM YYYY # eg: YYYY年MM月
    order: -1 # Sort of order. 1, asc for ascending; -1, desc for descending
    limit: 8 # if set 0 will show all
    sort_order: # Don't modify the setting unless you know how it works
  card_webinfo:
    enable: true
    post_count: true
    last_push_date: true
    sort_order: # Don't modify the setting unless you know how it works
```

## 访问人数 busuanzi (UV 和 PV)

访问 busuanzi 的[官方网站](http://busuanzi.ibruce.info/)查看更多的介绍。

修改 `主题配置文件`

```yaml
busuanzi:
  site_uv: true
  site_pv: true
  page_pv: true
```

> 如果需要修改 busuanzi 的 CDN 链接，可通过 主题配置文件 的 CDN 中的 option 进行修改

```yaml
CDN:
  option:
  	busuanzi: xxxxxxxxx
```

![](https://img02.anzhiy.cn/adminuploads/1/2023/04/20/6441312192cba.png)

![](https://img02.anzhiy.cn/adminuploads/1/2023/04/20/6441312d5e8d0.webp!blogimg)

## 运行时间

网页已运行时间

修改 `主题配置文件`

```yml
# Time difference between publish date and now (网页运行时间)
# Formal: Month/Day/Year Time or Year/Month/Day Time
runtimeshow:
  enable: true
  publish_date: 4/1/2021 00:00:00
```

![运行时间](https://img02.anzhiy.cn/adminuploads/1/2023/04/20/6441319e80977.webp)

## 最新评论

最新评论只会在刷新时才会去读取，并不会实时变化

由于 API 有 访问次数限制，为了避免调用太多，主题默认存取期限为 10 分钟。也就是説，调用后资料会存在 localStorage 里，10 分钟内刷新网站只会去 localStorage 读取资料。 10 分钟期限一过，刷新页面时才会去调取 API 读取新的数据。（ 3.6.0 新增了 storage 配置，可自行配置缓存时间）

在侧边栏显示最新评论板块

修改 `主题配置文件`

```yaml
# Aside widget - Newest Comments
newest_comments:
  enable: true
  sort_order: # Don't modify the setting unless you know how it works
  limit: 6
  storage: 10 # unit: mins, save data to localStorage
  avatar: true
```

| 配置    | 解释                    |
| ------- | ----------------------- |
| limit   | 显示的数量              |
| storage | 设置缓存时间，单位 分钟 |
| avatar  | 是否显示头像            |

![](https://img02.anzhiy.cn/adminuploads/1/2023/04/20/644132e885d91.webp!blogimg)

## 右下角按钮 (Bottom right button)

### 简繁转换

简体繁体互换

右下角会有简繁转换按钮。

修改 `主题配置文件`

```yml
translate:
  enable: true
  # 默认按钮显示文字(网站是简体，应设置为'default: 繁')
  default: 简
  #网站默认语言，1: 繁体中文, 2: 简体中文
  defaultEncoding: 1
  #延迟时间,若不在前, 要设定延迟翻译时间, 如100表示100ms,默认为0
  translateDelay: 0
  #当文字是简体时，按钮显示的文字
  msgToTraditionalChinese: "繁"
  #当文字是繁体时，按钮显示的文字
  msgToSimplifiedChinese: "简"
```

> 简体

![简体](https://img02.anzhiy.cn/adminuploads/1/2023/04/20/644133ef810f7.webp)

> 繁体

![繁体](https://img02.anzhiy.cn/adminuploads/1/2023/04/20/644133ef85f42.webp)

### 阅读模式

阅读模式下会去掉除文章外的内容，避免干扰阅读。

只会出现在文章页面，右下角会有阅读模式按钮。

修改 `主题配置文件`

```yaml
readmode: true
```

![阅读模式](https://img02.anzhiy.cn/adminuploads/1/2023/04/20/6441350b98041.webp)

### 夜间模式

右下角会有夜间模式按钮

修改 `主题配置文件`

```yaml
# dark mode
darkmode:
  enable: true
  # Toggle Button to switch dark/light mode
  button: true
  # Switch dark/light mode automatically (自动切换 dark mode和 light mode)
  # autoChangeMode: 1  Following System Settings, if the system doesn't support dark mode, it will switch dark mode between 6 pm to 6 am
  # autoChangeMode: 2  Switch dark mode between 6 pm to 6 am
  # autoChangeMode: false
  autoChangeMode: 1
  # Set the light mode time. The value is between 0 and 24. If not set, the default value is 6 and 18
  start: # 8
  end: # 22
```

| 参数           | 解释                                                                                                                                                                                                                                     |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| button         | 是否在右下角显示日夜模式切换按钮                                                                                                                                                                                                         |
| autoChangeMode | 自动切换的模式                                                                                                                                                                                                                           |
| autoChangeMode | autoChangeMode: 1 跟随系统而变化，不支持的浏览器/系统将按照时间 start 到 end 之间切换为 light mode<br/>autoChangeMode: 2 只按照时间 start 到 end 之间切换为 light mode ,其余时间为 dark mode<br/>autoChangeMode: false 取消自动切换<br/> |
| start          | light mode 的开始时间                                                                                                                                                                                                                    |
| end            | light mode 的结束时间                                                                                                                                                                                                                    |

## 按钮排序

```yaml
# Don't modify the following settings unless you know how they work (非必要请不要修改 )
# Choose: readmode,translate,darkmode,hideAside,toc,chat,comment
# Don't repeat 不要重复
rightside_item_order:
  enable: false
  hide: # readmode,translate,darkmode,hideAside
  show: # toc,chat,comment
```

## 标签外挂（Tag Plugins）

{% note info %}
标签外挂是 Hexo 独有的功能，并不是标准的 Markdown 格式。
以下的写法，只适用于 AnZhiYu 主题，用在其它主题上不会有效果，甚至可能会报错。使用前请留意
{% endnote %}

{% note warning %}
标签外挂虽然能为主题带来一些额外的功能和 UI 方面的强化，但是，标签外挂也有明显的限制，使用时请留意。
{% endnote %}

### Note (Bootstrap Callout)

{% tabs note,4 %}

<!-- tab 通用配置 -->

修改主题配置文件

```yml
note:
  # Note tag style values:
  #  - simple    bs-callout old alert style. Default.
  #  - modern    bs-callout new (v2-v3) alert style.
  #  - flat      flat callout style with background, like on Mozilla or StackOverflow.
  #  - disabled  disable all CSS styles import of note tag.
  style: simple
  icons: false
  border_radius: 3
  # Offset lighter of background in % for modern and flat styles (modern: -12 | 12; flat: -18 | 6).
  # Offset also applied to label tag variables. This option can work with disabled note tag.
  light_bg_offset: 0
```

`Note`标签外挂有两种用法。`icons`和`light_bg_offset`只对方法一生效。

`fontawesome`图标需开启主题配置文件中`icons.fontawesome`

<!-- endtab -->
<!-- tab 语法格式 -->

{% folding, 方法一 %}

```markdown
{% note [class] [no-icon] [style] %}
Any content (support inline tags too.io).
{% endnote %}
```

{% endfolding %}

{% folding , 方法二 %}

```markdown
{% note [color] [icon] [style] %}
Any content (support inline tags too.io).
{% endnote %}
```

{% endfolding %}

<!-- endtab -->
<!-- tab 配置参数 -->

{% folding , 方法一 %}
|参数|用法|
|:--|:-------------|
|class|【可选】标识，不同的标识有不同的配色<br>（ default / primary / success / info / warning / danger ）|
|no-icon|【可选】不显示 icon|
|style| 【可选】可以覆盖配置中的 style<br>（simple/modern/flat/disabled）|
{% endfolding %}
{% folding, 方法二 %}
|参数|用法|
|:--|:-------------|
|class|【可选】标识，不同的标识有不同的配色<br>（ default / blue / pink / red / purple / orange / green ）|
|no-icon|【可选】可配置自定义 icon (支持 fontawesome 图标和主题内置的阿里图标,`fontawesome`图标需开启主题配置文件中`icons.fontawesome`, 也可以配置 no-icon )|
|style| 【可选】可以覆盖配置中的 style<br>（simple/modern/flat/disabled）|
{% endfolding %}

<!-- endtab -->
<!-- tab 样式预览 -->

{% folding, 方法一 %}

1. `simple`样式
   {% note simple %}默认 提示块标签{% endnote %}
   {% note default simple %}default 提示块标签{% endnote %}
   {% note primary simple %}primary 提示块标签{% endnote %}
   {% note success simple %}success 提示块标签{% endnote %}
   {% note info simple %}info 提示块标签{% endnote %}
   {% note warning simple %}warning 提示块标签{% endnote %}
   {% note danger simple %}danger 提示块标签{% endnote %}

2. `modern`样式
   {% note modern %}默认 提示块标签{% endnote %}
   {% note default modern %}default 提示块标签{% endnote %}
   {% note primary modern %}primary 提示块标签{% endnote %}
   {% note success modern %}success 提示块标签{% endnote %}
   {% note info modern %}info 提示块标签{% endnote %}
   {% note warning modern %}warning 提示块标签{% endnote %}
   {% note danger modern %}danger 提示块标签{% endnote %}

3. `flat`样式
   {% note flat %}默认 提示块标签{% endnote %}
   {% note default flat %}default 提示块标签{% endnote %}
   {% note primary flat %}primary 提示块标签{% endnote %}
   {% note success flat %}success 提示块标签{% endnote %}
   {% note info flat %}info 提示块标签{% endnote %}
   {% note warning flat %}warning 提示块标签{% endnote %}
   {% note danger flat %}danger 提示块标签{% endnote %}

4. `disabled`样式
   {% note disabled %}默认 提示块标签{% endnote %}
   {% note default disabled %}default 提示块标签{% endnote %}
   {% note primary disabled %}primary 提示块标签{% endnote %}
   {% note success disabled %}success 提示块标签{% endnote %}
   {% note info disabled %}info 提示块标签{% endnote %}
   {% note warning disabled %}warning 提示块标签{% endnote %}
   {% note danger disabled %}danger 提示块标签{% endnote %}

5. `no-icon`样式
   {% note no-icon %}默认 提示块标签{% endnote %}
   {% note default no-icon %}default 提示块标签{% endnote %}
   {% note primary no-icon %}primary 提示块标签{% endnote %}
   {% note success no-icon %}success 提示块标签{% endnote %}
   {% note info no-icon %}info 提示块标签{% endnote %}
   {% note warning no-icon %}warning 提示块标签{% endnote %}
   {% note danger no-icon %}danger 提示块标签{% endnote %}

{% endfolding %}
{% folding, 方法二 %}

图标支持 `fontawesome` 和 `主题内置的阿里图标`，使用方法为加上对应的类名，`fontawesome`图标需开启主题配置文件中`icons.fontawesome`，默认未开启 fontawesome

1.  simple 样式
    `主题内置阿里图标`
    {% note 'anzhiyufont anzhiyu-icon-rocket' simple %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'anzhiyufont anzhiyu-icon-bullhorn' simple %}2022 年快到了....{% endnote %}
    {% note pink 'anzhiyufont anzhiyu-icon-instagram' simple %}小心开车 安全至上{% endnote %}
    {% note red 'anzhiyufont anzhiyu-icon-fan' simple%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'anzhiyufont anzhiyu-icon-dengpao' simple %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'anzhiyufont anzhiyu-icon-sanmingzhi' simple %}剪刀石头布{% endnote %}
    {% note green 'anzhiyufont anzhiyu-icon-ic_train' simple %}前端最讨厌的浏览器{% endnote %}
    <p><code>fontawesome 图标</code>，开启主题配置文件中的<code>icons.fontawesome</code>为<code>true</code>后可见</p>
    {% note 'fab fa-cc-visa' simple %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'fas fa-bullhorn' simple %}2022 年快到了....{% endnote %}
    {% note pink 'fas fa-car-crash' simple %}小心开车 安全至上{% endnote %}
    {% note red 'icon-fan' simple%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'fas fa-battery-half' simple %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'far fa-hand-scissors' simple %}剪刀石头布{% endnote %}
    {% note green 'fab fa-internet-explorer' simple %}前端最讨厌的浏览器{% endnote %}

2.  modern 样式
    `主题内置阿里图标`
    {% note 'anzhiyufont anzhiyu-icon-rocket' modern %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'anzhiyufont anzhiyu-icon-bullhorn' modern %}2022 年快到了....{% endnote %}
    {% note pink 'anzhiyufont anzhiyu-icon-instagram' modern %}小心开车 安全至上{% endnote %}
    {% note red 'anzhiyufont anzhiyu-icon-fan' modern%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'anzhiyufont anzhiyu-icon-dengpao' modern %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'anzhiyufont anzhiyu-icon-sanmingzhi' modern %}剪刀石头布{% endnote %}
    {% note green 'anzhiyufont anzhiyu-icon-ic_train' modern %}前端最讨厌的浏览器{% endnote %}
    <p><code>fontawesome 图标</code>，开启主题配置文件中的<code>icons.fontawesome</code>为<code>true</code>后可见</p>
    {% note 'fab fa-cc-visa' modern %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'fas fa-bullhorn' modern %}2021 年快到了....{% endnote %}
    {% note pink 'fas fa-car-crash' modern %}小心开车 安全至上{% endnote %}
    {% note red 'icon-fan' modern%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'fas fa-battery-half' modern %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'far fa-hand-scissors' modern %}剪刀石头布{% endnote %}
    {% note green 'fab fa-internet-explorer' modern %}前端最讨厌的浏览器{% endnote %}

3.  flat 样式
    `主题内置阿里图标`
    {% note 'anzhiyufont anzhiyu-icon-rocket' flat %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'anzhiyufont anzhiyu-icon-bullhorn' flat %}2022 年快到了....{% endnote %}
    {% note pink 'anzhiyufont anzhiyu-icon-instagram' flat %}小心开车 安全至上{% endnote %}
    {% note red 'anzhiyufont anzhiyu-icon-fan' flat%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'anzhiyufont anzhiyu-icon-dengpao' flat %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'anzhiyufont anzhiyu-icon-sanmingzhi' flat %}剪刀石头布{% endnote %}
    {% note green 'anzhiyufont anzhiyu-icon-ic_train' flat %}前端最讨厌的浏览器{% endnote %}
    <p><code>fontawesome 图标</code>，开启主题配置文件中的<code>icons.fontawesome</code>为<code>true</code>后可见</p>
    {% note 'fab fa-cc-visa' flat %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'fas fa-bullhorn' flat %}2021 年快到了....{% endnote %}
    {% note pink 'fas fa-car-crash' flat %}小心开车 安全至上{% endnote %}
    {% note red 'icon-fan' flat%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'fas fa-battery-half' flat %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'far fa-hand-scissors' flat %}剪刀石头布{% endnote %}
    {% note green 'fab fa-internet-explorer' flat %}前端最讨厌的浏览器{% endnote %}

4.  disabled 样式
    `主题内置阿里图标`
    {% note 'anzhiyufont anzhiyu-icon-rocket' disabled %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'anzhiyufont anzhiyu-icon-bullhorn' disabled %}2022 年快到了....{% endnote %}
    {% note pink 'anzhiyufont anzhiyu-icon-instagram' disabled %}小心开车 安全至上{% endnote %}
    {% note red 'anzhiyufont anzhiyu-icon-fan' disabled%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'anzhiyufont anzhiyu-icon-dengpao' disabled %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'anzhiyufont anzhiyu-icon-sanmingzhi' disabled %}剪刀石头布{% endnote %}
    {% note green 'anzhiyufont anzhiyu-icon-ic_train' disabled %}前端最讨厌的浏览器{% endnote %}
    <p><code>fontawesome 图标</code>，开启主题配置文件中的<code>icons.fontawesome</code>为<code>true</code>后可见</p>
    {% note 'fab fa-cc-visa' disabled %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'fas fa-bullhorn' disabled %}2021 年快到了....{% endnote %}
    {% note pink 'fas fa-car-crash' disabled %}小心开车 安全至上{% endnote %}
    {% note red 'icon-fan' disabled %}这是三片呢？还是四片？{% endnote %}
    {% note orange 'fas fa-battery-half' disabled %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'far fa-hand-scissors' disabled %}剪刀石头布{% endnote %}
    {% note green 'fab fa-internet-explorer' disabled %}前端最讨厌的浏览器{% endnote %}

5.  no-icon 样式
    {% note no-icon %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue no-icon %}2021 年快到了....{% endnote %}
    {% note pink no-icon %}小心开车 安全至上{% endnote %}
    {% note red no-icon %}这是三片呢？还是四片？{% endnote %}
    {% note orange no-icon %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple no-icon %}剪刀石头布{% endnote %}
    {% note green no-icon %}前端最讨厌的浏览器{% endnote %}

{% endfolding %}

<!-- endtab -->
<!-- tab 示例源码 -->

{% folding, 方法一 %}

1. `simple`样式

   ```markdown
   {% note simple %}默认 提示块标签{% endnote %}
   {% note default simple %}default 提示块标签{% endnote %}
   {% note primary simple %}primary 提示块标签{% endnote %}
   {% note success simple %}success 提示块标签{% endnote %}
   {% note info simple %}info 提示块标签{% endnote %}
   {% note warning simple %}warning 提示块标签{% endnote %}
   {% note danger simple %}danger 提示块标签{% endnote %}
   ```

2. `modern`样式
   ```markdown
   {% note modern %}默认 提示块标签{% endnote %}
   {% note default modern %}default 提示块标签{% endnote %}
   {% note primary modern %}primary 提示块标签{% endnote %}
   {% note success modern %}success 提示块标签{% endnote %}
   {% note info modern %}info 提示块标签{% endnote %}
   {% note warning modern %}warning 提示块标签{% endnote %}
   {% note danger modern %}danger 提示块标签{% endnote %}
   ```
3. `flat`样式
   ```markdown
   {% note flat %}默认 提示块标签{% endnote %}
   {% note default flat %}default 提示块标签{% endnote %}
   {% note primary flat %}primary 提示块标签{% endnote %}
   {% note success flat %}success 提示块标签{% endnote %}
   {% note info flat %}info 提示块标签{% endnote %}
   {% note warning flat %}warning 提示块标签{% endnote %}
   {% note danger flat %}danger 提示块标签{% endnote %}
   ```
4. `disabled`样式

   ```markdown
   {% note disabled %}默认 提示块标签{% endnote %}
   {% note default disabled %}default 提示块标签{% endnote %}
   {% note primary disabled %}primary 提示块标签{% endnote %}
   {% note success disabled %}success 提示块标签{% endnote %}
   {% note info disabled %}info 提示块标签{% endnote %}
   {% note warning disabled %}warning 提示块标签{% endnote %}
   {% note danger disabled %}danger 提示块标签{% endnote %}
   ```

5. `no-icon`样式
   ```markdown
   {% note no-icon %}默认 提示块标签{% endnote %}
   {% note default no-icon %}default 提示块标签{% endnote %}
   {% note primary no-icon %}primary 提示块标签{% endnote %}
   {% note success no-icon %}success 提示块标签{% endnote %}
   {% note info no-icon %}info 提示块标签{% endnote %}
   {% note warning no-icon %}warning 提示块标签{% endnote %}
   {% note danger no-icon %}danger 提示块标签{% endnote %}
   ```

{% endfolding %}
{% folding, 方法二 %}

图标支持 `fontawesome` 和 `主题内置的阿里图标`，使用方法为加上对应的类名，`fontawesome`图标需开启主题配置文件中`icons.fontawesome`，默认未开启 fontawesome

1.  simple 样式
    `主题内置阿里图标`

    ```markdown
    {% note 'anzhiyufont anzhiyu-icon-rocket' simple %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'anzhiyufont anzhiyu-icon-bullhorn' simple %}2022 年快到了....{% endnote %}
    {% note pink 'anzhiyufont anzhiyu-icon-instagram' simple %}小心开车 安全至上{% endnote %}
    {% note red 'anzhiyufont anzhiyu-icon-fan' simple%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'anzhiyufont anzhiyu-icon-dengpao' simple %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'anzhiyufont anzhiyu-icon-sanmingzhi' simple %}剪刀石头布{% endnote %}
    {% note green 'anzhiyufont anzhiyu-icon-ic_train' simple %}前端最讨厌的浏览器{% endnote %}
    ```

    <p><code>fontawesome 图标</code>，开启主题配置文件中的<code>icons.fontawesome</code>为<code>true</code>后可见</p>
    ```markdown
    {% note 'fab fa-cc-visa' simple %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'fas fa-bullhorn' simple %}2022 年快到了....{% endnote %}
    {% note pink 'fas fa-car-crash' simple %}小心开车 安全至上{% endnote %}
    {% note red 'icon-fan' simple%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'fas fa-battery-half' simple %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'far fa-hand-scissors' simple %}剪刀石头布{% endnote %}
    {% note green 'fab fa-internet-explorer' simple %}前端最讨厌的浏览器{% endnote %}
    ```

2.  modern 样式
    `主题内置阿里图标`

    ```markdown
    {% note 'anzhiyufont anzhiyu-icon-rocket' modern %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'anzhiyufont anzhiyu-icon-bullhorn' modern %}2022 年快到了....{% endnote %}
    {% note pink 'anzhiyufont anzhiyu-icon-instagram' modern %}小心开车 安全至上{% endnote %}
    {% note red 'anzhiyufont anzhiyu-icon-fan' modern%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'anzhiyufont anzhiyu-icon-dengpao' modern %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'anzhiyufont anzhiyu-icon-sanmingzhi' modern %}剪刀石头布{% endnote %}
    {% note green 'anzhiyufont anzhiyu-icon-ic_train' modern %}前端最讨厌的浏览器{% endnote %}
    ```

    <p><code>fontawesome 图标</code>，开启主题配置文件中的<code>icons.fontawesome</code>为<code>true</code>后可见</p>
    ```markdown
    {% note 'fab fa-cc-visa' modern %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'fas fa-bullhorn' modern %}2021 年快到了....{% endnote %}
    {% note pink 'fas fa-car-crash' modern %}小心开车 安全至上{% endnote %}
    {% note red 'icon-fan' modern%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'fas fa-battery-half' modern %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'far fa-hand-scissors' modern %}剪刀石头布{% endnote %}
    {% note green 'fab fa-internet-explorer' modern %}前端最讨厌的浏览器{% endnote %}
    ```

3.  flat 样式
    `主题内置阿里图标`

    ```markdown
    {% note 'anzhiyufont anzhiyu-icon-rocket' flat %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'anzhiyufont anzhiyu-icon-bullhorn' flat %}2022 年快到了....{% endnote %}
    {% note pink 'anzhiyufont anzhiyu-icon-instagram' flat %}小心开车 安全至上{% endnote %}
    {% note red 'anzhiyufont anzhiyu-icon-fan' flat%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'anzhiyufont anzhiyu-icon-dengpao' flat %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'anzhiyufont anzhiyu-icon-sanmingzhi' flat %}剪刀石头布{% endnote %}
    {% note green 'anzhiyufont anzhiyu-icon-ic_train' flat %}前端最讨厌的浏览器{% endnote %}
    ```

    ```markdown
    <p><code>fontawesome 图标</code>，开启主题配置文件中的<code>icons.fontawesome</code>为<code>true</code>后可见</p>
    {% note 'fab fa-cc-visa' flat %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'fas fa-bullhorn' flat %}2021 年快到了....{% endnote %}
    {% note pink 'fas fa-car-crash' flat %}小心开车 安全至上{% endnote %}
    {% note red 'icon-fan' flat%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'fas fa-battery-half' flat %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'far fa-hand-scissors' flat %}剪刀石头布{% endnote %}
    {% note green 'fab fa-internet-explorer' flat %}前端最讨厌的浏览器{% endnote %}
    ```

4.  disabled 样式
    `主题内置阿里图标`

    ```markdown
    {% note 'anzhiyufont anzhiyu-icon-rocket' disabled %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'anzhiyufont anzhiyu-icon-bullhorn' disabled %}2022 年快到了....{% endnote %}
    {% note pink 'anzhiyufont anzhiyu-icon-instagram' disabled %}小心开车 安全至上{% endnote %}
    {% note red 'anzhiyufont anzhiyu-icon-fan' disabled%}这是三片呢？还是四片？{% endnote %}
    {% note orange 'anzhiyufont anzhiyu-icon-dengpao' disabled %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'anzhiyufont anzhiyu-icon-sanmingzhi' disabled %}剪刀石头布{% endnote %}
    {% note green 'anzhiyufont anzhiyu-icon-ic_train' disabled %}前端最讨厌的浏览器{% endnote %}
    ```

    <p><code>fontawesome 图标</code>，开启主题配置文件中的<code>icons.fontawesome</code>为<code>true</code>后可见</p>
    ```markdown
    {% note 'fab fa-cc-visa' disabled %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue 'fas fa-bullhorn' disabled %}2021 年快到了....{% endnote %}
    {% note pink 'fas fa-car-crash' disabled %}小心开车 安全至上{% endnote %}
    {% note red 'icon-fan' disabled %}这是三片呢？还是四片？{% endnote %}
    {% note orange 'fas fa-battery-half' disabled %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple 'far fa-hand-scissors' disabled %}剪刀石头布{% endnote %}
    {% note green 'fab fa-internet-explorer' disabled %}前端最讨厌的浏览器{% endnote %}
    ```

5.  no-icon 样式
    ```markdown
    {% note no-icon %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note blue no-icon %}2021 年快到了....{% endnote %}
    {% note pink no-icon %}小心开车 安全至上{% endnote %}
    {% note red no-icon %}这是三片呢？还是四片？{% endnote %}
    {% note orange no-icon %}你是刷 Visa 还是 UnionPay{% endnote %}
    {% note purple no-icon %}剪刀石头布{% endnote %}
    {% note green no-icon %}前端最讨厌的浏览器{% endnote %}
    ```

{% endfolding %}

<!-- endtab -->

{% endtabs %}

### Gallery 相册图库

一个图库集合。

{% tabs gallery,3 %}

<!-- tab 标签语法 -->

1.  gallerygroup 相册图库

    ```markdown
    <div class="gallery-group-main">
    {% galleryGroup name description link img-url %}
    {% galleryGroup name description link img-url %}
    {% galleryGroup name description link img-url %}
    </div>
    ```

2.  gallery 相册

{% tabs Gallery相册 %}

<!-- tab 本地 -->

```markdown
{% gallery %}
markdown 图片格式
{% endgallery %}

{% gallery true,220,10 %}
markdown 图片格式
{% endgallery %}

{% gallery true,,10 %}
markdown 图片格式
{% endgallery %}
```

| 参数名    | 释义                                                                                 |
| --------- | ------------------------------------------------------------------------------------ |
| lazyload  | 【可选】点击按钮加载更多图片，填写 true/false。默认为 `false`。                      |
| rowHeight | 【可选】图片显示的高度，如果需要一行显示更多的图片，可设置更小的数字。默认为 `220`。 |
| limit     | 【可选】每次加载多少张照片。默认为 `10`。                                            |

<!-- endtab -->

<!-- tab 远程 -->

```markdown
{% gallery url,[link],[lazyload],[rowHeight],[limit] %}
{% endgallery %}
```

| 参数名    | 释义                                                                                 |
| --------- | ------------------------------------------------------------------------------------ |
| url       | 【必须】 识别词                                                                      |
| link      | 【必须】远程的 json 链接                                                             |
| lazyload  | 【可选】点击按钮加载更多图片，填写 true/false。默认为 `false`。                      |
| rowHeight | 【可选】图片显示的高度，如果需要一行显示更多的图片，可设置更小的数字。默认为 `220`。 |
| limit     | 【可选】每次加载多少张照片。默认为 `10`。                                            |

> 远程链接 Json 的例子

有三个参数，`url`是必须存在的，`alt` 和 `title` 可有，也可没有。

```json
[
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0556.jpg",
    "alt": "IMG_0556.jpg",
    "title": "这是title"
  },
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0472.jpg",
    "alt": "IMG_0472.jpg"
  },
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0453.jpg",
    "alt": ""
  },
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0931.jpg",
    "alt": ""
  }
]
```

> 示例

```markdown
{% gallery url,https://xxxx.com/sss.json %}
{% endgallery %}

{% gallery url,https://xxxx.com/sss.json,true,220,10 %}
{% endgallery %}

{% gallery url,https://xxxx.com/sss.json,true,,10 %}
{% endgallery %}
```

<!-- endtab -->

{% endtabs%}

<!-- endtab -->

<!-- tab 参数配置 -->

- gallerygroup 相册图库

  | 参数名      | 释义                 |
  | :---------- | :------------------- |
  | name        | 图库名字             |
  | description | 图库描述             |
  | link        | 链接到对应相册的地址 |
  | img-url     | 图库封面             |

{% note info %}
思维拓展一下，相册图库的实质其实就是个快捷方式，可以自定义添加描述、封面、链接。那么我们未必要把它当做一个相册，完全可以作为一个链接卡片，链接到视频、QQ、友链都是不错的选择。
{% endnote %}

- gallery 相册
  区别于旧版的 Gallery 相册,新的 Gallery 相册会自动根据图片长度进行排版，书写也更加方便，与 markdown 格式一样。可根据需要插入到相应的 md。无需再自己配置长宽。**建议在粘贴时故意使用长短、大小、横竖不一的图片**，会有更好的效果。（尺寸完全相同的图片只会平铺输出，效果很糟糕）

{% tabs Gallery相册参数 %}

<!-- tab 本地 -->

```markdown
{% gallery %}
markdown 图片格式
{% endgallery %}

{% gallery true,220,10 %}
markdown 图片格式
{% endgallery %}

{% gallery true,,10 %}
markdown 图片格式
{% endgallery %}
```

| 参数名    | 释义                                                                                 |
| --------- | ------------------------------------------------------------------------------------ |
| lazyload  | 【可选】点击按钮加载更多图片，填写 true/false。默认为 `false`。                      |
| rowHeight | 【可选】图片显示的高度，如果需要一行显示更多的图片，可设置更小的数字。默认为 `220`。 |
| limit     | 【可选】每次加载多少张照片。默认为 `10`。                                            |

<!-- endtab -->

<!-- tab 远程 -->

```markdown
{% gallery url,[link],[lazyload],[rowHeight],[limit] %}
{% endgallery %}
```

| 参数名    | 释义                                                                                 |
| --------- | ------------------------------------------------------------------------------------ |
| url       | 【必须】 识别词                                                                      |
| link      | 【必须】远程的 json 链接                                                             |
| lazyload  | 【可选】点击按钮加载更多图片，填写 true/false。默认为 `false`。                      |
| rowHeight | 【可选】图片显示的高度，如果需要一行显示更多的图片，可设置更小的数字。默认为 `220`。 |
| limit     | 【可选】每次加载多少张照片。默认为 `10`。                                            |

> 远程链接 Json 的例子

有三个参数，`url`是必须存在的，`alt` 和 `title` 可有，也可没有。

```json
[
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0556.jpg",
    "alt": "IMG_0556.jpg",
    "title": "这是title"
  },
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0472.jpg",
    "alt": "IMG_0472.jpg"
  },
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0453.jpg",
    "alt": ""
  },
  {
    "url": "https://cdn.jsdelivr.net/gh/jerryc127/CDN/img/IMG_0931.jpg",
    "alt": ""
  }
]
```

> 示例

```markdown
{% gallery url,https://xxxx.com/sss.json %}
{% endgallery %}

{% gallery url,https://xxxx.com/sss.json,true,220,10 %}
{% endgallery %}

{% gallery url,https://xxxx.com/sss.json,true,,10 %}
{% endgallery %}
```

<!-- endtab -->

{% endtabs%}

<!-- endtab -->

<!-- tab 样式预览 -->

- gallerygroup 相册图库

<div class="gallery-group-main">
{% galleryGroup MC 在Rikkaの六花服务器里留下的足迹 '/wordScenery/' https://cdn.cbd.int/akilar-candyassets@1.0.36/image/1.jpg %}
{% galleryGroup Gundam 哦咧哇gundam哒！ '/thousand/' https://cdn.cbd.int/akilar-candyassets@1.0.36/image/20200907110508327.png %}
{% galleryGroup I-am-Akilar 某种意义上也算自拍吧 '/wallpaper/' https://cdn.cbd.int/akilar-candyassets@1.0.36/image/20200907113116651.png %}
</div>

- gallery 相册

{% gallery true,,2 %}
![](https://i.loli.net/2019/12/25/Fze9jchtnyJXMHN.jpg)
![](https://i.loli.net/2019/12/25/ryLVePaqkYm4TEK.jpg)
![](https://i.loli.net/2019/12/25/gEy5Zc1Ai6VuO4N.jpg)
![](https://i.loli.net/2019/12/25/d6QHbytlSYO4FBG.jpg)
![](https://i.loli.net/2019/12/25/6nepIJ1xTgufatZ.jpg)
![](https://i.loli.net/2019/12/25/E7Jvr4eIPwUNmzq.jpg)
![](https://i.loli.net/2019/12/25/mh19anwBSWIkGlH.jpg)
![](https://i.loli.net/2019/12/25/2tu9JC8ewpBFagv.jpg)
{% endgallery %}

<!-- endtab -->
<!-- tab 示例源码 -->

{% note info %}
对于很多同学提问的`gallerygroup`和`gallery`相册页的链接问题。这里说下我个人的使用习惯。
一般使用相册图库的话，可以在导航栏加一个 gallery 的 page(**使用指令`hexo new page gallery`添加**)，里面放相册图库作为封面。然后在`[Blogroot]/source/gallery/`下面建立相应的文件夹，例如若按照这里的示例，若欲使用`/gallery/MC/`路径访问 MC 相册，则需要新建`[Blogroot]/source/gallery/MC/index.md`，并在里面填入`gallery`相册内容。

注意 ⚠️：本站相册集为单独优化，可参考[配置相册页面](https://anzhiy.cn/posts/220c.html)。
{% endnote %}

1. gallerygroup 相册图库

   ```markdown
   <div class="gallery-group-main">
   {% galleryGroup MC 在Rikkaの六花服务器里留下的足迹 '/gallery/MC/' https://cdn.cbd.int/akilar-candyassets@1.0.36/image/1.jpg %}
   {% galleryGroup Gundam 哦咧哇gundam哒！ '/gallery/Gundam/' https://cdn.cbd.int/akilar-candyassets@1.0.36/image/20200907110508327.png %}
   {% galleryGroup I-am-Akilar 某种意义上也算自拍吧 '/gallery/I-am-Akilar/' https://cdn.cbd.int/akilar-candyassets@1.0.36/image/20200907113116651.png %}
   </div>
   ```

2. gallery 相册

   ```markdown
   {% gallery true,,2 %}
   ![](https://i.loli.net/2019/12/25/Fze9jchtnyJXMHN.jpg)
   ![](https://i.loli.net/2019/12/25/ryLVePaqkYm4TEK.jpg)
   ![](https://i.loli.net/2019/12/25/gEy5Zc1Ai6VuO4N.jpg)
   ![](https://i.loli.net/2019/12/25/d6QHbytlSYO4FBG.jpg)
   ![](https://i.loli.net/2019/12/25/6nepIJ1xTgufatZ.jpg)
   ![](https://i.loli.net/2019/12/25/E7Jvr4eIPwUNmzq.jpg)
   ![](https://i.loli.net/2019/12/25/mh19anwBSWIkGlH.jpg)
   ![](https://i.loli.net/2019/12/25/2tu9JC8ewpBFagv.jpg)
   {% endgallery %}
   ```

<!-- endtab -->

{% endtabs%}

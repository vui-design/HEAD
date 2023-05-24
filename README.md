# HEAD

[![Contributors](https://img.shields.io/github/contributors/joshbuchea/head.svg?style=for-the-badge)](https://github.com/joshbuchea/HEAD/graphs/contributors)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg?style=for-the-badge)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Follow @joshbuchea on Mastodon](https://img.shields.io/badge/Follow_@joshbuchea-purple?logo=mastodon&logoColor=white&style=for-the-badge)](https://hachyderm.io/@joshbuchea)

HTML文档 `<head>` 标签内容清单。

## 目录

- [最小推荐](#最小推荐)
- [网页元素](#网页元素)
- [Meta 标签](#meta-标签)
- [链接](#链接)
- [网站图标](#网站图标)
- [社交](#社交)
  - [Facebook Open Graph](#facebook-open-graph)
  - [Twitter Card](#twitter-card)
  - [Google+ / Schema.org](#google--schemaorg)
  - [Facebook Instant Articles](#facebook-instant-articles)
  - [OEmbed](#oembed)
- [浏览器 / 平台](#浏览器--平台)
  - [Apple iOS](#apple-ios)
  - [Apple Safari](#apple-safari)
  - [Google Android](#google-android)
  - [Google Chrome](#google-chrome)
  - [Google Chrome Mobile (只针对 Android)](#google-chrome-mobile只针对-android)
  - [Microsoft Internet Explorer](#microsoft-internet-explorer)
- [国内的浏览器](#国内的浏览器)
  - [360 浏览器](#360-浏览器)
  - [QQ 移动浏览器](#qq-移动浏览器)
  - [UC 移动浏览器](#uc-移动浏览器)
- [应用链接](#应用链接)
- [注意](#注意)
  - [性能](#性能)
- [其他资源](#其他资源)
- [相关项目](#相关项目)
- [其他格式](#其他格式)
- [翻译](#翻译)
- [贡献](#贡献)
  - [贡献者](#贡献者)
- [作者](#作者)
- [许可](#许可)

## 最小推荐

下面是基本的、最低限度的网站基本标签：

```html
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<!-- 以上 2 个 meta 标签必须放在 <head> 的最前面；任何其他头元素都应该在这些标签后面 -->
<title>页面标题</title>
```

`meta charset` - 设置文档的字符编码，`utf-8` 为标准编码

`meta name="viewport"` - 与移动响应相关的视口设置

`width=device-width` - 使用设备的物理宽度

`initial-scale=1` - 初始缩放，1表示不缩放

**[返回顶部](#目录)**

## 网页元素

有效的 `<head>` 元素包括 `meta`、`link`、`title`、`style`、`script`、`noscript` 和 `base`。

这些元素为 web 技术（如浏览器、搜索引擎、机器人等）应该如何感知和呈现文档提供了信息。

``` html
<!-- 设置文档的字符编码，以便 UTF-8 空间内的所有字符（例如表情符号）正确渲染 -->
<meta charset="utf-8" />

<!-- 设置文档标题 -->
<title>页面标题</title>

<!-- 为文档中的所有相对 URL 设置基本 URL -->
<base href="https://example.com/page.html" />

<!-- 链接外部 CSS 样式文件 -->
<link rel="stylesheet" href="styles.css" />

<!-- 用于添加文档内联 CSS 样式 -->
<style>
  /* ... */
</style>

<!-- JavaScript & No-JavaScript 标签 -->
<script>
  // function(s) go here
</script>
<noscript>
  <!-- 用来定义在脚本未被执行时的替代内容（文本） -->
</noscript>
```

**[返回顶部](#目录)**

## Meta 标签

``` html
<!-- 以下 2 个 meta 标签必须放在 <head> 的最前面；任何其他头元素都应该在这些标签后面 -->
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />

<!-- 允许控制资源的加载位置，应尽可能早地放置在 ＜head＞ 中，因为该标签只适用于在其后面声明的资源 -->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'" />

<!-- Web 应用程序的名称（仅当网站被用作应用程序时才使用）-->
<meta name="application-name" content="Application Name" />

<!-- Chrome、Firefox OS 和 Opera 的主题颜色 -->
<meta name="theme-color" content="#4285f4" />

<!-- 针对页面的简短描述（限制在 150 个字符以内）-->
<!-- 在某些情况下，此内容会被用作搜索引擎结果的一部分 -->
<meta name="description" content="A description of the page" />

<!-- 控制搜索引擎的抓取和索引行为 -->
<meta name="robots" content="index,follow" /><!-- 所有搜索引擎 -->
<meta name="googlebot" content="index,follow" /><!-- 仅对 Google 有效 -->

<!-- 告诉 Google 不显示附加链接搜索框 -->
<meta name="google" content="nositelinkssearchbox" />

<!-- 告诉 Google 不为此页面提供翻译 -->
<meta name="google" content="notranslate" />

<!-- 验证网站所有权 -->
<meta name="google-site-verification" content="verification_token" /><!-- Google Search Console -->
<meta name="yandex-verification" content="verification_token" /><!-- Yandex Webmasters -->
<meta name="msvalidate.01" content="verification_token" /><!-- Bing Webmaster Center -->
<meta name="alexaVerifyID" content="verification_token" /><!-- Alexa Console -->
<meta name="p:domain_verify" content="code_from_pinterest" /><!-- Pinterest Console -->
<meta name="norton-safeweb-site-verification" content="norton_code" /><!-- Norton Safe Web -->

<!-- 确定用于构建页面的软件（如 WordPress、Dreamweaver）-->
<meta name="generator" content="program" />

<!-- 文档主题的简短描述 -->
<meta name="subject" content="your document's subject" />

<!-- 基于网站内容给出一般的年龄分级 -->
<meta name="rating" content="General" />

<!-- 允许控制 referrer 信息如何传递 -->
<meta name="referrer" content="no-referrer" />

<!-- 禁用自动检测和格式化可能的电话号码 -->
<meta name="format-detection" content="telephone=no" />

<!-- 通过设置为 "off" 完全退出 DNS 预取 -->
<meta http-equiv="x-dns-prefetch-control" content="off" />

<!-- 在客户端存储 cookie，web 浏览器的客户端识别 -->
<meta http-equiv="set-cookie" content="name=value; expires=date; path=url" />

<!-- 指定要显示在一个特定框架中的页面 -->
<meta http-equiv="Window-Target" content="_value" />

<!-- 地理标签 -->
<meta name="ICBM" content="latitude, longitude" />
<meta name="geo.position" content="latitude; longitude" />
<meta name="geo.region" content="country[-state]" /><!-- 国家代码 (ISO 3166-1): 强制性；州代码 (ISO 3166-2): 可选；如 content="US" / content="US-NY" -->
<meta name="geo.placename" content="city/town" /><!-- 如 content="New York City" -->

<!-- 网络货币化 https://webmonetization.org/docs/getting-started -->
<meta name="monetization" content="$paymentpointer.example" />
```

- [Google 可以识别的 Meta 标签](https://support.google.com/webmasters/answer/79812?hl=zh-Hans)
- [WHATWG Wiki: Meta 拓展](https://wiki.whatwg.org/wiki/MetaExtensions)
- [ICBM - 维基百科](https://en.wikipedia.org/wiki/ICBM_address#Modern_use)
- [地理标记 - 维基百科](https://en.wikipedia.org/wiki/Geotagging#HTML_pages)

**[返回顶部](#目录)**

## 链接

``` html
<!-- 链接外部 CSS 样式文件 -->
<link rel="stylesheet" href="https://example.com/styles.css" />

<!-- 有助于防止出现内容重复的问题 -->
<link rel="canonical" href="https://example.com/article/?page=2" />

<!-- 指向当前文档的 AMP HTML 版本的链接 -->
<link rel="amphtml" href="https://example.com/path/to/amp-version.html" />

<!-- 指向一个指定 Web 应用程序安装凭据的 JSON 文件 -->
<link rel="manifest" href="manifest.json" />

<!-- 有关文档作者的信息 -->
<link rel="author" href="humans.txt" />

<!-- 链接到该文档的版权信息 -->
<link rel="license" href="copyright.html" />

<!-- 链接到该文档的替代版本（比如打印页、翻译或镜像） -->
<link rel="alternate" href="https://es.example.com/" hreflang="es" />

<!-- 提供有关作者或其他人的信息 -->
<link rel="me" href="https://google.com/profiles/thenextweb" type="text/html" />
<link rel="me" href="mailto:name@example.com" />
<link rel="me" href="sms:+15035550125" />

<!-- 链接到一个描述历史记录、文档或其他具有历史意义的材料的集合的文档 -->
<link rel="archives" href="https://example.com/archives/" />

<!-- 链接到分层结构中的顶级资源 -->
<link rel="index" href="https://example.com/" />

<!-- 提供自我引用 - 当文档有多个可能的引用时很有用 -->
<link rel="self" type="application/atom+xml" href="https://example.com/atomFeed.php?page=3" />

<!-- 分别为一系列文档中的第一个、最后一个、上一个和下一个文档 -->
<link rel="first" href="https://example.com/atomFeed.php" />
<link rel="last" href="https://example.com/atomFeed.php?page=40" />
<link rel="prev" href="https://example.com/atomFeed.php?page=1" />
<link rel="next" href="https://example.com/atomFeed.php?page=3" />

<!-- 当使用第三方服务维护博客时使用 -->
<link rel="EditURI" href="https://example.com/xmlrpc.php?rsd" type="application/rsd+xml" title="RSD" />

<!-- 当另一个 WordPress 博客链接到您的 WordPress 博客或帖子时形成自动评论 -->
<link rel="pingback" href="https://example.com/xmlrpc.php" />

<!-- 当你在页面中链接到一个 url 时通知它 -->
<link rel="webmention" href="https://example.com/webmention" />

<!-- 启用通过 Micropub 客户端发布你的域名 -->
<link rel="micropub" href="https://example.com/micropub" />

<!-- 加载一个外部的 HTML 文件到当前页面 -->
<link rel="import" href="/path/to/component.html" />

<!-- 打开搜索 -->
<link rel="search" href="/open-search.xml" type="application/opensearchdescription+xml" title="Search Title" />

<!-- 提要 -->
<link rel="alternate" href="https://feeds.feedburner.com/example" type="application/rss+xml" title="RSS" />
<link rel="alternate" href="https://example.com/feed.atom" type="application/atom+xml" title="Atom 0.3" />

<!-- 预取、预加载、预浏览 -->
<!-- 更多信息：https://css-tricks.com/prefetching-preloading-prebrowsing/ -->
<link rel="dns-prefetch" href="//example.com/" />
<link rel="preconnect" href="https://www.example.com/" />
<link rel="prefetch" href="https://www.example.com/" />
<link rel="prerender" href="https://example.com/" />
<link rel="preload" href="image.png" as="image" />
```

- [Link Relations](https://www.iana.org/assignments/link-relations/link-relations.xhtml)

**[返回顶部](#目录)**

## 网站图标

``` html
<!-- 针对 IE 10 及以下版本 -->
<!-- 如果将 `favicon.ico` 放在根目录下，则无需标签 -->

<!-- 对于 IE 11、Chrome、Firefox、Safari 和 Opera -->
<link rel="icon" type="image/png" sizes="16x16" href="/path/to/favicon-16x16.png">
<link rel="icon" type="image/png" sizes="32x32" href="/path/to/favicon-32x32.png">
<link rel="icon" type="image/png" sizes="96x96" href="/path/to/favicon-96x96.png">
<!-- 更多信息: https://bitsofco.de/all-about-favicons-and-touch-icons/ -->
```

- 📖 [所有关于网站图标（和触摸图标）的信息](https://bitsofco.de/all-about-favicons-and-touch-icons/)
- 📖 [网站图标对照表](https://github.com/audreyr/favicon-cheat-sheet)

**[返回顶部](#目录)**

## 社交

### Facebook Open Graph

``` html
<meta property="fb:app_id" content="123456789">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:type" content="website">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<meta property="article:author" content="">
```

- 📖 [Facebook 的 Open Graph 的标记](https://developers.facebook.com/docs/sharing/webmasters#markup)
- 📖 [Open Graph 协议](https://ogp.me/)
- 🛠 [页面验证 - Facebook Sharing Debugger](https://developers.facebook.com/tools/debug/)

### Twitter Card

``` html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
```

- 📖 [名片入门指南 - Twitter 开发者](https://dev.twitter.com/cards/getting-started)
- 🛠 [页面验证 - Twitter Card Validator](https://cards-dev.twitter.com/validator)
### Google+ / Schema.org

``` html
<link href="https://plus.google.com/+YourPage" rel="publisher">
<meta itemprop="name" content="内容标题">
<meta itemprop="description" content="内容描述少于 200 个字符">
<meta itemprop="image" content="https://example.com/image.jpg">
```

### Pinterest

根据他们的[帮助中心](https://help.pinterest.com/en/articles/prevent-people-saving-things-pinterest-your-site)可知，Pinterest 允许你禁止他人保存你网站里的内容。`description` 为可选。

``` html
<meta name="pinterest" content="nopin" description="Sorry, you can't save from my website!">
```

### Facebook Instant Articles

``` html
<meta charset="utf-8">
<meta property="op:markup_version" content="v1.0">

<!-- 你的文章的 Web 版网址 -->
<link rel="canonical" href="https://example.com/article.html">

<!-- 用于该文章的样式 -->
<meta property="fb:article_style" content="myarticlestyle">
```

- 📖 [创建文章 - Instant Articles](https://developers.facebook.com/docs/instant-articles/guides/articlecreate)
- 📖 [代码示例 - Instant Articles](https://developers.facebook.com/docs/instant-articles/reference)

### OEmbed

``` html
<link rel="alternate" type="application/json+oembed"
  href="https://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=json"
  title="oEmbed Profile: JSON">
<link rel="alternate" type="text/xml+oembed"
  href="https://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=xml"
  title="oEmbed Profile: XML">
```

- 📖 [oEmbed 格式](https://oembed.com/)

**[返回顶部](#目录)**

## 浏览器 / 平台

### Apple iOS

``` html
<!-- 智能应用 Banner -->
<meta name="apple-itunes-app" content="app-id=APP_ID,affiliate-data=AFFILIATE_ID,app-argument=SOME_TEXT">

<!-- 禁用自动检测和格式化可能的电话号码 -->
<meta name="format-detection" content="telephone=no">

<!-- 添加到主屏幕 -->
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black">
<meta name="apple-mobile-web-app-title" content="应用标题">

<!-- 触摸图标 -->
<!-- 在大多数情况下，在 `<head>` 中，一个 180×180px 触摸图标就已经足够了 -->
<link rel="apple-touch-icon" href="/path/to/apple-touch-icon.png">

<!-- 启动画面（已无效） -->
<link rel="apple-touch-startup-image" href="path/to/startup.png">

<!-- iOS 应用深层链接 -->
<meta name="apple-itunes-app" content="app-id=APP-ID, app-argument=http/url-sample.com">
<link rel="alternate" href="ios-app://APP-ID/http/url-sample.com">
```

- 📖 [Apple Meta 标签](https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)

### Apple Safari

```html
<!-- 固定网站 -->
<link rel="mask-icon" href="path/to/icon.svg" color="red">
```

### Google Android

``` html
<meta name="theme-color" content="#E64545">

<!-- 添加到主屏幕 -->
<meta name="mobile-web-app-capable" content="yes">
<!-- 更多信息：https://developer.chrome.com/multidevice/android/installtohomescreen -->
```

### Google Chrome

``` html
<link rel="chrome-webstore-item" href="https://chrome.google.com/webstore/detail/APP_ID">

<!-- 禁用翻译提示 -->
<meta name="google" content="notranslate">
```

### Google Chrome Mobile (只针对 Android)

从 Chrome 31 开始，你可以设置你的 Web 应用为“app mode”，如 Safari。

``` html
<!-- 链接到一个 manifest 并定义 manifest 的元数据 -->
<!-- manifest.json 中的例子也可以通过以下链接找到 -->
<link rel="manifest" href="manifest.json">

<!-- 定义你的网页为 Web 应用 -->
<meta name="mobile-web-app-capable" content="yes">

<!-- 主屏幕图标 -->
<link rel="icon" sizes="192x192" href="/path/to/highres-icon.png">
```

- 📖 [Google 开发者](https://developer.chrome.com/multidevice/android/installtohomescreen)

### Microsoft Internet Explorer

``` html
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="skype_toolbar" content="skype_toolbar_parser_compatible">

<!-- IE10: 禁用链接点击高亮 (https://blogs.windows.com/buildingapps/2012/11/15/adapting-your-webkit-optimized-site-for-internet-explorer-10/) -->
<meta name="msapplication-tap-highlight" content="no">

<!-- 固定网站 (https://msdn.microsoft.com/en-us/library/dn255024(v=vs.85).aspx) -->
<meta name="application-name" content="Sample Title">
<meta name="msapplication-tooltip" content="A description of what this site does.">
<meta name="msapplication-starturl" content="https://example.com/index.html?pinned=true">
<meta name="msapplication-navbutton-color" content="#FF3300">
<meta name="msapplication-window" content="width=800;height=600">
<meta name="msapplication-task" content="name=Task 1;action-uri=https://host/Page1.html;icon-uri=https://host/icon1.ico">
<meta name="msapplication-task" content="name=Task 2;action-uri=https://microsoft.com/Page2.html;icon-uri=https://host/icon2.ico">
<meta name="msapplication-badge" value="frequency=NUMBER_IN_MINUTES;polling-uri=https://example.com/path/to/file.xml">
<meta name="msapplication-TileColor" content="#FF3300">
<meta name="msapplication-TileImage" content="path/to/tileimage.jpg">

<meta name="msapplication-config" content="https://example.com/browserconfig.xml">
<meta name="msapplication-notification" content="frequency=60;polling-uri=https://example.com/livetile;polling-uri2=https://example.com/livetile2">
<meta name="msapplication-task-separator" content="1">
```

**[返回顶部](#目录)**

## 国内的浏览器

### 360 浏览器

``` html
<!-- 选择渲染引擎 -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

### QQ 移动浏览器

``` html
<!-- 在指定方向上锁定屏幕（锁定横/竖屏） -->
<meta name="x5-orientation" content="landscape/portrait">
<!-- 全屏显示此页面 -->
<meta name="x5-fullscreen" content="true">
<!-- 页面将以“应用模式”显示（全屏等）-->
<meta name="x5-page-mode" content="app">
```

### UC 移动浏览器

``` html
<!-- 在指定方向上锁定屏幕（锁定横/竖屏） -->
<meta name="screen-orientation" content="landscape/portrait">

<!-- 全屏显示此页面 -->
<meta name="full-screen" content="yes">

<!-- 即使在“文本模式”下，UC 浏览器也会显示图片 -->
<meta name="imagemode" content="force">

<!-- 页面将以“应用模式”显示（全屏、禁止手势等） -->
<meta name="browsermode" content="application">

<!-- 在此页面禁用 UC 浏览器的“夜间模式” -->
<meta name="nightmode" content="disable">

<!-- 简化页面，减少数据传输 -->
<meta name="layoutmode" content="fitscreen">

<!-- 禁用的 UC 浏览器的功能，“当此页面中有较多文本时缩放字体” -->
<meta name="wap-font-scale" content="no">
```

- 📖 [UC 浏览器文档](https://www.uc.cn/download/UCBrowser_U3_API.doc)

**[返回顶部](#目录)**

## 应用链接

``` html
<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="App Links">

<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="App Links">
<meta property="al:android:package" content="org.applinks">

<!-- 页面回退 -->
<meta property="al:web:url" content="https://applinks.org/documentation">
```

- 📖 [应用链接文档](https://applinks.org/documentation/)

**[返回顶部](#目录)**

## 注意

### 性能

当启用 GZIP 时，移动 `href` 属性到该元素的开头以提高压缩，因为 `href` 属性被用于 `a`、`base` 和 `link` 标签。

示例:

``` html
<link href="https://fonts.googleapis.com/css?family=Open+Sans:400,700" rel="stylesheet">
```

**[返回顶部](#目录)**

## 其他资源

- 📖 [HTML5 样板文档：HTML 标签](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/html.md)
- 📖 [HTML5 样板文档：扩展和定制](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/extend.md)

**[返回顶部](#目录)**

## 相关项目

- [Atom HTML Head 片段](https://github.com/joshbuchea/atom-html-head-snippets) - Atom `HEAD` 片段包
- [Sublime Text HTML Head 片段](https://github.com/marcobiedermann/sublime-head-snippets) - Sublime Text `HEAD` 片段包
- [head-it](https://github.com/hemanth/head-it) - `HEAD` 片段的 CLI 接口
- [vue-head](https://github.com/ktquez/vue-head) - 在 Vue.js 中操作 `HEAD` 标签的 meta 信息

**[返回顶部](#目录)**
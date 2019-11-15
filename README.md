# HEAD

> 这是一份关于文档`<head>`标签内可以用的元素的清单

[![CC0](https://img.shields.io/badge/license-CC0-green.svg?style=flat-square)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Contributors](https://img.shields.io/github/contributors/joshbuchea/head.svg?style=flat-square)](https://github.com/joshbuchea/HEAD/graphs/contributors)

## 目录

- [基础](#recommended-minimum)
- [元素](#elements)
- [meta标签](#meta)
- [链接](#link) 
- [图标](#icons) 
- [社交](#social) 
  - [Facebook Open Graph](#facebook-open-graph)
  - [Twitter Card](#twitter-card)
  - [Twitter Privacy](#twitter-privacy) 
  - [Schema.org](#schemaorg)
  - [Pinterest](#pinterest)
  - [Facebook Instant Articles](#facebook-instant-articles)
  - [OEmbed](#oembed)
- [浏览器 / 平台](#browsers--platforms)
  - [Apple iOS](#apple-ios)
  - [Google Android](#google-android)
  - [Google Chrome](#google-chrome)
  - [Microsoft Internet Explorer](#microsoft-internet-explorer)
- [浏览器(中国)](#browsers-chinese) 
  - [360 Browser](#360-browser)
  - [QQ Mobile Browser](#qq-mobile-browser)
  - [UC Mobile Browser](#uc-mobile-browser)
- [App 链接](#app-links) 
- [其他资源](#other-resources)
- [相关项目](#related-projects)
- [其他格式](#other-formats)
- [翻译](#translations)
- [贡献](#contributing) 
  - [贡献者](#contributors) 
- [作者](#author)
- [协议](#license)

## 基础

以下是构成任何web文档（网站/应用程序）的基本元素

```html
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<!--
  以上2个meta标签*必须*放在<head>标签的最顶部，以确保文档正确渲染。任何其他head内元素都应该放在这些标签之后。
 -->
<title>页面标题</title>
```

**[⬆ 回到顶部](#table-of-contents)**

## 元素

有效的`<head>`元素包括`meta`, `link`, `title`, `style`, `script`, `noscript`, and `base`。

这些元素为浏览器、搜索引擎、网络爬虫等技术提供了关于文档应当如何被感知和呈现的信息。

```html
<!--
  设置文档的字符编码，以便UTF-8范围内（如emoji）的所有字符能够正常显示。
-->
<meta charset="utf-8">

<!-- 设置文档标题 -->
<title>页面标题</title>

<!-- 设置文档中所有相对路径的基础路径 -->
<base href="https://example.com/page.html">

<!-- 链接外部css文件 -->
<link rel="stylesheet" href="styles.css">

<!-- 用于添加文档内的css -->
<style>
  /* ... */
</style>

<!-- JavaScript 和 No-JavaScript 标签 -->
<script src="script.js"></script>
<script>
  // 运行JavaScript
</script>
<noscript>
  <!-- 停用JavaScript时显示 -->
</noscript>
```

**[⬆ 返回顶部](#table-of-contents)**

## Meta标签

```html
<!--
  下面2个meta标签*必须*写在<head>标签的顶部，以确保文档正确渲染。任何<head>内元素都应当写在这些标签后面。
-->
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">

<!--
  允许控制从何处加载资源。尽可能放在<head>靠前的位置，因为该标签仅对它之后声明的资源生效。
-->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">

<!-- web应用的名字（仅在网站被当做app使用时生效） -->
<meta name="application-name" content="Application Name">

<!-- Chrome、Firefox OS和Opera的主题颜色 -->
<meta name="theme-color" content="#4285f4">

<!-- 文档简单描述（限制150个字符） -->
<!-- 这些内容*可能*回座位搜索引擎结果的一部分 -->
<meta name="description" content="A description of the page">

<!-- 控制搜索引擎的抓取和索引行为 -->
<meta name="robots" content="index,follow"><!-- 所有搜索引擎生效 -->
<meta name="googlebot" content="index,follow"><!-- 仅对Google有效 -->

<!-- 告诉Google不显示网站链接搜索框 -->
<meta name="google" content="nositelinkssearchbox">

<!-- 告诉Google不对此文档进行翻译 -->
<meta name="google" content="notranslate">

<!-- 验证网站所有权 -->
<meta name="google-site-verification" content="verification_token"><!-- Google Search Console -->
<meta name="yandex-verification" content="verification_token"><!-- Yandex Webmasters -->
<meta name="msvalidate.01" content="verification_token"><!-- Bing Webmaster Center -->
<meta name="alexaVerifyID" content="verification_token"><!-- Alexa Console -->
<meta name="p:domain_verify" content="code_from_pinterest"><!-- Pinterest Console-->
<meta name="norton-safeweb-site-verification" content="norton_code"><!-- Norton Safe Web -->

<!-- 确定用于构建文档的软件(如 WordPress,Dreamweaver) -->
<meta name="generator" content="program">

<!-- 文档主题的简单描述 -->
<meta name="subject" content="your document's subject">

<!-- 基于网站内容提供年龄分级 -->
<meta name="rating" content="General">

<!-- 允许控制referrer信息如何传递 -->
<meta name="referrer" content="no-referrer">

<!-- 禁止自动检测和格式化可能存在的电话号码 -->
<meta name="format-detection" content="telephone=no">

<!-- 通过设置“off”完全退出DNS预处理 -->
<meta http-equiv="x-dns-prefetch-control" content="off">

<!-- 指定要显示在一个特定frame中的文档 -->
<meta http-equiv="Window-Target" content="_value">

<!-- 和地理相关的标签 -->
<meta name="ICBM" content="latitude, longitude">
<meta name="geo.position" content="latitude;longitude">
<meta name="geo.region" content="country[-state]"><!-- 国家代码 (ISO 3166-1): 必填, 州代码 (ISO 3166-2): 可选; 例如. content="US" / content="US-NY" -->
<meta name="geo.placename" content="city/town"><!-- 例如 content="New York City" -->
```

- 📖 [Google可以识别的Meta标签](https://support.google.com/webmasters/answer/79812?hl=en)
- 📖 [WHATWG Wiki: Meta扩展](https://wiki.whatwg.org/wiki/MetaExtensions)
- 📖 [ICBM - 维基百科](https://en.wikipedia.org/wiki/ICBM_address#Modern_use)
- 📖 [地理标记 - 维基百科](https://en.wikipedia.org/wiki/Geotagging#HTML_pages)

**[⬆ 回到顶部](#table-of-contents)**

## 链接

```html
<!-- 指向一个外部CSS样式表 -->
<link rel="stylesheet" href="https://example.com/styles.css">

<!-- 有助于避免网站内容重复的问题 -->
<link rel="canonical" href="https://example.com/article/?page=2">

<!-- 链接到当前文档的一个AMP HTML版本 -->
<link rel="amphtml" href="https://example.com/path/to/amp-version.html">

<!-- 指向指定Web应用程序的"安装"凭据的JSON文件。 -->
<link rel="manifest" href="manifest.json">

<!-- 指向关于文档作者的信息 -->
<link rel="author" href="humans.txt">

<!-- 指向适用于链接上下文的版权声明 -->
<link rel="license" href="copyright.html">

<!-- 提供你的文档可能存在的另一个语言版本的链接 -->
<link rel="alternate" href="https://es.example.com/" hreflang="es">

<!-- 提供关于作者或其他人的信息 -->
<link rel="me" href="https://google.com/profiles/thenextweb" type="text/html">
<link rel="me" href="mailto:name@example.com">
<link rel="me" href="sms:+15035550125">

<!-- 连接到一个描述记录、文档、或其他有历史意义的材料集合的文档 -->
<link rel="archives" href="https://example.com/archives/">

<!-- 连接到分层结构的顶级资源 -->
<link rel="index" href="https://example.com/article/">

<!-- 提供自我引用 —— 当文档可能有多个引用时非常有用 -->
<link rel="self" type="application/atom+xml" href="https://example.com/atom.xml">

<!-- 一系列文档中第一个、最后一个、上一个、下一个文档-->
<link rel="first" href="https://example.com/article/">
<link rel="last" href="https://example.com/article/?page=42">
<link rel="prev" href="https://example.com/article/?page=1">
<link rel="next" href="https://example.com/article/?page=3">

<!-- 当使用第三方服务来维护博客时使用 -->
<link rel="EditURI" href="https://example.com/xmlrpc.php?rsd" type="application/rsd+xml" title="RSD">

<!-- 当另一个WordPress博客连接到你的WordPress博客或文章时自动化一个评论 -->
<link rel="pingback" href="https://example.com/xmlrpc.php">

<!-- 当你在你的文档中连接到一个URL时候通知它 -->
<link rel="webmention" href="https://example.com/webmention">

<!-- 使用Micropub客户端发布你的域名 -->
<link rel="micropub" href="https://example.com/micropub">

<!-- 打开搜索 -->
<link rel="search" href="/open-search.xml" type="application/opensearchdescription+xml" title="Search Title">

<!-- Feeds -->
<link rel="alternate" href="https://feeds.feedburner.com/example" type="application/rss+xml" title="RSS">
<link rel="alternate" href="https://example.com/feed.atom" type="application/atom+xml" title="Atom 0.3">

<!-- 预取, 预加载, 预浏览 -->
<!-- 更多信息: https://css-tricks.com/prefetching-preloading-prebrowsing/ -->
<link rel="dns-prefetch" href="//example.com/">
<link rel="preconnect" href="https://www.example.com/">
<link rel="prefetch" href="https://www.example.com/">
<link rel="prerender" href="https://example.com/">
<link rel="preload" href="image.png" as="image">
```

- 📖 [链接关系](https://www.iana.org/assignments/link-relations/link-relations.xhtml)

**[⬆ 回到顶部](#table-of-contents)**

## 图标

```html
<!-- 针对IE10及其以下版本 -->
<!-- 将favicon.ico放在根目录下 - 不需要标签 -->

<!-- 我们需要的图标的最高分辨率 -->
<link rel="icon" sizes="192x192" href="/path/to/icon.png">

<!-- 苹果触摸图标（尺寸192px） -->
<link rel="apple-touch-icon" href="/path/to/apple-touch-icon.png">

<!-- Safari选项卡图标 -->
<link rel="mask-icon" href="/path/to/icon.svg" color="blue">
```

- 📖 [所有关于Favicons (和触摸图标)的信息](https://bitsofco.de/all-about-favicons-and-touch-icons/)
- 📖 [创建选项卡图标](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/pinnedTabs/pinnedTabs.html)
- 📖 [Favicon对照表](https://github.com/audreyr/favicon-cheat-sheet)
- 📖 [图标 & 浏览器颜色](https://developers.google.com/web/fundamentals/design-and-ux/browser-customization/)

**[⬆ 回到顶部](#table-of-contents)**

## 社交

### Facebook Open Graph

```html
<meta property="fb:app_id" content="123456789">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:type" content="website">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:image:alt" content="A description of what is in the image (not a caption)">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<meta property="article:author" content="">
```

- 📖 [Facebook 的 Open Graph 标记](https://developers.facebook.com/docs/sharing/webmasters#markup)
- 📖 [Open Graph 协议](http://ogp.me/)
- 🛠 页面验证 [Facebook Sharing Debugger](https://developers.facebook.com/tools/debug/)

### Twitter Card

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
<meta name="twitter:image:alt" content="A text description of the image conveying the essential nature of an image to users who are visually impaired. Maximum 420 characters.">
```

- 📖 [名片使用指南 — Twitter 开发者](https://dev.twitter.com/cards/getting-started)
- 🛠 页面验证 [Twitter Card Validator](https://cards-dev.twitter.com/validator)

### Twitter Privacy
如果您在网站中嵌入了Twitter，Twitter就可以使用网站的信息来为Twitter用户定制内容和建议。[更多Twitter隐私相关条款](https://dev.twitter.com/web/overview/privacy#what-privacy-options-do-website-publishers-have).
```html
<!-- 禁止Twitter使用你的网站信息来实现个性化 -->
<meta name="twitter:dnt" content="on">
```

### Schema.org

```html
<html lang="" itemscope itemtype="https://schema.org/Article">
    <head>
      <link rel="author" href="">
      <link rel="publisher" href="">
      <meta itemprop="name" content="Content Title">
      <meta itemprop="description" content="Content description less than 200 characters">
      <meta itemprop="image" content="https://example.com/image.jpg">
```

**注意:** 这些Meta标签需要在`<html>`标签中添加 `itemscope` 和 `itemtype` 属性。

- 🛠 验证页面 [结构化数据测试工具](https://developers.google.com/structured-data/testing-tool/)

### Pinterest

根据 [帮助中心](https://help.pinterest.com/en/business/article/prevent-saves-to-pinterest-from-your-site)，Pinterest允许你禁止他人保存你网站上的内容， `description`可选。

```html
<meta name="pinterest" content="nopin" description="Sorry, you can't save from my website!">
```

### Facebook Instant Articles

```html
<meta charset="utf-8">
<meta property="op:markup_version" content="v1.0">

<!-- 你文章的web版路径 -->
<link rel="canonical" href="https://example.com/article.html">

<!-- 该文章的样式 -->
<meta property="fb:article_style" content="myarticlestyle">
```

- 📖 [创建文章 - Instant Articles](https://developers.facebook.com/docs/instant-articles/guides/articlecreate)
- 📖 [代码示例 - Instant Articles](https://developers.facebook.com/docs/instant-articles/reference)

### OEmbed

```html
<link rel="alternate" type="application/json+oembed"
  href="https://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=json"
  title="oEmbed Profile: JSON">
<link rel="alternate" type="text/xml+oembed"
  href="https://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=xml"
  title="oEmbed Profile: XML">
```

- 📖 [oEmbed 格式](https://oembed.com/)

**[⬆ 返回顶部](#table-of-contents)**

## 浏览器 / 平台

### Apple iOS

```html
<!-- Smart App Banner -->
<meta name="apple-itunes-app" content="app-id=APP_ID,affiliate-data=AFFILIATE_ID,app-argument=SOME_TEXT">

<!-- 禁止自动检测和格式化可能存在的电话号码 -->
<meta name="format-detection" content="telephone=no">

<!-- 启动图标 （180x180px 后更大） -->
<link rel="apple-touch-icon" href="/path/to/apple-touch-icon.png">

<!-- 屏幕启动图片 -->
<link rel="apple-touch-startup-image" href="/path/to/launch.png">

<!-- 启动图标的标题 -->
<meta name="apple-mobile-web-app-title" content="App Title">

<!-- 启用独立 （全屏） 模式 -->
<meta name="apple-mobile-web-app-capable" content="yes">

<!-- 状态栏外观（除非启用全屏模式，否则无效） -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">

<!-- iOS app deep linking -->
<meta name="apple-itunes-app" content="app-id=APP-ID, app-argument=http/url-sample.com">
<link rel="alternate" href="ios-app://APP-ID/http/url-sample.com">
```

- 📖 [配置Web应用](https://developer.apple.com/library/content/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

### Google Android

```html
<meta name="theme-color" content="#E64545">

<!-- 添加到主屏幕 -->
<meta name="mobile-web-app-capable" content="yes">
<!-- More info: https://developer.chrome.com/multidevice/android/installtohomescreen -->

<!-- Android app deep linking -->
<meta name="google-play-app" content="app-id=package-name">
<link rel="alternate" href="android-app://package-name/http/url-sample.com">
```

### Google Chrome

```html
<link rel="chrome-webstore-item" href="https://chrome.google.com/webstore/detail/APP_ID">

<!-- 禁止翻译提示 -->
<meta name="google" content="notranslate">
```

### Microsoft Internet Explorer

```html
<!-- 强制IE 8/9/10 使用其最新的渲染引擎 -->
<meta http-equiv="x-ua-compatible" content="ie=edge">

<!-- 禁止通过Skype浏览器扩展自动检测和格式化可能存在的手机号码 -->
<meta name="skype_toolbar" content="skype_toolbar_parser_compatible">

<!-- Windows 磁贴 -->
<meta name="msapplication-config" content="/browserconfig.xml">
```

最低限度的`browserconfig.xml`配置

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

- 📖 [浏览器配置架构参考 ](https://msdn.microsoft.com/en-us/library/dn320426.aspx)

**[⬆ 返回顶部](#table-of-contents)**

## 浏览器 (中国)

### 360浏览器

```html
<!-- 选择渲染引擎的使用顺序  -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

### QQ 移动浏览器

```html
<!-- Locks the screen into the specified orientation -->
<!-- 锁定屏幕方向（横屏或竖屏） -->
<meta name="x5-orientation" content="landscape/portrait">

<!-- 文档全屏显示-->
<meta name="x5-fullscreen" content="true">

<!-- 文档使用“应用模式”显示（全屏，等） -->
<meta name="x5-page-mode" content="app">
```

### UC 移动浏览器

```html
<!-- 锁定屏幕方向（横屏或竖屏） -->
<meta name="screen-orientation" content="landscape/portrait">

<!-- 文档全屏显示-->
<meta name="full-screen" content="yes">

<!-- 即使在“文本模式”下，UC浏览器也会显示图片 -->
<meta name="imagemode" content="force">

<!-- 文档使用“应用模式”显示（全屏、禁止手势，等） -->
<meta name="browsermode" content="application">

<!-- 在该文档禁用U浏览器的"夜间模式" -->
<meta name="nightmode" content="disable">

<!-- 简化文档来减少数据传输 -->
<meta name="layoutmode" content="fitscreen">

<!-- 禁用UC浏览器的“当文档中有较多文字时缩放字体”功能 -->
<meta name="wap-font-scale" content="no">
```

- 📖 [UC 浏览器文档](https://www.uc.cn/download/UCBrowser_U3_API.doc)

**[⬆ 回到顶部](#table-of-contents)**

## App 链接

```html
<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="App Links">

<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="App Links">
<meta property="al:android:package" content="org.applinks">

<!-- Web 回退 -->
<meta property="al:web:url" content="https://applinks.org/documentation">
```

- 📖 [App 链接](https://applinks.org/documentation/)

**[⬆ 回到顶部](#table-of-contents)**

## 其他资源

- 📖 [HTML5 Boilerplate 文档: The HTML](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/html.md)
- 📖 [HTML5 Boilerplate 文档: 扩展和定制](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/extend.md)

**[⬆ 回到顶部](#table-of-contents)**

## 相关项目

- [Atom HTML Head Snippets](https://github.com/joshbuchea/atom-html-head-snippets) - Atom`HEAD`代码片段包
- [Sublime Text HTML Head Snippets](https://github.com/marcobiedermann/sublime-head-snippets) - Sublime`HEAD`代码片段包
- [head-it](https://github.com/hemanth/head-it) - `HEAD`代码片段的CLI接口
- [vue-head](https://github.com/ktquez/vue-head) - 在Vue.js中操作`HEAD`标签的meta信息

**[⬆ 回到顶部](#table-of-contents)**

## 其他格式

- 📄 [PDF](https://gitprint.com/joshbuchea/HEAD/blob/master/README.md)

**[⬆ 回到顶部](#table-of-contents)**

## 翻译

- 🇧🇷 [Brazilian Portuguese](https://github.com/Webschool-io/HEAD)
- 🇨🇳 [Chinese (Simplified)](https://github.com/Amery2010/HEAD)
- 🇩🇪 [German](https://github.com/Shidigital/HEAD)
- 🇮🇹 [Italian](https://github.com/Fakkio/HEAD)
- 🇯🇵 [Japanese](https://coliss.com/articles/build-websites/operation/work/collection-of-html-head-elements.html)
- 🇰🇷 [Korean](https://github.com/Lutece/HEAD)
- 🇷🇺 [Russian/Русский](https://github.com/Konfuze/HEAD)
- 🇪🇸 [Spanish](https://github.com/alvaroadlf/HEAD)
- 🇹🇷 [Turkish/Türkçe](https://github.com/mkg0/HEAD)

**[⬆ back to top](#table-of-contents)**

## 贡献

**开启一个issue或通过pull request来提出修改和补充**

### 指南

**HEAD** 仓库包含两个分支

#### 1. `master`

该分支包含`README.md`文件，该文件的修改会自动同步到[htmlhead.dev](https://htmlhead.dev/)网站。应当直接在该文件上进行内容修改。

请按照以下步骤进行pull request

- 只修改一个标签，或者一次修改一组相关标签
- 对属性使用双引号
- 不要在自闭合标签内使用斜杠 —— HTML5规范说他们是可选的
- 考虑添加一些文档链接以支持你所提到的变化

#### 2. `gh-pages`

该分支负责[htmlhead.dev](https://htmlhead.dev/)网站。我们使用[Jekyll](https://jekyllrb.com/)通过[GitHub Pages](https://pages.github.com/)服务部署了`README.md`文件。所有与网站相关的修改都必须指向此处。
 
你可能需要通过[Jekyll 文档](https://jekyllrb.com/docs/home/)来了解Jekyll，以便在该分支上工作。

### 贡献者

看看所有超棒的[贡献者们](https://github.com/joshbuchea/HEAD/graphs/contributors).

## 作者

**[Josh](https://twitter.com/joshbuchea)**

## 协议

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

**[⬆ 回到顶部](#table-of-contents)**

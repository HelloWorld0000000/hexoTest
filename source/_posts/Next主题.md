---
title: Next主题美化		#标题
categories: Next主题	#分类
tags: 主题美化			#标签
top: false				#置顶
---

## Git下载主题地址

> ```
> git clone https://github.com/theme-next/hexo-theme-next themes/next
> ```



## 提示

> 1. **站点配置文件**指的是博客文件根目录下的 `_config.yml`
> 2. **主题配置文件**是主题文件夹next 下的 `_config.yml`	



## 启动 主题

> **站点配置文件**：找到 theme 字段, 并将其值更改为 next
>
> ```
> theme: next
> ```
>
> **Git输入**
>
> ```
> hexo g  //刷新
> hexo s  //启动
> ```



## 更换 主题外观

> **主题配置文件**：找到 `schemes` 字段，使用去掉 #，不使用加上 #。有4个外观
>
> <img src="Next%E4%B8%BB%E9%A2%98/01.jpg" alt="01" style="zoom:80%;" />  
>
> 在次执行,可预览效果
>
> ```
> hexo clean
> heox s
> ```



## 设置 语言

> **站点配置文件**：找到`language`字段 设置成你所需要的语言
>
> ```
> 例如：language: zh-CN
> ```
>
> 目前 NexT 支持的语言如以下表格所示：
>
> <img src="Next%E4%B8%BB%E9%A2%98/02.jpg" alt="02" style="zoom:80%;" /> 



##  设置 菜单

> **主题配置文件**：
>
> 1. 设定菜单内容，对应的字段是`menu`。使用使用哪个，将 # 去掉
>
>    NexT 默认的菜单项有（标注 ！的项表示需要手动创建这个页面）
>
>    <img src="Next%E4%B8%BB%E9%A2%98/03.jpg" alt="03" style="zoom:80%;" /> 
>
>    注：若你的站点运行在子目录中，请将链接前缀的`/`去掉
>
> 
>
> 2. 设置菜单项的显示文本 或 若需要添加一个菜单项
>
>    打开：主题目录下 --> languages目录下 --> zh-CN.yml文本，对应的字段是`menu` 
>
>    若有添加菜单项，还需打开**主题配置文件**在字段是`menu`进行手动添加
>
>    <img src="Next%E4%B8%BB%E9%A2%98/04.jpg" alt="04" style="zoom:80%;" /> 
>
>    <img src="Next%E4%B8%BB%E9%A2%98/05.jpg" alt="05" style="zoom:80%;" /> 

### 设置 图标和数字

> **主题配置文件**：搜索关键字`menu_settings`
>
> <img src="Next%E4%B8%BB%E9%A2%98/13.png" alt="13" style="zoom:80%;" /> 

### 标签

> Git输入。将会新建：tags文件夹 --> index.md文件
>
> ```
> hexo new page tags
> ```
>
> 修改index.md文件：
>
> ```
> title: 标签
> date: 2022-04-20 10:59:41
> type: "tags"
> layout: "tags"
> ```

### 标签 颜色和边框

> 打开：next --> layout --> **page.swig** 以文本打开
>
> 找到对应字段：`{% if page.type === "tags" %}`，将其下面的代码1 替换为 代码2
>
> ```javascript
> <!--原本代码1：-->
> 
> 		<div class="tag-cloud">
>             <div class="tag-cloud-title">
>               {{ _p('counter.tag_cloud', site.tags.length) }}
>             </div>
>             <div class="tag-cloud-tags">
>               {{ tagcloud({
>                 min_font   : theme.tagcloud.min,
>                 max_font   : theme.tagcloud.max,
>                 amount     : theme.tagcloud.amount,
>                 color      : true,
>                 start_color: theme.tagcloud.start,
>                 end_color  : theme.tagcloud.end})
>               }}
>             </div>
>           </div>
> ```
>
> ```javascript
> <!--替换为代码2：-->
> 
> <div class="tag-cloud">
> 
>   <!-- <div class="tag-cloud-title">
> 
>       {{ _p('counter.tag_cloud', site.tags.length) }}
> 
>   </div> -->
> 
>   <div class="tag-cloud-tags" id="tags">
> 
>     {{ tagcloud({min_font: 16, max_font: 16, amount: 300, color: true, start_color: '#fff', end_color: '#fff'}) }}
> 
>   </div>
> 
> </div>
> 
> <br>
> 
> <script type="text/javascript">
> 
>    var alltags=document.getElementById('tags');
> 
>    var tags=alltags.getElementsByTagName('a');
> 
>    for (var i = tags.length - 1; i >= 0; i--) {
> 
>      var r=Math.floor(Math.random()*75+130);
> 
>      var g=Math.floor(Math.random()*75+100);
> 
>      var b=Math.floor(Math.random()*75+80);
> 
>      tags[i].style.background = "rgb("+r+","+g+","+b+")";
> 
>    }
> 
> </script>
> 
> <style type="text/css">
> 
>     div#posts.posts-expand .tag-cloud a{
> 
>    background-color: #f5f7f1;
> 
>    border-radius: 6px;
> 
>    padding-left: 10px;
> 
>    padding-right: 10px;
> 
>    margin-top: 18px;
> 
>  }
> 
>  .tag-cloud a{
> 
>    background-color: #f5f7f1;
> 
>    border-radius: 4px;
> 
>    padding-right: 5px;
> 
>    padding-left: 5px;
> 
>    margin-right: 5px;
> 
>    margin-left: 0px;
> 
>    margin-top: 8px;
> 
>    margin-bottom: 0px;
> 
>  }
> 
>  .tag-cloud a:before{
> 
>       content: "?";
> 
>  }
> 
>  .tag-cloud-tags{
> 
>    text-align: left;
> 
>    counter-reset: tags;
> 
>  }
> 
> </style>
> ```

### 分类

> Git输入。将会新建：categories文件夹 --> index.md文件
>
> ```
> hexo new page categories
> ```
>
> 修改index.md文件：
>
> ```
> title: 分类
> date: 2022-04-20 11:07:06
> type: "categories"
> layout: "categories"
> ```

### 关于

> Git输入。将会新建：about文件夹 --> index.md文件
>
> ```
> hexo new page about 
> ```
>
> 修改index.md文件：
>
> ```
> title: 关于
> date: 2022-04-20 10:59:41
> type: "about"
> layout: "about"
> ```

### 留言板

> Git输入。将会新建：contact文件夹 --> index.md文件
>
> ```
> hexo new page contact 
> ```
>
> 修改index.md文件：
>
> ```
> title: 留言板
> date: 2022-04-20 10:59:41
> type: "contact"
> layout: "contact"
> ```

### 日程表

> 内容显示在中间，目录显示在侧边栏
>
> Git输入。将会新建：contact文件夹 --> index.md文件
>
> ```
> hexo new page schedule
> ```
>
> 修改index.md文件：
>
> ```
> title: 日程表
> date: 2022-04-20 10:59:41
> layout: "schedule"
> ```



## 设置 头像

> **主题配置文件**：修改字段`avatar`值设置成头像的链接地址
>
> > 头像的链接地址：
> >
> > 1. 完整的互联网URI(图片地址)： （例：http://example.com/avatar.png）
> > 2. 站点内的地址：主题文件夹next --> source文件夹 --> images文件夹 --> `avatar.gif`图片(必须以这个命名)
>
> <img src="Next%E4%B8%BB%E9%A2%98/14.png" alt="14" style="zoom:80%;" /> 

 

## 设置 标题和作者以及链接

> **站点配置文件**：修改内容
>
> ```
> # Site
> title: 网站标题
> subtitle: 副标题
> description: 个人签名
> author: 姓名
> language: 语言
> timezone: 设置时区
> ```



## 设置 侧边栏

### 位置

> **主题配置文件**：修改字段`sidebar`
>
> <img src="Next%E4%B8%BB%E9%A2%98/20.jpg" alt="20" style="zoom:80%;" /> 

### 显示的时机

> **主题配置文件**：修改字段`display `，有4种类型：
>
> ```
> post - 默认行为，在文章页面（拥有目录列表）时显示
> always - 在所有页面中都显示
> hide - 在所有页面中都隐藏（可以手动展开）
> remove - 完全移除
> ```

### 社交链接

> **主题配置文件**：修改字段`social` 
>
> <img src="Next%E4%B8%BB%E9%A2%98/06.jpg" alt="06" style="zoom:80%;" /> 

### 友情链接

> **主题配置文件**：修改字段`links`，可进行添加



## 设置 打赏功能

> 该功能显示在 每篇文章的下方
>
> **主题配置文件**：修改字段`reward`
>
> **添加图片位置**：主题文件夹next --> source文件夹 --> images文件夹 --> 自定义添加图片，命名 参考配置文件设置的
>
> <img src="Next%E4%B8%BB%E9%A2%98/07.jpg" alt="07" style="zoom:80%;" /> 



## 添加 代码-复制按钮

> **主题配置文件**：搜索关键字` copy_button`
>
> <img src="Next%E4%B8%BB%E9%A2%98/08.png" alt="08" style="zoom:80%;" /> 



## 设置 代码-边框

> **主题配置文件**：搜索关键字`codeblock`
>
> <img src="Next%E4%B8%BB%E9%A2%98/22.png" alt="22" style="zoom:80%;" />



## 添加 一键回到顶部

> **主题配置文件**：搜索关键字`back2top`
>
> <img src="Next%E4%B8%BB%E9%A2%98/9.png" alt="9" style="zoom: 80%;" /> 



## 添加 顶部读取进度条

>  **主题配置文件**：搜索关键字`reading_progress`
>
> <img src="Next%E4%B8%BB%E9%A2%98/10.png" alt="10" style="zoom:80%;" /> 



## 添加 书签

> **主题配置文件**：搜索关键字`bookmark`
>
> 作用：关闭页面或点击书签图标时保存读取进度
>
> <img src="Next%E4%B8%BB%E9%A2%98/11.png" alt="11" style="zoom:80%;" /> 



## 设置 加载博客的速度/动画

> **主题配置文件**：搜索关键字`motion`
>
> <img src="Next%E4%B8%BB%E9%A2%98/12.jpg" alt="12" style="zoom:80%;" />  



## 设置 文章底部-标签图标

> **主题配置文件**：搜索关键字`tag_icon`
>
> <img src="Next%E4%B8%BB%E9%A2%98/15.png" alt="15" style="zoom: 80%;" /> 



## 添加 关注我的其他途径

> **主题配置文件**：搜索关键字`follow_me`
>
> 显示在：每篇文章的底部
>
> <img src="Next%E4%B8%BB%E9%A2%98/16.jpg" alt="16" style="zoom:80%;" /> 



## 添加 首页-阅读全文

> 1. 主目录下-Git下载：
>
>    ```
>    npm install hexo-excerpt --save
>    ```
>
> 2. **站点配置文件**：可在底部 **添加以下代码**
>
>    ```
>    excerpt:			# 一定要顶格写，注意格式
>      depth: 5			# 他的大小就是全文阅读预览长度设置
>      excerpt_excludes: []
>      more_excludes: []
>      hideWholePostExcerpts: true  
>    ```
>
> 3. **主题配置文件**：搜索关键字`excerpt_description`，将值修改为 true 



## 添加 动态背景

> 1. **打开**：next --> layout --> **_layout.swig** 以文本打开
>
>     **添加代码**：在 `< /body>`之前添加代码
>
>    ```javascript
>    {% if theme.canvas_nest %}
>    <script type="text/javascript"
>    color="0,0,255" opacity='0.7' zIndex="-2" count="99" src="//cdn.bootcss.com/canvas-nest.js/1.0.0/canvas-nest.min.js"></script>
>    {% endif %}
>    ```
>
>    <img src="Next%E4%B8%BB%E9%A2%98/18.jpg" alt="18" style="zoom:80%;" />
>
>     
>
> 2. **主题配置文件**
>
>    ```
>    # --------------------------------------------------------------
>    # background settings
>    # --------------------------------------------------------------
>    # add canvas-nest effect
>    # see detail from https://github.com/hustcc/canvas-nest.js
>    canvas_nest: true
>    ```
>
>    <img src="Next%E4%B8%BB%E9%A2%98/19.jpg" alt="19" style="zoom:80%;" /> 



## 添加 底部显示统计字数

> 1. 主目录下-Git下载：
>
>    ```
>    npm install hexo-wordcount --save
>    ```
>
> 2. 打开：next --> layout --> _partials --> **footer.swig** 以文本打开
>
>    底部添加代码：
>
>    ```javascript
>    <div class="theme-info">
>      <div class="powered-by"></div>
>      <span class="post-count">博客全站共{{ totalcount(site) }}字</span>
>    </div>
>    ```



## 添加 文章置顶+置顶标签

> 1.  主目录下-Git下载：
>
>    ```
>    $ npm uninstall hexo-generator-index --save
>    
>    $ npm install hexo-generator-index-pin-top --save
>    ```
>
> 2. 在需要置顶的文章内，顶部加上 `top: true`【如下图】
>
>    <img src="Next%E4%B8%BB%E9%A2%98/21.jpg" alt="21" style="zoom:80%;" /> 
>
> 3. 打开：next --> layout --> _macro --> **post.swig** 以文本打开
>
>    对应的字段：`<div class="post-meta">`
>
>    在字段下，添加代码：
>
>    ```javascript
>    {% if post.top %}
>    	<i class="fa fa-thumb-tack"></i>
>    	<font color=7D26CD>置顶</font>
>    	<span class="post-meta-divider">|</span>
>    {% endif %} 
>    ```



## 添加 点击爱心效果

> 1. 打开：next --> source --> js --> 创建新文件夹**src** --> 创建 **clicklove.js**文本
>
>    **clicklove.js**文本内，加入代码：
>
>    ```
>    !function(e,t,a){function n(){c(".heart{width: 10px;height: 10px;position: fixed;background: #f00;transform: rotate(45deg);-webkit-transform: rotate(45deg);-moz-transform: rotate(45deg);}.heart:after,.heart:before{content: '';width: inherit;height: inherit;background: inherit;border-radius: 50%;-webkit-border-radius: 50%;-moz-border-radius: 50%;position: fixed;}.heart:after{top: -5px;}.heart:before{left: -5px;}"),o(),r()}function r(){for(var e=0;e<d.length;e++)d[e].alpha<=0?(t.body.removeChild(d[e].el),d.splice(e,1)):(d[e].y--,d[e].scale+=.004,d[e].alpha-=.013,d[e].el.style.cssText="left:"+d[e].x+"px;top:"+d[e].y+"px;opacity:"+d[e].alpha+";transform:scale("+d[e].scale+","+d[e].scale+") rotate(45deg);background:"+d[e].color+";z-index:99999");requestAnimationFrame(r)}function o(){var t="function"==typeof e.onclick&&e.onclick;e.onclick=function(e){t&&t(),i(e)}}function i(e){var a=t.createElement("div");a.className="heart",d.push({el:a,x:e.clientX-5,y:e.clientY-5,scale:1,alpha:1,color:s()}),t.body.appendChild(a)}function c(e){var a=t.createElement("style");a.type="text/css";try{a.appendChild(t.createTextNode(e))}catch(t){a.styleSheet.cssText=e}t.getElementsByTagName("head")[0].appendChild(a)}function s(){return"rgb("+~~(255*Math.random())+","+~~(255*Math.random())+","+~~(255*Math.random())+")"}var d=[];e.requestAnimationFrame=function(){return e.requestAnimationFrame||e.webkitRequestAnimationFrame||e.mozRequestAnimationFrame||e.oRequestAnimationFrame||e.msRequestAnimationFrame||function(e){setTimeout(e,1e3/60)}}(),n()}(window,document);
>    ```
>
> 2. 打开：next --> layout --> _partials --> **footer.swig**以文本打开
>
>    可在底部 **添加以下代码**：
>
>    ```javascript
>    <script type="text/javascript" src="/js/src/clicklove.js"></script>
>    ```



## 添加 网站运行时间的设置

> 打开：next --> layout --> _partials --> **footer.swig**以文本打开
>
> 可在底部 **添加以下代码**
>
> ```javascript
> 			<!-- 网站运行时间的设置 -->
> 
> <span id="timeDate">载入天数...</span>
> <span id="times">载入时分秒...</span>
> <script>
>     var now = new Date();
>     function createtime() {
>         var grt= new Date("04/26/2022 23:26:00");  //此处修改你的建站时间或者网站上线时间
>         now.setTime(now.getTime()+250);
>         days = (now - grt ) / 1000 / 60 / 60 / 24; dnum = Math.floor(days);
>         hours = (now - grt ) / 1000 / 60 / 60 - (24 * dnum); hnum = Math.floor(hours);
>         if(String(hnum).length ==1 ){hnum = "0" + hnum;} minutes = (now - grt ) / 1000 /60 - (24 * 60 * dnum) - (60 * hnum);
>         mnum = Math.floor(minutes); if(String(mnum).length ==1 ){mnum = "0" + mnum;}
>         seconds = (now - grt ) / 1000 - (24 * 60 * 60 * dnum) - (60 * 60 * hnum) - (60 * mnum);
>         snum = Math.round(seconds); if(String(snum).length ==1 ){snum = "0" + snum;}
>         document.getElementById("timeDate").innerHTML = "本站已安全运行 "+dnum+" 天 ";
>         document.getElementById("times").innerHTML = hnum + " 小时 " + mnum + " 分 " + snum + " 秒";
>     }
> setInterval("createtime()",250);
> </script>
> ```



## 设置 底部-动态图标

> **主题配置文件**：搜索关键字`底部设置`
>
> <img src="Next%E4%B8%BB%E9%A2%98/23.png" alt="23" style="zoom:80%;" /> 



## 添加 搜索功能(仅限个人博客内容)

> 1. 主目录下-Git下载：安装站内搜索插件
>
>    ```
>    $  npm install hexo-generator-searchdb --save
>    或者---------------------------------------------
>    $ cnpm install hexo-generator-searchdb --save
>    ```
>
> 2. **站点配置文件**：可在底部 **添加以下代码**
>
>    ```
>    #表示站内搜索
>    search:
>        path: search.xml
>        field: post
>        format: html
>        limit: 10000
>    ```
>
> 3. **主题配置文件**：搜索关键字`local_search`
>
>    <img src="Next%E4%B8%BB%E9%A2%98/24.png" alt="24" style="zoom:80%;" /> 



## 添加 网页-音乐播放器

> 1. 下载：[GitHub Aplayer](https://blog.51cto.com/u_12877374/2853807)  
>
>    下载到本地进行解压 或 `git pull拉取下来`。后将 `dist`文件夹 复制到 next -> source文件夹下
>
> 2. 打开：next --> source --> dist -- > **music.js**新建文本
>
>    **music.js**添加内容
>
>    ```javascript
>    const ap = new APlayer({
>        container: document.getElementById('aplayer'),
>        fixed: true,
>        autoplay: false,
>        listFolded: true,
>        listMaxHeight: 90,
>    			<!--在顶部添加，别在底部；name歌名，artist歌手，url地址，cover封面-->
>        audio: [		
>         
>         {
>            name: '好久不见',
>            artist: '陈奕迅',
>            url: 'http://music.163.com/song/media/outer/url?id=65538.mp3',
>            cover: 'http://p1.music.126.net/o_OjL_NZNoeog9fIjBXAyw==/18782957139233959.jpg?param=130y130',
>          },
>        ]
>    });
>    ```
>
>    - 歌曲的url：将id=  换掉即可，id从[网易云](https://music.163.com/)某首歌的url获取
>
>      ```
>      http://music.163.com/song/media/outer/url?id=1299550532.mp3
>      ```
>
>    - 封面的url：[网易云](https://music.163.com/) --> 歌曲播放 --> 在封面位置，右击 --> 复制图片地址
>
>      
>
> 3. 对应的参数，[Aplayer 中文文档](https://aplayer.js.org/#/zh-Hans/?id=%E5%8F%82%E6%95%B0)
>
>    <img src="Next%E4%B8%BB%E9%A2%98/25.png" alt="25" style="zoom:80%;" /> 
>
>    
>
> 4. 打开：next --> layout --> **_layout.swig**以文本打开
>
>    在`<body></body>`里的底部 添加以下代码
>
>    ```javascript
>    <link rel="stylesheet" href="/dist/APlayer.min.css">
>    <div id="aplayer"></div>
>    <script type="text/javascript" src="/dist/APlayer.min.js"></script>
>    <script type="text/javascript" src="/dist/music.js"></script>
>    ```



## 添加 文章内-音乐播放器

> 打开 [网易云](https://music.163.com/#)，选好一首歌，点击**生成外链播放器**，复制 粘贴在文章内



## 添加 动漫小人

> 1. 下载：[live2D文件](https://gitcode.net/mirrors/stevenjoezhang/live2d-widget?utm_source=csdn_github_accelerator)
>
> 2. 解压文件(文件名要修改为：live2d-widget)，将文件复制到：next --> source文件夹内
>
> 3. 更改live2d-widget下的**autoload.js**内容：注释第二行，取消第三行的注释
>
>    ```
>    // 注意：live2d_path 参数应使用绝对路径
>    //const live2d_path = "https://cdn.jsdelivr.net/gh/stevenjoezhang/live2d-widget@latest/";
>    const live2d_path = "/live2d-widget/";
>    ```
>
> 4. 打开：next --> layout --> **_layout.swig**以文本打开；在`<head></head>`标签中，添加以下代码：
>
>    ```javascript
>    <script src="/live2d-widget/autoload.js"></script>
>    ```
>
> 5. 打开：next --> **_config.yml**以文本打开，添加以下代码：
>
>    ```
>    live2d:
>      enable: true
>    ```





---

---

## 官网/文档

> 主题的GitHub官网：https://github.com/theme-next/hexo-theme-next
>
> Next官方文档：http://theme-next.iissnan.com/getting-started.html
>
> 参考文章：https://yangbingdong.com/2017/build-blog-hexo-base/
>
> ​				   https://yangbingdong.com/2017/build-blog-hexo-advanced/
>
> 图标代码：https://fontawesome.com/search
>
> 图标代码：https://fontawesome.com/v4/icons/

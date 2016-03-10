# jiedai-SEO-v1.0
jiedai.cn SEO rules

# 网站SEO标准 V1.0

@(heroone的笔记本)[服务端, 网站结构, 网页, 内容, markdown语法]

>SEO标准第一版本着网站的抓取和收录为目的，对于刚上线的网站抓取收录有促进作用，以此标准建站，可以最大化网站本身的利益。

-----------

[TOC]

### 服务端标准

#### 文件命名标准

+ 文件命名统一小写
	- 文件名称统一用小写英文字母，数字，下划线“_”和英文连字符“-”的组合。
+ 尽量按单词的英文翻译位名称，拼音次之，比如苹果的命名，优先选择apple，其次选择pingguo。
+ 命名尽可能地简短

#### HTTP状态码及重定向使用规范

+ 301状态码
	- 内容相同但是URL不同的要重定向到常用的URL上去，并返回301状态码。
		* 举个例子，`jiedai.cn`应当301重定向于`www.jiedai.cn`
	- 有用户习惯直接访问的URL，应当重定向于常用的URL，并返回301状态码
		* 例如:`jiedai.cn/jiedai/12345`应当重定向到`sh.jiedai.cn/jiedai/12345`
	- 出现URL修改或者删除时，应当重定向到新页面，并返回301状态码
+ 302状态码
	- 临时性转移网址并且短期恢复的应当将URL重定向于新的URL，并且返回302状态码
+ 404状态码
	- 页面如果被删除，必须返回404状态码，并且重定向至标准的404页面

#### robots.txt标准

+ 文件存储于网站的根目录下
+ 文件命名应为robots.txt，全部小写
+ 文件书写格式应为：
	- User-agent: *
	- Disallow: /aaa/
	- Allow: /bbb/
	- 其中user-agent的内容是搜索引擎爬虫，*泛指所有的蜘蛛，包括baiduspider，googlebot等
	- allow中的页面表示蜘蛛可以去爬取，可以收录
	- disallow中的页面表示不予抓取，不希望被收录
	- 具体的robots.txt的写法和用处可以参考百度的官方说明：
	- [关于robots.txt文件的写法]('http://www.baidu.com/search/robots.html')
+ robots.txt文件的内容需要经过SEO组的审核，如有需求，需要与SEO组进行确认后在进行更改

#### 搜索引擎爬虫

+ 根据经验以及部分行业人士的判断，百度的爬虫集中在北京网通的线路上，要确保的是网站所在的服务器对北京网通的响应速度正常
+ 爬虫会耽搁IP大量连续的请求多个页面，要保证防火墙和防采集系统的设置未对爬虫设置屏蔽规则。

### 网站结构标准

#### URL标准

+ URL静态化
	- 即URL中不包含？或者=等特殊符号，虽然搜索引擎可以正常收录动态URL但是比竞争对手多做一些就可以多一分竞争优势。
+ URL结构
	- 结构要清晰，表示的是各种同类项要归在各类目录下
+ URL简短与可阅读
	- URL的命名要尽可能的短和易记
+ URL目录层级
	- URL目录的曾经最好控制在3级内
		* http://www.jiedai.cn/  --> 根目录
		* http://www.jiedai.cn/aa/  -->一级目录URL
		* http://www.jiedai.cn/aa/bb/  -->二级目录URL
		* http://www.jiedai.cn/aa/bb/cc/  -->三级目录URL
		* 尽量避免类似http://www.jiedai.cn/aa/bb/cc/dd/ 这种四级目录URL
+ URL唯一化
	- 确保每个页面都有唯一的URL对应，避免出现不同的URL指向同一页面的情况
		* 如：开发最易忽略但也很重要的是这样的页面：
		* `http://www.jiedai.cn/jiedai`和`http://www.jiedai.cn/jiedai/`
		* 上面的例子要统一成一个形式，如果需要有追踪数据等的需求，SEO也可参与讨论并输出意见。
+ URL字母小写
+ 英文之间的连接符应当使用“_”和“-”，避免在URL中使用特殊字符
	- 例如：@,^,:空格等
+ 避免对老URL进行修改，如修改做好301重定向
+ 避免对已生成的URL进行删除操作，特别是距离首页点击距离比较近的链接，如果产生删除页面则必须返回404状态码，避免出现内容死链和协议死链的情况
+ 易被忽视的那些细节点，下面的细节点的解决方案就是301重定向，注意即可
	- `www.jiedai.cn`和`jiedai.cn`
	- `www.jiedai.cn`和`www.jiedai.cn/index.html`
	- `sh.jiedai.cn/jiedai`和`sh.jiedai.cn/jiedai/`

#### 网站导航系统

+ 整站页面须有清晰的导航系统，包括主导航，栏目导航页，页面底部导航，以及面包屑导航等等
+ 需保证每一条导航链接的可抓取性，避免采用flash,iframe,flash或ajax等特殊方式，可使用lynx在线查看
+ 导航的内容需要是可点击的文字内容，而不是图片，flash等特殊加载方法
+ 如有特殊产品需要flash等，需要和SEO部门协商

#### 扁平化

+ 网站的设计必须遵循扁平化，降低用户从首页点击进入内容页的点击次数
+ 每个层级需要注意的是设置好对于下一层级内容的指引，页面中的链接要控制在一定范围内，一般不超过100个，尽量避免过多的翻页

#### 低质量内容
> 避免发生网站结构逻辑错误而产生的大量雷同，无内容页面。

+ 避免无限空间
	- 举个例子就是，日历中的日期，如果日期能够无限增长且能访问的话，这样就会造成无限空间的，应避免之
+ 避免死循环页面
	- 如一些动态链接中的参数位置可以任意颠倒，但是页面内容却是一样的，因此类型动态页面的原因导致蜘蛛被困在此处返回不了数据，在设计过程中如遇到此类问题则需要和SEO部门沟通

#### 内链部署

+ 相关性
	- 每个页面均需要链向站内的其他页面，且连接的页面必须有相关性
+ 避免孤岛页面
	- 站内的每个页面均需要有内部链接指向，避免大量无内部页面链接指向的页面存在
		* 孤岛页面定义：从首页出发，可以到达网站中的每一个页面，如果有页面从首页中无法通过点击进入，则称之为孤岛页面。
		* 常见的孤岛页面：下架的产品页，过期的活动页

#### 追踪代码

> 现有的站内追踪代码，一个URL不要超过3个参数，并且告知SEO人员代码部署的位置

#### 对SEO不友好的技术

+ 避免使用iframe
+ 谨慎使用Ajax异步加载技术，对于重要页面和重要链接，避免使用。
+ 避免使用sessionID，DHTML，cookies，JavaScript，flash等技术展现内容
	- 使用sessionID，DHTML，cookies，JavaScript，flash等技术展现内容搜索引擎的抓取度并不十分友好，用Lynx浏览器可以检测到网页中的对SEO不友好的技术

### 网页标准

#### TDK标准

+ title要能够描述网页的主题
	- 即，title能够完整地描述网页中的模块内容，相关，推荐等，注意要绝对主题相关
+ title中必须要包含目标关键词
	- 关键词出现的频次控制在2-3次
+ title不能与其余网站相同
	- 在百度的搜索结果页中查找，保证其相似率要低于30%
+ title的字数要控制在32个，而移动端的title要控制在15个
+ 页面中的keywords不要超过10个，词与词之间用英文状态下的逗号
+ description中要有目标关键词，3-4次为最佳，在文章页可以让蜘蛛自由抓取
+ description也不要超过72个汉字

#### 代码标准

```
1. 避免使用空的<a>标签
2. 遵循xhtml规则，注意闭合标签，如果丢失标签则可能会影响搜索引擎对于页面结构的错误判断，可以使用`[w3c](http://validator.w3.com')进行验证
3. 页面元素的命名注意语义化和形式统一化
4. 避免使用多层的嵌套关系，使页面正文处于最深的嵌套中
5. 使用语义标签对页面进行规划布局
	1. 分段使用<p>而不是<b>
	2. 列表使用<ul>
	3. 表格使用<table>,<th>等标签，但要注意避免多余的嵌套
6. 正确使用<meta name="robot" content="" />标签
	1.正确使用noarchive,nofollow,noindex等属性,防止错误屏蔽了爬虫
7. 避免行内样式和<body>内的css样式，会造成页面的渲染问题，降低效率
8. 合理使用H1~H6标签，使网页文本具有层次性，一般网页使用的为H1-H3标签，其中页面中只需1个H1标签。H标签的大小加粗不用再css中定义了，搜索引擎是可以解析css的
9. 减少页面上的无关信息
	1. 无意义的代码，文本text/html code = x,x越大，则网页质量就越高，减少DOM数量可以提升页面的渲染速度
	2. 广告，隐藏菜单等等使用js调用，提高页面的信噪比
10. 预先在<img>中定义好每个图片的大小,在出现图片加载不出的情况时不会破坏页面结构
11. 页面所有的图片需要加上Alt属性，并且调用可以说明图片信息的周围信息，图片最好使用jpg和png
12. 避免空的<img src=>,这样会造成额外请求，尤其是大型网站的图片较多，细节会拉出差距的
13. 启用`if-Modified-Since`,用于提醒SE自上次抓取后页面内容是否发生了变化，可以节约带宽和开销
14. 开启Gzip压缩所有文件，以提高传输效率
15. 设置Expires/Cache-Control，对于静态元素进行无限期地缓存，动态的则设置一个合理的缓存时间，下次可以通过改变文件名来重置，例如jiedaistyle-v1.css==>jiedaistyle-v2.css
```

#### 链接标准

+ 链接的位置最好处在文字的下方
+ 链接的锚文字要有精确的叙述意义
+ 指向目标网页的url要是统一格式的，注意url末尾是否有/符号
+ 避免非常规的方式部署链接，如js,flash或者option下拉菜单
+ nofollow标签要统一由SEO人员负责添加
+ 避免出站链接，如有必要，还希望于SEO人员沟通

#### 网页体积标准

+ 页面体积控制在一定的大小内，建议在180K以内，可以从以下三处入手：
	- 减少HTML体积
	- 减少网页其他元素体积
	- 开启服务器压缩，Gzip等
	- 推荐一个工具www.webpagetest.org,可以检查网页各个元素响应瀑布图
+ 共享CSS样式和脚本样式，相同的样式用户只需下载一次，压缩CSS文件中的空白
+ 压缩js代码移除重复，无用的js代码，使代码简洁化
+ 合并js，css文件减少http请求
+ 压缩html代码中的tab、空白元素使页面加载更快

### 内容标准

#### 关键词分析

+ 撰写文章或者进行专题策划前要进行关键词分析
    - 分析出与文章相关的关键词，如借贷，个人征信，信用等级等于小额贷款类的文章相关。
    - 用户搜索量高的话题优先考虑，搜索量小的话题降低优先级。
+ 文章的关键词可以通过对整体的需求分析来选择，优先选择搜索量高但是借贷网中缺少的关键词。
    - 如上海贷款公司是热词，但是网站中却很多内容，可以不用关注，而上海购房商业贷款，可能网站没有相关内容，优先选择。
+ 关键词分析完成后要记录关键词的百度排名，以作日后参考。

#### 文章撰写与伪原创

+ 文章标题中包含关键词，并且尽量左置靠前。
    - 上海购房商业贷款资质大全 借贷网带你全知全晓
+ 文章中第一段内出现关键词，并且尽量靠前，控制在200字以内须至少出现一次关键词。
    - 如：2016年上海购房商业贷款机构都有哪些？借贷网带您一一拜访...
+ 关键词在文章中出现的次数要控制在一定的百分比中，要求是2%-4%。
+ 文章内容的字数在400字以上，尽量配图，并且图片的比例协调，文本的排版整齐。
+ 文章要给不同的段落设置小标题，用`<h2>`标签封装
+ 文章内至少要有两个链接指向对应的页面，锚文本要精确的描述对应页面的内容，避免使用详情参见，具体咨询，更多请看等等模糊定义的词句。
+ 从别处复制来的文章要修改标题，确保新标题与原标题的相似度降低到30%以下，通俗点说是10个字要有7个字不同。
+ 复制来的文章一定要经过二次编辑，此次编辑需要做的是剔除掉大量的高频词，换上我方的相关词。
+ 文章发布时要设置好标签，确保文章关联到了其他文章。

#### 其他注意事项

+ 专题上线前要与SEO部门商议，确保内容的可搜索性和页面的可抓取性良好。
+ 专题下线后，能不删除的页面尽量不删除，必须删除的页面则将URL重定向至首页。
+ 运营活动上线后要建立流量统计报表，数据定期发送，总结，汇报。

> 向ITSEO-yexi致敬致谢

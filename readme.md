[![License: LGPL v3](https://img.shields.io/badge/License-LGPL%20v3-blue.svg)](http://www.gnu.org/licenses/lgpl-3.0)

### 58同城品牌公寓爬虫


项目缘起于[高德API+Python解决租房问题](https://zhuanlan.zhihu.com/p/21883516),
修修补补之后上线了[58公寓高德搜房(全国版)：http://codelover.link:8080/](http://codelover.link:8080/)。

经过了多次代码优化、内容改版、新增房源等...

相关文章可移步知乎专栏：[一只程序汪的自我修养](https://zhuanlan.zhihu.com/codelover)



简单介绍一下工程结构：

1. ASP.NET MVC4：58HouseSearch\58HouseSearch.sln
2. ASP.NET Core：58HouseSearch.Core\58HouseSearch.Core.sln（已迁移至VS2017）


以上两个版本大体逻辑一致，Core版本为当前线上版本，新增了豆瓣租房小组数据。

下一个版本为HouseCrawler.Core，初步计划以下功能：

1. 爬虫数据固化到数据，优化爬虫策略
2. 前端页面改版，交互优化，内容引导等


### HouseCrawler.Core版本说明

1. 当前版本已完成数据固化功能，项目代码为“HouseCrawler.Core”。
2. 此项目已分成HouseCrawler.Core和HouseCrawler.Web，其中Web已经移除了相关爬虫逻辑，Core中有爬虫+Web；
3. 已上线部分豆瓣数据分析，使用[jieba.net](https://github.com/linezero/jieba.NET)分词提取价格功能已初步完成。



以下是日常更新：

### 2017.06.24
1、新增独立Web项目，把网站和爬虫分离
2、更新分析数据逻辑


### 2017.06.12
1、引入分词库[jieba.NET](https://github.com/liguobao/jieba.NET) （没有nuget包，暂时以项目的形式引入）
2、开始做豆瓣数据分析

### 2017.06.06
1、新增根据发布时间过滤数据、修改默认显示数量
2、调整代码结构，新增log类


### 2017.06.05
1、修复了昨天的Bug，顺便删除了PV数据的统计
2、引入友盟做站点统计（实在是懒得弄...）
3、已更新到[地图搜房：http://codelover.link:8080/](http://codelover.link:8080/)、同时在[yibaobao.wang:8080](yibaobao.wang:8080)有一个备用站点



### 2017.06.04

1、初步完成HouseCrawler.Core中的数据固化，线上版本每小时拉取一次数据
2、前端UI改版初步完成，基本可用
3、已知bug：发布的时候缺少配置文件，稍后解决


### 2017.03.11
1. 迁移至.NET Core1.1.1,项目变更为csproj，VS2017可用，如需要老版本，自助切换至forVS2015分支，没必要情况代码不同步（懒嘛


### 2016.12.02
1. 新增HouseCrawler.Core，计划基于此版本做数据固化以及定时爬虫
2. 58HouseSearch为ASP.NET MVC4版本，58HouseSearch.Core为ASP.NET core版本，两者暂停更新

### 2016.11.27
1. 完成豆瓣租房小组功能上线
2. 细化功能待产品姐姐PRD了


### 2016.11.22
1. 新增豆瓣租房小组数据
2. 租房小组数据未完善


### 2016.10.12
1. 项目迁移ASP.NET Core 已初步完成， ASP.NET MVC版本停止更新
2. 着手引入定时任务，定时爬取数据，缓存落地
3. 新增免责说明



### 2016.10.02
1. 更改JS适应ASP.NET Core版本
2. 更改pv.json文件读取

### 2016.10.02
1. 新增ASP.NET Core版本。


### 2016.09.29
1.解决新增PV记录并发问题
2.加入log4net日志功能排查问题


### 2016.09.11
1.改进JS结构，修复上一版本的bug


### 2016.09.11
1. 重构搜索页面请求，改为JS异步请求数据
2. 改进上次重构的JS结构


### 2016.08.25
1. 上线步行导航,满足需要步行上班的狼友们
2. 辣鸡前端代码等待重构，实在没法看下去了


### 2016.08.24
1. 58品牌公寓、58诚信租房完成页面改造
2. 自动加载前20页数据，按价格区间显示


### 2016.08.24
1. 去除互助租房页面价格标签，改用价格区间图标
2. 新增价格区间图标，第一版为渐变色，效果还好
3. 薪资价格区间相关数据，下版本完成其余页面改造


### 2016.08.23
TODO:
1. 新增问题反馈,邮件服务?限制IP？JSON记录？
2. 侧边栏调整，移动地图的时候不是很方便

### 2016.08.23
1. 新增侧边栏功能，页面初始化打开侧边栏，点击其余页面收起侧边栏(感觉也不是很好,回头优化一下)
2. 优化前台CSS代码（其实只是收成了一个CSS文件，逃...
3. 价格标签过多之后密集恐惧症发作的小伙伴等下一次更新（明天？


### 2016.08.22
1. 互助租房页面新增价格标签，地图上可直接显示价格
2. 为了避免缩放工具栏挡住导航信息，调整导航栏位置
TODO：优化58同城查询速度，新增价格标签，互助租房新增价格过滤



### 2016.08.21
1. 新增“上海互助租房数据”，此项目房源基本真实可靠，无中介。详情见微博：http://weibo.com/u/5389952376
2. 优化获取互助租房数据，200条数据基本在1秒内可以拿的到
3. 由于数据时效性问题，互助租房数据原则上只取前200条数据
4. TODO：互助租房价格过滤（互助租房不提供过滤，只能自己做）？非上海互助租房数据（感觉没有...）？
5. 感谢互助租房项目（http://www.huzhumaifang.com/）。



### 2016.08.21
1. 修复一个获取数据正常，地图无法显示数据的bug（衣衣重构代码弄出来的...）
2. 经测试后发现，某些地图没有诚信房源数据（考虑这种情况是否直接取个人出租信息）


### 2016.08.20
1. 继续感谢衣衣重构的代码，广告数据也基本过滤了
2. 地图房源显示直接附上租金，更换房源链接之后实现直接定位到具体房源
3. 去除不必要的JS文件，使得两个页面使用同一个JS


### 2016.08.20
1. 新增“58同城诚信房源”（PS：看了下房源，感觉一点都不诚信...只能祝好运了。）
2. 有点想去抓微博某账号数据，不过微博这种鬼...想放着吧。
3. TODO：优化一下查询速度（感觉可以并发请求页面，不过我的辣鸡服务器是否扛得住是个问题）；去除页面广告数据


#### 2016.08.13
1. 更新后同步挂载于： http://codelover.link:8080
2. 下一步准备加入更多的房源信息(PS:只是准备...)
3. 知乎专栏无耻求赞（ https://zhuanlan.zhihu.com/p/21998221）

#### 2016.08.13
1. 加入城市名匹配58同城城市简称功能，去除城市名转拼音导致无法准确定位城市问题
2. 继续感谢衣衣姐去除58同城广告数据的commit


##### 2016.08.13
1. 去除输入城市名定位问题，改为移动地图直接获取地图中心所在城市
2. 下一步准备构建城市名-城市简称字典，用于快速匹配正常的58同城地址
3. 修复已知bug...

##### 2016.08.12
1. 感谢衣姐的重构代码的commit
2. 修复输入城市中文名导致地图房子位置点击后跳转页面错误问题
3. 输入城市名无法直接定位到城市这个问题正在解决


##### 2016.08.08
1. 完成指定城市名定位
2. 修复上版本bug
3. 更正为全国版


##### 2016.08.7
1. 改版于 https://zhuanlan.zhihu.com/p/21883516
2. 使用高德地图API
3. 挂载于 http://codelover.link:8080
4. 手动输入城市名还有点bug，暂时无法正常使用

# 1. 博客项目
### 部署地址：https://blog.darkcraft.top/  
### 文章创作接口：https://blog.darkcraft.top/compose
### [项目源码](https://github.com/ClarkKenty/blog)
#### [JAVA](https://github.com/ClarkKenty/blog/tree/main/src/main/java/com/darkcraft) [前端&静态文件](https://github.com/ClarkKenty/blog/tree/main/src/main/webapp)
### 概述
#### 框架：整体采用SSM+Thymeleaf进行编写  

#### ORM框架采用了mybatis来进行数据库映射

#### 后端：写的较为简单，流程为：先在数据库中添加需要的表->然后根据表中数据写相应的pojo并生成getter和setter->在dao中通过注解方式将SQL操作映射到一个个函数上面->在service中写接口以及实现->最后写controller(没有将具体操作放在service里面，写的不太规范)
#### 前端：
##### 设计方面：
* 首页为了保持较为简洁的风格，放了一些SVG路径动画以及一个时间轴，并使用js监听鼠标滚轮事件来实现页面间的平滑移动（[代码](https://github.com/ClarkKenty/blog/blob/main/src/main/webapp/js/script.js)），后期可在首页增加一页作为个人介绍。
* 文章导航界面采用书本翻页式设计，该特效的实现比较复杂，大致思路是将翻页时的一张纸横向十四等分，每一部分翻转不同的角度来模拟翻页的特效(参考了codepen上面的一个设计)。在翻页动画运行时通过js将Dom插入每个部分，并通过设置padding等方式将每一部分中的内容平移到对应的位置。
* 文章界面使用了卷轴式设计，进入时会有一个下拉渐现式特效。
* 使用rem代替px作为尺寸单位，以实现浏览器缩放时页面大小的自动调整。
##### 代码方面:
* 前端没有使用任何框架，使用原生js进行逻辑处理
* 通过Thymeleaf插入接口来返回后端数据
# 2. 线上书城项目
### 部署地址：https://darkcraft.top/demo/bookmarket
### [项目源码](https://github.com/ClarkKenty/bookmarket)
### 概述

#### 主要功能：

1. 注册：用户的注册可以在前台实现，用户可以在前台进行基本信息的录入，并且进行信息的注册，添加。

2. 商品分类：可以进行商品的分类的展示，对于图书的类别，以列表的形式进行首页的展示，点击后，可以进行相应图书的信息查看。

3. 热销：推荐了热销的图书，在首页以排行的形式，展示热销书籍，后台可以通过Apriori算法，进行相关的书籍推荐。

4. 新品：对新发布的图书信息进行展示，以列表，时间的顺序进行图书的排序，可以查看到最新的图书信息。

5. 购物车：用户可以在线进行图书的购买，添加，添加到购物车中，进行图书的购买。

#### 框架：spring boot + vue  

#### ORM框架使用hibernate

#### 后端：大部分使用的是jpa内置的接口，有个别较为复杂的操作内置接口无法处理，直接用的sql语句或是提前准备好的存储过程。
#### 前端：为简化操作，使用了element ui作为css框架，并通过vue的深度选择器对部分样式进行重写来达到界面风格的统一。在管理员界面使用了vcharts来生成图表，以达成较为美观的数据展示。

[项目部署时遇到的问题整理](https://blog.darkcraft.top/article?num=12&back=2)

[课程设计报告](https://onedrive.live.com/view.aspx?resid=8FFAEA0D1251E3B3!197457&ithint=file%2cdocx&authkey=!AGmdNNX3yG8SuDU)
# 转发树可视化实现

> pub date: 2021-04-09
> modified: 2021-04-09
> language: CN

![image-20210409130022723](RepoTreeVis_imgs/image-20210409130022723.png)

## 简介

北京航空航天大学『数据可视化分析技术』课程第二次小作业作品。展示了一个推文 / 博文的转发途径

演示链接：[https://apassbydreg.github.io/RepostTreeVisualization/](https://apassbydreg.github.io/RepostTreeVisualization/)

参考论文：[R-Map: A Map Metaphor for Visualizing Information Reposting Process in Social Media](https://ieeexplore.ieee.org/document/8805419)

>S. Chen, S. Li, S. Chen and X. Yuan, "R-Map: A Map Metaphor for Visualizing Information Reposting Process in Social Media," in IEEE Transactions on Visualization and Computer Graphics, vol. 26, no. 1, pp. 1204-1214, Jan. 2020, doi: 10.1109/TVCG.2019.2934263.

## 图标释义

本可视化主要分为两部分，左侧是关键节点部分，右侧是每个关键节点对应的时间线，下方是节点信息的展示区域。图标的具体释义如下：

-   深蓝色圆圈：根节点，即转发树上的原始博文
-   浅蓝色圆圈：关键节点，是所有节点中子树从大到小排列前 K 位的节点
-   绿色方块：颜色从浅到深对应了该时间点处节点的平均深度从小到大

## 交互逻辑

- 界面默认使用模拟的样例数据进行展示，你也可以选择你自己的数据进行可视化。需要注意的是选择的数据需要符合样例数据的格式（你可以点击右侧按钮查看样例数据）。
- 你也可以通过点击标题中的蓝色部分下载当前可视化的数据。
- 你可以通过 `Add / Remove` 按钮进行关键节点数量的增减操作
- 你可以通过点击任意一个节点或时间块以在下方查看该部分的详细信息

## 实现方法

本实现采用 Vue.js 作为基础设施，实现了一个响应式的页面，让数据可以自动地

另外利用了 Material Design Bootstrap 辅助开发，大大简化了代码的复杂度

数据部分使用了少量基于深度优先搜索的简单树算法
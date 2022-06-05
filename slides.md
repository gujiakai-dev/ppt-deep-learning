---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://static.gujiakai.top/static/ppt/deep-learning/images/elonmusk.jpg
# apply any windi css classes to the current slide
class: "text-center"
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## 深度学习课程汇报
# persist drawings in exports and build
drawings:
  persist: false
---

<div class='text-5xl'>
基于深度学习的 Tesla 股票预测模型
</div>

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br mb-30 mr-15 flex gap-2">
汇报人：顾佳凯
</div>
<div class="abs-br mb-20 mr-8 flex gap-2">
汇报日期：2022.6.8
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/real-jiakai/slidev-ppt" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
大家好，今天我给大家带来的汇报主题是基于深度学习的Tesla股票预测模型。
-->

---

# 背景介绍

<div grid="~ cols-2 gap-10">

<div class="text-xl tracking-wide">

2022 年 4 月，Elon Musk 和 Twitter 达成收购协议。Elon Musk 的这一举动促使当时 Twitter 的股票价格飙升以及 Tesla 的股票价格暴跌。

但随着 Elon Musk 在 5 月份宣布收购 Twitter 的计划搁置，Twitter 的股票价格开始暴跌，Tesla 的股票前景也并不明朗。

本文基于决策树模型、随机森林模型以及 AdaBoost 模型，分别搭建了股票涨跌预测模型。搭建模型用到的数据源自雅虎财经公开的 [Tesla 历史股票价格数据集](https://finance.yahoo.com/quote/TSLA/history?p=TSLA)。

</div>

<div>

<img src="https://static.gujiakai.top/static/ppt/deep-learning/images/tesla-stock.jpg" class="bg-right">

</div>
</div>

<!--
背景介绍，可额外扩展的点
  - Elon Musk的财富缩水了近20%，在我的4月7日日记中，Elon Musk的财富是279.5$B，
  现在其身价为219$B。
  - Elon Musk的商业头脑、敢于冒险、高瞻远瞩，铸就了他的伟大。
  - 从SpaceX到Tesla，再到Neuralink、Starlink，无不展现其野心与才华。
  -
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# 模型结果比较分析

### 将数据集中前 90%的数据作为训练集，后 10%的数据作为测试集。得到如下图所示的实验结果。

<br/>
<br/>

|  模型名  | 模型准确度 | 特征重要性最大值 |
| :------: | :--------: | :--------------: |
|  决策树  |    0.57    |       MA10       |
| 随机森林 |    0.52    |      EMA12       |
| AdaBoost |    0.57    |    MACSsignal    |

<!--
搭建的3个模型准确度均在50%以上，说明搭建的模型较为可靠。
右侧的3组数据是股票走势的评判标准，无需过多深究。
 -->

---

# 收益回测曲线绘制

<div grid="~ cols-2 gap-10">

<div class="text-xl tracking-wide">

在商业实战中，我们更关心股票预测模型的收益回测曲线(又称为净值曲线)，即观察根据搭建的模型获得的结果是否比不利用模型获得的结果更好。

可视化结果如右图所示。图中上方的曲线为根据模型得到的收益率曲线，下方的曲线为股票本身的收益率曲线，可以看到，利用模型得到的收益还是不错的。

但要说明的是，本实验搭建的模型过于理想化了，真正的股市是错综复杂的，这里仅仅是为了展示深度学习模型搭建的效果。

</div>

<div>
<img src="https://static.gujiakai.top/static/ppt/deep-learning/images/chart.jpg" class="bg-right">
</div>
</div>

---

# 尾语

<div class="text-xl tracking-wide">

这个学期深度学习课程实验全部都出自一本名为《Python 大数据分析与机器学习商业案例实战》的书籍。这本书籍，网上目前还没有电子版流出，感兴趣的同学可以去《京东读书》app 购买电子版书籍阅读。

我课程汇报的 3 个模型就改编自随机森林模型章节的股票涨跌预测模型，我只是将数据集及一些
数据预处理步骤替换掉了而已。其实深度学习我学的一团糟。

深度学习是当下的一个风口，仅凭一个学期的课程最多入个门，我个人感觉我还没有入门，平时的作业，
对着 ppt 敲代码没多大用处，最多就是完成老师的任务罢了。

其实我作业的很大一部分都是直接去 GitHub 上下载源代码上交的。🥲

再见深度学习！

[作业源代码](https://gitee.com/gujiakai/deep-learning-homework)👈

</div>

<div>

<img src="https://static.gujiakai.top/static/ppt/deep-learning/images/book_cover.jpg" class="bg-right abs-br">

</div>

---

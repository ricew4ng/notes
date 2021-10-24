## 简介
- Flex 是 Flexible Box 的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性
-
- 任何一个容器都可以指定为 Flex 布局。
-
  #+BEGIN_QUOTE
  .box{
    display: flex;
  }
  #+END_QUOTE
-
- 注意，设为 Flex 布局以后，子元素的float、clear和vertical-align属性将失效。
-
## 基本
- 采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称"项目"。
- ![](https://raw.githubusercontent.com/ser4wang/static/master/20210910101550.png)
- 容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做main start，结束位置叫做main end；交叉轴的开始位置叫做cross start，结束位置叫做cross end。
- 项目默认沿主轴排列。单个项目占据的主轴空间叫做main size，占据的交叉轴空间叫做cross size。
-
## 容器的属性
- 下6个属性可被设置在容器上。
- flex-direction
  flex-wrap
  flex-flow
  justify-content
  align-items
  align-content
-
### flex-direction属性
- flex-direction属性决定主轴的方向（即项目的排列方向）。
- .box {
  flex-direction: row | row-reverse | column | column-reverse;
  }
- ![](https://raw.githubusercontent.com/ser4wang/static/master/20210910101828.png)
- 它可能有4个值。
- row（默认值）：主轴为水平方向，起点在左端。
  row-reverse：主轴为水平方向，起点在右端。
  column：主轴为垂直方向，起点在上沿。
  column-reverse：主轴为垂直方向，起点在下沿。
-
- flex-wrap属性
  默认情况下，项目都排在一条线（又称"轴线"）上。flex-wrap属性定义，如果一条轴线排不下，如何换行。
- ![](https://raw.githubusercontent.com/ser4wang/static/master/20210910102150.png)
- .box{
    flex-wrap: nowrap | wrap | wrap-reverse;
  }
-
- （1）nowrap（默认）：不换行。
- ![](https://raw.githubusercontent.com/ser4wang/static/master/20210910102224.png)
- （2）wrap：换行，第一行在上方。
- ![](https://raw.githubusercontent.com/ser4wang/static/master/20210910102236.png)
- （3）wrap-reverse：换行，第一行在下方。
- ![](https://raw.githubusercontent.com/ser4wang/static/master/20210910102247.png)
-
### flex-flow
flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap。
- .box {
  flex-flow: <flex-direction> || <flex-wrap>;
  }
-
### justify-content属性
justify-content属性定义了项目在主轴上的对齐方式。
- .box {
  justify-content: flex-start | flex-end | center | space-between | space-around;
  }
- ![](https://raw.githubusercontent.com/ser4wang/static/master/20210910102757.png){:height 771, :width 637}
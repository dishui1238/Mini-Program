# 微信小程序开发学习笔记

## flex布局
> 采用 Flex 布局的元素，称为 Flex 容器（flex container），简称"容器"。它的所有子元素自动成为容器成员，称为 Flex 项目（flex item），简称"项目"。

### 容器的属性
+ flex-direction: row(默认) | row-reverse | column | column-reverse; 决定主轴的方向
```css
.father{
      border: 1px solid #f00;
      /*1.把父盒子设置成伸缩布局 子元素实现水平排列 */
      display: flex;  
      /* 2.设置flex方向 */
      flex-direction: column;
    }
```
+ justify-content: flex-start(默认) | flex-end | center | space-between* | space-around; 主轴上(水平)的对齐方式
   1. 水平垂直居中定位方式实现
   ```css
   .father{
     width:500px;
     height:500px;
     position:relative;
   }
   .son{
     width:100px;
     height:100px;
     position:absolute;
     left:50%;
     top:50%;
     /*margin-left:-50%;
     margin-top:-50%;*/
     transform:translate(-50%,-50%);
   }
   ```
   2. flex布局实现水平垂直居中
   ```css
   .father{
     display:flex;
     justify-content:center;
     align-items:center;
   }
   ```
+ align-items: flex-start | flex-end | center | baseline | stretch; 定义项目在交叉轴(y轴)上如何对齐
+ flex-wrap: nowrap(默认) | wrap | wrap-reverse; 定义如果一条轴线排不下，如何换行

### 项目的属性
+ `order: <integer>` 定义项目的排列顺序。数值越小，排列越靠前，默认为0。
+ `flex-grow: <number>` 定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
+ `flex-shrink: <number>` 定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小
+  `flex-basis: <length>` | auto 定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。
+ `flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]`
+ `align-self: auto | flex-start | flex-end | center | baseline | stretch;` 允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。

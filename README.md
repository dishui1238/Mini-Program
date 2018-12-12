# 微信小程序开发学习笔记

## flex布局

### 核心属性
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

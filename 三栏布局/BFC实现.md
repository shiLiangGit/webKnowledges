### 双飞翼布局 --- 浮动实现

```
左右栏均设置左右浮动
中间内容设置BFC, 除去左右两边，自适应
左右栏文档流前面，先行渲染
```



#### 最终效果

![image-20220602164528194](http://rc0nh980a.hn-bkt.clouddn.com/images/image-20220602164528194.png)

### 实现步骤

1、左右栏浮动+中间内容BFC

### 最终源码：

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>BFC布局</title>
</head>
<style>
  body,html{height: 100%;margin: 0px;padding: 0px;}
  div, p {padding: 0;margin: 0}
  .header, .footer{height: 50px;line-height: 50px;background: cadetblue;text-align: center;font-size: 16px;color: #fff;}
  .footer{background: darkolivegreen;}
  .middle,.left,.right{height: 400px;line-height: 400px;font-size: 18px;text-align: center;}
  .clearfix:after {content: "";display: table;clear: both;}
  .left {width: 200px;background-color: lightcyan;}
  .right {width: 200px;background-color: lightgreen;}
  /*第一步设置left，right：左右浮动*/
  .left{
    float: left;
    background-color: lightsalmon;
  }
  .right{
    float: right;
    background-color: lightskyblue;
  }
  /*设置middle为BFC，即可（利用BFC的宽度自适应）*/
  .middle{
    overflow: hidden;
    background-color: lightpink;
  }
</style>
<body>
<div class="header">BFC布局</div>
<div class="container clearfix" >
<!--  布局方式，先写左右两栏div，左右写中间内容div-->
  <div class="left">left</div>
  <div class="right">right</div>
  <div class="middle">
    <div class="cont">我是内容区域</div>
  </div>
</div>
<div class="footer">Footer内容区</div>
</body>
</html>
```
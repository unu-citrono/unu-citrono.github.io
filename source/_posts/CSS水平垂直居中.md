---
title: CSS水平垂直居中
date: 2022-03-21
tags:
---
***[注]：不建议使用table进行居中，不利于HTML语义化***

​		***position + transform平移效果 = position + margin（宽高已知）***

### 水平居中

* 定宽元素

  margin： 0 auto;

* 不定宽元素

  1. flex布局：父元素设置

     ```{ display: flex; justify-content: center; }```

  2. 设置居中元素display为table

     ```{ display: table; margin: 0 auto; }```

  3. 多个元素共同居中

     ```js
     // 子元素
     {
         display: inline-block;
     }
     // 父元素
     {
         text-align: center;
     }
     ```

* position

  ```js
  // 父元素
  {
      position: relative;
  }
  // 子元素
  {
      position: absolute;
      left: 50%;
      transform: translate(-50%); // 宽度未知时，已知可使用margin
  }
  
  ```

  

  

### 垂直居中

* 单个元素 ，父元素：

  1. 定高且为文本：`line-height` 为 自身高度

  	2. 不定高：设置padding相同的top和bottom
  	2. position（同水平居中思路）

* 多个元素：

  1. flex布局

     ```js
     // 父元素
     {
         display: flex;
         align-items: center;
     }
     ```

  2. display：table

  ![image-20220320171748437](C:\Users\MI\AppData\Roaming\Typora\typora-user-images\image-20220320171748437.png)

  ```html
  <div class="parent">
      <div class="container">
          <p>12345678</p>
          <p>12345678</p>
          <p>12345678</p>
      </div>
  </div>
  ```

  ```js
  .parent {
      display: table;
  }
  .container {
      display: table-cell;
      vertical-align: center;
  }
  ```

  

### 水平垂直居中

* flex布局

  ```js
  // 父元素
  {
      display: flex;
      justify-content: center;
      align-items: center;
  }
  ```

  

* position

  ```js
  // 父元素
  {
      position: relative;
  }
  // 子元素
  {
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
  }
  ```

* display: table

  ```js
  // 父元素
  {
      display: table;
  }
  // 子元素
  {
      
      display:table-cell;
      text-align:center;
      vertical-align: middle;
  }
  ```

  
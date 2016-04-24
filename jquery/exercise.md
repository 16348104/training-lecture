# 练习题

## PART I:  jQuery 核心

1. 为所有 div 的子 h1 添加背景色

  ```html
  <body>
  <h1>abc</h1>
  <div>
      <h1>div-1</h1>
      <h1>div-2</h1>
  </div>
  <h1>xyz</h1>
  </body>
  ```

2. 设置一个页面的背景色为红色


3. 隐藏一个表单内的所有 input

  ```html
  <body>
  <form name='demo_form'>
      First name: <input type="text" name="fname"><br>
      Last name: <input type="text" name="lname"><br>
      <input type="submit" value="Submit">
  </form>
  </body>
```

4. 查找下拉列表某个选项的内容

  ```html
  <body>
  <select id="myselect">
      <option value="1">Option-1</option>
      <option value="2">Option-2</option>
      <option value="3">Option-3</option>
  </select>
  </body>
  ```
  
  希望输出: "Option-2"

5. 选中 Female

  ```html
  <body>
  <form action="">
      <input type="radio" name="sex" value="male" checked>Male<br>
      <input type="radio" name="sex" value="female">Female
  </form>
  </body>
  ```

6. 使用 jQuery 动态的把以下 div 及其内容添加到 `<body>` 标记中 :

  ```html
  <div><h1>JQuery Core</h1></div>
  ```

7. 选择某一个标记的内容

  ```html
  <body>
  <ui>
      <li>Html Tutorial</li>
      <li>Mongodb Tutorial</li>
      <li>Python Tutorial</li>
  </body>
  ```
  
  希望输出: "Mongodb Tutorial"

8. 使用 jQuery 为下面的列表添加 `<b>` 标记和它的索引
    
    ```html
    <body>
    <ul>
        <li>Html Tutorial</li>
        <li>Mongodb Tutorial</li>
        <li>Python Tutorial</li>
    <ul>
    </body>

    ```
    
    希望变成:
    
    <ul>
      <li><b>0: Html Tutorial</b></li>
      <li><b>1: Mongodb Tutorial</b></li>
      <li><b>2: Python Tutorial</b></li>
    </ul>
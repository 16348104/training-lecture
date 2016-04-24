# 练习题

## PART I: jQuery 核心

1. 为所有 `div` 的子 `h1` 添加背景色

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

3. 隐藏一个表单内的所有 `input`

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

6. 动态的把以下 `div` 及其内容添加到 `body` 标记中 :

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

8. 为下面的列表添加 `b` 标记和它的索引
    
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
    
## PART II: CSS
1. 点击段落，输出其 `background-color`

    ```html
    <body>
    <p class=".highlight">jQuery Exercises</p>
    <p>and Solution.</p>
    </body>
    ```
    
    ```css
    <style>
        p {
            margin: 8px;
            font-size: 16px;
        }
    
        .myclass {
            color: #FA5858;
        }
    
        .highlight {
            background: #CEF6F5;
        }
    </style>
    ```

2. 为段落添加 `myclass`

    ```html
    <body>
    <p>jQuery Exercises</p>
    <p>and Solution.</p>
    </body>
    ```
    
    ```css
    <style>
        p {
            margin: 8px;
            font-size: 16px;
        }
    
        .myclass {
            color: #FA5858;
        }
    
        .highlight {
            background: #CEF6F5;
        }
    </style>
    ```

3. 输出 `p` 和 `div` 的高度和宽度

    ```html
    <body>
    <p> jQuery Exercises</p>
    <div style="height:75px;width:200px;padding:10px;margin:3px;border:1px solid blue;background-color:#81DAF5;"></div>
    </body>
    ```

4. 输出 `p` 的 `scrollTop` 和 `scrollLeft` 值

    ```html
    <body>
    <p></p>
    </body>
    ```

5. 输出 `p` 的 `position` 值

    ```html
    <body>
    <div style="height:75px;width:200px;padding:10px;margin:3px;border:1px solid blue;background-color:#F3E2A9;">
    </div>
    <p></p>
    </body>
    ```

6. 输出 `div` 和 `p` 的 `innerHeight` 和 `innerWidth`

    ```html
    <body>
    <div></div>
    <p></p>
    </body>
    ```

7. 输出 `div` 和 `p` 的 `outerHeight` 和 `outerWidth`
    
    ```html
    <body>
    <div></div>
    <p></p>
    </body>
    ```

8. 判断 `div` 是否使用了 `.divclass`

    ```html
    <body>
    <div id="div1" class="divclass"></div>
    <div id="div2"></div>
    <div id="div3"></div>
    </body>
    ```
    
    ```css
    <style>
        .divclass {
            width: 90px;
            height: 75px;
            margin: 5px;
            background-color: #F3E2A9
        }
    </style>
    ```

9. 输出 `p` 的 `offset` 值

    ```html
    <body>
    <p></p>
    </body>
    ```
    
    ```css
    <style>
        p {
            margin-top: 20px;
            margin-left: 10px;
            padding: 5px;
            border: 2px solid #666;
        }
    </style>
    ```

10. 为 `p` 添加样式切换

    ```html
    <body>
    <p></p>
    </body>
    ```
    
    ```css
    <style>
        p {
            margin-top: 20px;
            margin-left: 10px;
            padding: 5px;
            border: 2px solid #666;
        }
    </style>
    ```
# jQuery 练习题

## PART I: 核心

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
  
## PART II: Event  

1. 为 `p` 添加单击和双击事件 

  ```html
  <body>
  <p>Click me!</p>
  </body>
  ```
  
  单击追加以下段落
  
  ```html
  <p>This is a click Event</p>
  ```
  
  双击追加以下段落
  
  ```html
  <p>This is a double-click Event</p>
  ```

2. 为 `Field 1` `input` 添加 `blue` 事件响应

  ```html
  <body>
  <form>
      <input id="field1" type="text" value="Field 1">
      <input id="field2" type="text" value="Field 2">
  </form>
  </body>
  ```

3. 当 `input` 发生改变时，为其追加 `p` 段落

  ```html
  <body>
  <form name='demo_form'>
      First name: <input type="text" name="fname"><br>
      Last name: <input type="text" name="lname"><br>
      <input type="submit" value="Submit">
  </form>
  </body>
  ```

4. 当标题被点击时，隐藏所有标题

  ```html
  <body>
  <h1>Heading-1</h1>
  <h2>Heading-2</h2>
  <h3>Heading-3</h3>>
  </body>
  ```

5. 双击段落时，切换背景色

  ```html
  <body>
  <p>Double-click here to change the background color.</p>
  </body>
  ```
  
  ```css
  p {
    background: blue;
    color: white;
  }
  p.dbl {
    background: yellow;
    color: black;
  }
  ```

6. 单击 `h1` 添加另一个 `h1`

  ```html
  <h1>Click me to add another!</h1>
  ```

7. 单击每个 `header`， 显示 `on()` 方法传递的数据

  ```html
  <p>Click on each header element to return the data passed with the on() method.</p>
  <h3>This is a header1.</h3>
  <h3>This is another header2.</h3> 
  ```
  
  单击 header1 显示:
 
  Header1. paragraph has Event data: 0
  
  单击 header1 显示:
  
  Header2. paragraph has Event data: 1

8. 单击 `buttoon` 切换 `p` 背景色 

  ```html
  <body>
  <div style="background-color:yellow">
      <p>Click the button to change the background color of this paragraph.</p>
      <button>Click me!</button>
  </div>
  </body>
  ```

9. 单击时输出光标相对于 `document` 的 `top` `left`
   
10. 禁用 User ID

  ```html
  <body>
  <p>User ID : <input type="text" id='field1'></p>
  <p>Password : <input type="password" id='field2'>
  </body>
  ```

## PART III: CSS
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
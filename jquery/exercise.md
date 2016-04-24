# 练习题

## PART I:  jQuery 核心
1. Find all h1 elements that are children of a div element and apply a backgroud to them.

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

2. Set the background color of a page to red.


3. Hide all the input elements within a form.

  ```html
  <body>
  <form name='demo_form'>
      First name: <input type="text" name="fname"><br>
      Last name: <input type="text" name="lname"><br>
      <input type="submit" value="Submit">
  </form>
  </body>
```

4. Find the specific option tag text value of a selected option.

  ```html
  <body>
  <select id="myselect">
      <option value="1">Option-1</option>
      <option value="2">Option-2</option>
      <option value="3">Option-3</option>
  </select>
  </body>

  Expected Output :
  "Option-2"
  ```

5. Check/uncheck a checkbox input or radio button?

  ```html
  <body>
  <form action="">
      <input type="radio" name="sex" value="male" checked>Male<br>
      <input type="radio" name="sex" value="female">Female
  </form>
  </body>
  ```

6. Write jQuery code to append a div element (and all of its contents) dynamically to the body element. Inser the following within HTML
  ```html
  <body> tag :

  <div><h1>JQuery Core</h1></div>
  ```

7. Write a jQuery Code to get a single element from a selection.

  ```html
  <body>
  <ui>
      <li>Html Tutorial</li>
      <li>Mongodb Tutorial</li>
      <li>Python Tutorial</li>
  </body>
  Sample Output : "Mongodb Tutorial"
  ```

8. Write jQuery Code to add a `<b>` tag at the beginning of the list item, containing the index of the list item.
    
    ```html
    <body>
    <ui>
        <li>Html Tutorial</li>
        <li>Mongodb Tutorial</li>
        <li>Python Tutorial</li>
    </body>
    Sample Output :
    0: Html Tutorial
    1: Mongodb Tutorial
    2: Python Tutorial
    ```

    9. Write jQuery Code to change the hyperlink and the text of a existing link.
    
    ```html
    <a href="www.w3resource.com/sqlite/" id='tut'>SQLite Tutorial</a>
    ```
    Change the hyperlink to -> www.w3resource.com/mysql/mysql-tutorials.php
    text -> MySQL Tutorial
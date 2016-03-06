# Chapter 3 选择器

## CSS 的 3 种使用方式

1. 内联样式 `Inline Styles`

    > Source code
    
    ```html
    <!-- index.html -->
    <h1 style="color: #f00;">headline...</h1>
    ```

2. 内部样式 `Internal Style Sheet`

    > Source code
    
    ```html
    <!-- index.html -->
    <head>
        <style>
            h1 {
                color: #f00;
            }
        </style>
    </head>
    <body>
    <h1>headline...</h1>
    </body>
    ```

3. 外部样式 `External Style Sheet`

    > Source code
    
    ```css
    /* style.css */
    h1 {
        color: #f00;
    }
    ```
    
    ```html
    <!-- index.html -->
    <head>
        <link href="style.css">
    </head>
    <body>
    <h1>headline...</h1>
    </body>
    ```

## CSS 选择器

- 基本选择器
    - 标记(元素/标签)选择器
    - class 选择器
    - id 选择器
- 复合选择器
    - 交集选择器
    - 并集选择器
    - 派生选择器
    
## 伪类 `pseudo-class`

- 锚点的 LoVe - HeAt
    
  - `link`
  - `visited`
  - `hover`
  - `active`
- `first-child` 
 

    
## 伪元素
  - `before`
  - `after`
  - `first-letter`
  - `first-line`



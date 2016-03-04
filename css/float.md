# Chapter 5 Float

- 标准流的概念
- 浮动改变了什么
- 图文混排的实现
- 清除浮动 `clear`
- 塌缩 `collapse` 的解决

    > Source code
    
    ```html
    <!-- index.html -->
    <div>
        <div id="d1">div1...</div>
        <div id="d2">div2...</div>
        <div id="d3">div3...</div>
        <div class="clear"></div>
    </div>    
    ```
    
    ```css
    /* style.css */
    .clear {
        clear: both;
    }
    
    #d1,
    #d2,
    #d3 {
        float: left;
    }
    ```

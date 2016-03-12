# Chapter 4 Box model 

1. box **无处不在**

2. box 的并列关系和嵌套关系


> preview

<div style="border:1px dashed #333;">
    <div style="color:#f00; text-align:center; height:50px; line-height:50px;">margin</div>
    <div style="border:1px solid #369; margin:0 50px 50px; background: #cfc;">
        <div style="color:#f00; text-align:center; height:20px; line-height:20px;">border</div>
        <div style="border:1px solid #369; margin:0 20px 20px; background:#fff">
            <div style="color:#f00; text-align:center; height:30px; line-height:30px;">padding</div>
            <div style="height:50px; color:#333; border:1px dashed #333; margin:0 30px 30px; background:#ddd;">
                content
            </div>
<br>

> Source code

```html
<!-- html -->
<div>
    content
</div>    
```

```css
div {
    background: #ddd;
    border: 20px solid #cfc;
    height: 50px;
    margin: 50px;
    pading: 30px;
}
```

- box 之间的边距
  - 并列关系 
    - 块级
    - 行内
  - 嵌套

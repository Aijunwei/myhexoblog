---
title: table-layout:fixed 解决table布局被单元格内容撑宽
keywords: table,table-layout,单元格列宽,撑开
---
最近在项目中使用table布局来实现左侧固定宽度,右侧自适应的布局;由于右侧的区域中,内容过多,导致右侧被内容撑宽,解决方案是使用table-layout:fixed

 value | des
---|---
auto | 默认。列宽度由单元格内容设定
fixed | 列宽由表格宽度和列宽度设定
inherit | 规定应该从父元素继承 table-layout 属性的值


```
<div class="table-container">
    <div class="left-content">
        left-content width=300px
    </div>
    <div class="right-content">
        <span class = "header"> 测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试测试</span>
    </div>
</div>


css
.table-container{
    display: table;
    table-layout: fixed;
    width: 50%;
    height: 500px;

}

.table-container .left-content{
    display: table-cell;
    background: #F0F8FF;
    width: 300px;
    height: 100%;
}

.table-container .right-content{
    display: table-cell;
    background: #FA8072;
    height: 100%;
}

.table-container .right-content .header{
    display: inline-block;
    width: 80%;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

```

默认使用table-layout:auto时会导致,当右侧区域内容过多时,把单元格撑大.

[运行代码](https://jsfiddle.net/aijunwei/jdynnw61/)

---
layout: post
title: "disabled、readonly、display、visibility、hidden、type=hidden详解"
description: ""
category: "html5"
tags: ["disabled", "readonly", "display", "visibility", "hidden", "type=hidden"]
---
{% include JB/setup %}
##一、disabled
- 1、disabled只对所有的表单元素有效，对其他元素无效（例如contenteditable的div）。
- 2、disabled的表单元素不会被提交。
- 3、设置disabled方法：
    - 表单：disabled="disabled"或disabled="true"或disabled
    - jquery： attr("disabled", "disabled")或 attr("disabled", true)或 prop("disabled", true)。
    - 推荐方法：因为disabled可以认为是布尔值（只有true和false）。所以表单用disabled="true"，jquery用prop("disabled", true)。

##二、readonly
- 1、readonly只对input(text/password)或者textarea有效, 其他元素无效（包括非表单的contenteditable的div）。
- 2、readonly的表单元素会被提交。
- 3、设置readonly方法：
    - 表单：readonly="readonly"或readonly="true"或readonly
    - jquery： attr("readonly", "readonly")或 attr("readonly", true)或 prop("readonly", true)。
    - 推荐方法：因为readonly可以认为是布尔值（只有true和false）。所以表单用readonly="true"，jquery用prop("readonly", true)。

##三、type=hidden
- 1、type="hidden"：对input有效对textarea无效。(应该只对input有效）
- 2、隐藏input但保留空间，会被提交。（除非有disabled属性)

##四、display:none、visibility:hidden、hidden=true

### "display:xxx"
- 1、display:none 元素被隐藏，保留页面代码，不保留物理空间，如果是表单则依然会被提交。
- 2、jquery显示被display:none的元素：css("display", "block")或css("display", "inline")等。（看css的关于display的定义，根据实际情况）

### "visibility:xxx"
- 1、visibility:hidden 元素被隐藏，保留页面代码，保留物理空间，如果是表单则依然会被提交。
- 2、jquery显示被visibility:hidden的元素：css("visibility", "visible")等。（看css的关于display的定义，根据实际情况）

### 标签hidden属性
- 1、html5新增的属性，效果同display:none。
- 2、jquery显示被hidden=true的元素：prop("hidden", false)

#dom = htmlDom + xmlDom + coreDom
   > ####htmlDom:是规范ECMAScript对html节点(文档节点、元素节点、文本节点、属性节点、注释节点)CURD的标准

###1、节点关系：
    根root、父parent、子child、兄弟或同胞sibling
###2、编程接口：
    所有 HTML 元素被定义为对象，而编程接口则是对象方法和对象属性。
###3、对象：
-   Document: 每个载入浏览器的 HTML 文档都会成为 Document 对象。 Document 对象是 Window 对象的一部分，可通过 window.document 属性对其进行访问。
    - 对象集合：all[] 、anchors[] 、applets 、forms[] 、images[] 、links[]
    - 属性： body 、cookie 、domain 、lastModified 、referrer 、title 、URL
    - 方法： close() 、getElementById() 、getElementsByName() 、getElementsByTagName() 、open() 、write() 、writeln()

-   Event: Event对象代表事件的状态，比如事件在其中发生的元素、键盘按键的状态、鼠标的位置、鼠标按钮的状态。
    - 事件句柄：onabort 、onblur 、onchange 、onclick 、ondblclick 、onerror 、onfocus 、onkeydown 、onkeypress 、onkeyup 、onload 、onmousedown 、onmousemove 、onmouseout 、onmouseover 、onmouseup 、onreset 、onresize 、onselect 、onsubmit 、onunload
    - 属性：altKey 、button 、clientX 、clientY 、ctrlKey 、metaKey 、relatedTarget 、screenX 、screenY 、shiftKey

-   其他对象：
    - Anchor 、Area 、Base 、Body 、Button 、Canvas 、Form 、Frame 、Frameset 、IFrame 、Image 、Input Button 
      Input Checkbox 、Input File、Input Hidden 、Input Password 、Input Radio 、Input Reset 、Input Submit 、Input Text
      Link 、Meta 、Object 、Option 、Select 、Style、Table 、TableCell 、TableRow 、Textarea 

###4、常用属性：
   - innerHTML 属性可用于获取或改变任意 HTML 元素，包括 <html> 和 <body>。
   - nodeName  \*nodeName是只读的 \*元素节点的nodeName与标签名相同 \*属性节点的nodeName与属性名相同 \*文本节点的nodeName始终是 #text \*文档节点的nodeName始终是 #document 
   - nodeValue \*元素节点的nodeValue是undefined或null \*文本节点的nodeValue是文本本身 \*属性节点的nodeValue是属性值
   - nodeType  \*nodeType是只读的 \*元素1 \*属性2 \*文本3 \*注释8 \*文档9
  
###5、常用方法：
   - getElementById()         返回带有指定 ID 的元素。
   - getElementsByTagName()   返回包含带有指定标签名称的所有元素的节点列表（集合/节点数组）。
   - getElementsByClassName() 返回包含带有指定类名的所有元素的节点列表。 IE5,6,7,8 中无效。
   - appendChild()            把新的子节点添加到指定节点。
   - removeChild()            删除子节点。
   - replaceChild()           替换子节点。
   - insertBefore()           在指定的子节点前面插入新的子节点。
   - createAttribute()        创建属性节点。
   - createElement()          创建元素节点。
   - createTextNode()         创建文本节点。
   - getAttribute()           返回指定的属性值。
   - setAttribute()           把指定属性设置或修改为指定的值。

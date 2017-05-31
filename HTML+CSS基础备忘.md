#### `HTML`

* `<!--注释语句-->`注释
* `<body>`内容
* `<p>`段落
* `<hx>`标题
* `<strong>`粗体 
* `<em>`斜体
* `<span>`无语义
* `<q>`短文本引用
* `<blockquote>`长文本引用
* `<br>`换行
* `&nbsp;`空格
* `<hr>`水平横线
* `<address>`地址
* `<code>`代码 
* `<pre>`多行代码
* `<ul>`无序列 
* `<ol>`有序列 
* `<li>`列元素
* `<div>`层
* `<table>`表格 
 * `<tbody>`逐渐显示 
 * `<tr>`行 
 * `<td>`列 
 * `<th>`表头 
 * `<summary>`摘要 
 * `<caption>`标题
* `<a>`链接 例:`<a href="www.xxx.com" title="跳转链接" target="_blank">点击跳转链接</a>`
* `mailto`链接邮件 例:`<a href="mailto:user1@xxx.com?cc=user2@xxx.com&bcc=user3@xxx.com&subject=title&body=content">点击发送邮件</a>`
* `<img>`图片 例:`<img src="xxx.jpg" alt="加载失败时会显示" title="鼠标划过时会显示"/>`
* `<form>`表单 例:`<form method="post" action="save.php">...</form>`  
* `<input>`输入框 
 * `name`控件名称 
 * `value`提交到服务器的值
 * `type="text"`文本输入框
 * `type="password"`密码输入框
 * `type="radio"`单选框
 * `type="checkbox"`复选框
 * 当`type="radio/checkbox"`时 一组控件名称要一致 `checked="checked"`被选中
 * `type="submit"`提交按钮(`value`按钮上显示的文字)
 * `type="reset"`重置按钮(`value`按钮上显示的文字)
* `<textarea>`文本域 例:`<textarea rows="行数" cols="列数">文本</textarea>`
* `<select>`下拉列表框
 * `multiple="mulpitle"`多选 
 * `option`选项
 * `selected="selected"`已选中  
* `<label>`显示标签 `for="控件id名称"`关联的控件

#### `CSS`

* `/*注释语句*/`注释
* `选择器{css样式;}`
 * 标签选择器 `标签名称{css样式;}`
 * 类选择器 `.类名称{css样式;}`
 * `ID`选择器 `#ID名称{css样式;}`
 * 子选择器 使用`>`选择指定标签元素的第一代子元素 例:`.类名称>标签名称{css样式;}`
 * 包含(后代)选择器 使用空格选择指定标签元素下的后辈元素 例:`.类名称 标签名称{css样式;}`
 * 通用选择器 使用`*`匹配`HTML`中所有标签元素 例:`*{css样式;}`
 * 伪类选择符 允许给`HTML`不存在的标签（标签的某种状态）设置样式 例:`a:hover{color:red;} (为a标签鼠标滑过的状态设置字体颜色变红)`
 * 分组选择符 为多个标签元素设置同一个样式 例:`标签名称1,标签名称2{css样式;}`
* `类和ID选择器的区别`
 * `ID`选择器只能在文档中使用一次
 * 可以使用类选择器词列表方法为一个元素同时设置多个样式 例:`<span class="class1 class2">...</span>`
* `内联式css样式` 把`css`代码直接写在现有的`HTML`标签中 例:`<p style="color:red">这里文字是红色。</p>`
* `嵌入式css样式` 把`css`代码写在`<style type="text/css"></style>`标签之间 并且一般情况下写在`<head></head>`之间 例:`<style type="text/css">span{color:red;}</style>`
* `外部式css样式` 把`css`代码写一个单独的外部文件中，这个`css`样式文件以`“.css”`为扩展名，在`<head>`内（不是在`<style>`标签内）使用`<link>`标签将`css`样式文件链接到`HTML`文件内 例:`<link href="base.css" rel="stylesheet" type="text/css" />`
* `样式优先级` 内联式 > 嵌入式 > 外部式 就近原则（离被设置元素越近优先级别越高）
* `继承` 样式不仅应用于某个特定标签元素 而且应用于其后代 有一些样式不具有继承性
* `权值` 权值高则样式优先级高
 * 继承的权值最低 (`0.1`)
 * 标签的权值为`1`
 * 类选择符的权值为`10`
 * `ID`选择符的权值最高为`100`
 * `!important`权值最高 例:`p{color:red!important;}`
 * 权值相同时 最后一个样式会被应用
* `文字排版`
 * `font-family`字体
 * `font-size`字号
 * `color`颜色
 * `font-weight:bold`粗体
 * `font-style:italic`斜体
 * `text-decoration:underline`下划线
 * `text-decoration:line-through`删除线
 * `text-indent`缩进
 * `line-height`行间距/行高
 * `letter-spacing/word-spacing`字间距/词间距
 * `text-align`对齐方式
* `块状元素`
 * 每个块级元素都从新的一行开始 并且其后的元素也另起一行
 * 元素的高度、宽度、行高以及顶和底边距都可设置
 * 元素宽度在不设置的情况下 是它本身父容器的`100%`（和父元素的宽度一致）
 * `display:block`将元素显示为块级元素
 * `常用的块状元素` `<div>` `<p>` `<hx>` `<ol>` `<ul>` `<dl>` `<table>` `<address>` `<blockquote>` `<form>`
* `内联元素`
 * 和其他元素都在一行上
 * 元素的高度、宽度及顶部和底部边距不可设置
 * 元素的宽度就是它包含的文字或图片的宽度 不可改变
 * `display:inline`将元素设置为内联元素
 * `常用的内联元素` `<a>` `<span>` `<br>` `<i>` `<em>` `<strong>` `<label>` `<q>` `<var>` `<cite>` `<code>`
* `内联块状元素` 
 * 和其他元素都在一行上
 * 元素的高度、宽度、行高以及顶和底边距都可设置
 * `display:inline-block`将元素设置为内联块状元素
 * `常用的内联块状元素` `<img>` `<input>`
* `盒模型`
 * `border-width`边框宽度 `1px` `thin` `medium` `thick`
 * `border-style`边框样式 `dashed` `dotted` `solid`
 * `border-color`边框颜色
 * `border-top/right/bottom/left`单独为某个方向设置边框
 * 边框样式简写实例:`div{border-top:1px  solid  red;}`
 * `元素实际宽度（盒子的宽度）`=左边界+左边框+左填充+内容宽度+右填充+右边框+右边界
 * `元素实际高度（盒子的高度）计算方式与宽度类似`
 * `padding(-top/right/bottom/left)`填充
 * `margin(-top/right/bottom/left)`边界
 * `padding`与`margin`的区别在于`padding`在边框里而`margin`在边框外
* `布局模型`
 * `Flow`流动模型 从上到下 从左到右
 * `Float`浮动模型 `float`属性实现浮动
 * `Layer`层模型 `position:absolute/relative/fixed`绝对定位/相对定位/固定定位
 * 参照前辈元素定位 需要对被参照的元素设置`position:relative;` 然后对需要定位的元素设置`position:absolute;`
* `颜色设置方式`
 * `color:red;`
 * `color:rgb(133,45,200);`
 * `color:rgb(20%,33%,25%);`
 * `color:#00ffff;`
* `水平居中设置`
 * 行内元素`text-align:center;`
 * 定宽块状元素`margin:20px auto;`
 * 不定宽块状元素`1.加入table标签` `2.改变块级元素的display为inline类型 再参照行内元素设置` `3.通过给父元素设置float 然后给父元素设置position:relative和left:50% 子元素设置position:relative和left:-50%`
* `垂直居中设置`
 * 父元素高度确定的单行文本`设置父元素的height和line-height高度一致`
 * 父元素高度确定的多行文本`1.使用插入table (包括tbody、tr、td)标签 同时设置vertical-align：middle` `2.在chrome、firefox及IE8以上的浏览器下可以设置块级元素的display为table-cell（设置为表格单元显示）激活vertical-align属性`
* `隐性改变display类型（自动变为display:inline-block）`
 * `position:absolute`
 * `float:left 或 float:right`

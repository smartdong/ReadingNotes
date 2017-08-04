* `alert(字符串或变量)` 弹出提示框
* `confirm(提示字符串)` 弹出确认框，返回`Boolean`值
* `prompt(要显示在消息对话框中的文本, 文本框中的内容)` 弹出对话框，点击取消按钮将返回`null`点击确定按钮返回文本框中的内容
* `window.open([URL], [窗口名称], [参数字符串])` 查找一个已经存在或者新建的浏览器窗口
    * `URL` 可选参数，在窗口中要显示网页的网址或路径。如果省略这个参数，或者它的值是空字符串，那么窗口就不显示任何文档
    * 窗口名称：可选参数，被打开窗口的名称
        * 该名称由字母、数字和下划线字符组成
        * 具有特殊意义的名称
            * `_blank` 在新窗口显示目标网页
            * `_self` 在当前窗口显示目标网页
            * `_top` 框架网页中在上部窗口中显示目标网页
        * 相同`name`的窗口只能创建一个，要想创建多个窗口则`name`不能相同
        * `name`不能包含有空格
    * 参数字符串：可选参数，设置窗口参数，各参数用逗号隔开
* `window.close()` 关闭本窗口
* `<窗口对象>.close()` 关闭指定的窗口
* `document.getElementById("id")` 通过`id`获取元素
* `innerHTML` 属性用于获取或替换`HTML`元素的内容
* `document.getElementById("id").style.property = style` 更改样式
* 控件事件
    * `onclick` 鼠标单击
    * `onmouseover` 鼠标经过
    * `onmouseout` 鼠标移开
    * `onfocus` 光标聚集
    * `onblur` 失焦
    * `onselect` 内容选中
    * `onchange` 内容改变
    * `onload` 加载
    * `onunload` 卸载
* `Array` 方法
    * `concat` 连接数据并返回结果
    * `join` 把所有元素放入字符串，通过指定分隔符分隔
    * `pop` 删除并返回数组的最后一个元素
    * `push` 向数组的末尾添加更多元素，并返回新的长度
    * `reverse` 颠倒数组中元素的顺序
    * `shift` 删除并返回数组的第一个元素
    * `slice` 从已有的数组返回选定的元素
    * `sort` 对数组的元素进行排序
    * `splice` 删除元素，并向数组添加新元素
    * `toSource` 返回该对象的源代码
    * `toString` 把数组转为字符串，并返回结果
    * `toLocaleString` 把数组转为本地数组，并返回结果
    * `unshift` 向数组的开头添加元素，并返回新的长度
    * `valueOf` 数组对象的原始值
* `window` 方法
    * `alert` 显示带有一段消息和一个确认按钮的警告框
    * `prompt` 显示可提示用户输入的对话框
    * `confirm` 显示带有一段消息以及确认按钮和取消按钮的对话框
    * `open` 打开一个新的浏览器窗口或查找一个已命名的窗口
    * `close` 关闭浏览器窗口
    * `print` 打印当前窗口的内容
    * `focus` 把键盘焦点给予一个窗口
    * `blur` 把键盘焦点从顶层窗口移开
    * `moveBy` 相对窗口的当前坐标移动指定的像素
    * `moveTo` 把窗口的左上角移动到一个指定的坐标
    * `resizeBy` 相对当前的窗口大小调整大小
    * `resizeTo` 将窗口调整到指定大小
    * `scrollBy` 滚动指定像素
    * `scrollTo` 滚动到指定坐标
    * `setInterval` 每隔指定时间执行代码
    * `setTimeout` 延迟指定时间执行代码
    * `clearInterval` 取消 `setInterval`
    * `clearTimeout` 取消 `setTimeout`
* `location`
    * 属性
        * `hash` 从 `#` 以后开始的 `URL`
        * `host` 主机名和端口号
        * `hostname` 主机名
        * `href` 完整 `URL`
        * `pathname` `URL` 的路径部分
        * `port` 端口号
        * `protocol` 协议
        * `search` 参数部分
    * 方法
        * `assign` 加载新的文档
        * `reload` 重新加载当前文档
        * `replace` 用新的文档替换当前文档
* `navigator` 属性
    * `appCodeName` 浏览器代码名的字符串
    * `appName` 浏览器名称
    * `appVersion` 浏览器的平台和版本信息
    * `platform` 运行浏览器的操作系统平台
    * `userAgent` 客户端发送服务器的 `user-agent` 头部
* `window.screen` 属性
    * `availHeight` 窗口可以使用的屏幕高度，单位像素
    * `availWidth` 窗口可以使用的屏幕宽度，单位像素
    * `colorDepth` 颜色位数
    * `pixelDepth` 颜色位数（`IE`不支持）
    * `height` 屏幕高度，单位像素
    * `width` 屏幕宽度，单位像素
* `DOM` 
    * 属性
        * `nodeName` 节点名字
        * `nodeType` 节点类型
        * `nodeValue` 节点当前值
    * 方法
        * `childNodes` 所有子节点
        * `firstChild` 第一个子节点
        * `lastChild` 最后一个子节点
        * `parentNode` 父节点
        * `nextSibling` 指定节点的下一个子节点
        * `previousSibling` 指定节点的前一个子节点
        * `createElement` 创建一个新节点
        * `createTextNode` 创建一个包含指定文本的新文本节点
        * `appendChild` 在子节点列表后添加一个子节点
        * `insertBefore` 将子节点添加到指定子节点前
        * `removeChild` 删除子节点
        * `replaceChild` 替换子节点
* 区域大小
    * 可视区域
        * 宽度 `var w = document.documentElement.clientWidth || document.body.clientWidth;`
        * 高度 `var h = document.documentElement.clientHeight || document.body.clientHeight;`
    * 网页内容
        * 宽度 `var w = document.documentElement.scrollWidth || document.body.scrollWidth;`
        * 高度 `var h = document.documentElement.scrollHeight || document.body.scrollHeight;`
    * 网页尺寸
        * 宽度 `var w = document.documentElement.offsetWidth || document.body.offsetWidth;`
        * 高度 `var h = document.documentElement.offsetHeight || document.body.offsetHeight;`
    * 偏移量
        * `scrollLeft` 左边滚出屏幕的宽度
        * `scrollTop` 上边滚出屏幕的高度
        * `offsetLeft` 获取指定对象相对于版面或由 `offsetParent` 属性指定的父坐标的计算左侧位置
        * `offsetTop` 获取指定对象相对于版面或由 `offsetParent` 属性指定的父坐标的计算顶端位置

##### 基础

* `DOM` 对象转化成 `jQuery` 对象
    * `$div = $(document.getElementsByTagName('div'))`
* `jQuery` 对象转化成 `DOM` 对象
    * `var div = $('div')[0]`

##### 样式

* 选择器
    * `id` 选择器
        * `$("#id")`
    * 类选择器
        * `$(".class")`
    * 元素选择器
        * `$("element")`
    * 全选择器
        * `$("*")`
    * 层级选择器
        * `$("parent > child")` 子选择器 直接子元素
        * `$("ancestor descendant")` 后代选择器 所有后代
        * `$("prev + next")` 相邻兄弟选择器 某种元素后面紧邻的某种元素
        * `$("prev ~ siblings")` 一般兄弟选择器 某种元素后面的某种兄弟元素
    * 基本筛选选择器
        * `$(":first")` 第一个元素
        * `$(":last")` 最后一个元素
        * `$(":not(selector)")` 没有相关方法的所有元素
        * `$(":eq(index)")` 索引值为 `index` 的元素
        * `$(":gt(index)")` 索引值大于 `index` 的元素
        * `$(":lt(index)")` 索引值小于 `index` 的元素
        * `$(":even")` 索引值为偶数的元素 从 `0` 开始
        * `$(":odd")` 索引值为奇数的元素 从 `0` 开始
        * `$(":header")` 所有标题元素
        * `$(":lang(language)")` 指定语言的所有元素
        * `$(":root")` 该文档的根元素
        * `$(":animated")` 所有正在执行动画效果的元素
    * 内容筛选选择器
        * `$(":contains(text)")` 所有包含指定文本的元素
        * `$(":parent")` 所有含有子元素或者文本的元素
        * `$(":empty")` 所有没有子元素的元素 包括文本节点
        * `$(":has(selector)")` 有相关方法的所有元素
    * 可见性筛选选择器 
        * `$(":visible")` 所有显示的元素
        * `$(":hidden")` 所有隐藏的元素
    * 属性筛选选择器
        * `$("[attribute|='value']")` 指定属性的值为唯一值`-`或字符串开头后面带`-`(这个字符串的值必须为第一个值)
        * `$("[attribute*='value']")` 指定属性的值包含某个固定字符串
        * `$("[attribute~='value']")` 指定属性的值包含某个固定值
        * `$("[attribute='value']")` 指定属性名和值
        * `$("[attribute!='value']")` 指定属性的值不包含某个固定字符串
        * `$("[attribute^='value']")` 指定属性的值以某个固定字符串开头
        * `$("[attribute$='value']")` 指定属性的值以某个固定字符串结尾
        * `$("[attribute]")` 指定属性名
        * `$("[attributeFilter1][attributeFilterN]")` 指定匹配所有属性选择器的元素
    * 元素筛选选择器
        * `$(":first-child")` 所有父元素下的第一个子元素
        * `$(":last-child")` 所有父元素下的最后一个子元素
        * `$(":only-child")` 如果某个元素是其父元素的唯一子元素 则会被选中
        * `$(":nth-child")` 所有父元素下的第n个子元素
        * `$(":nth-last-child")` 所有父元素下的倒数第n个子元素
    * 表单元素选择器
        * `$(":input")` 所有 `input` `textarea` `select` `button` 元素
        * `$(":text")` 所有文本框
        * `$(":password")` 所有密码框
        * `$(":radio")` 所有单选按钮
        * `$(":checkbox")` 所有复选框
        * `$(":submit")` 所有提交按钮
        * `$(":image")` 所有图像域
        * `$(":reset")` 所有重置按钮
        * `$(":button")` 所有按钮
        * `$(":file")` 所有文件域
    * 表单对象属性筛选选择器 
        * `$(":enabled")` 所有可用的表单元素
        * `$(":disabled")` 所有不可用的表单元素
        * `$(":checked")` 所有被选中的 `input` 元素
        * `$(":selected")` 所有被选中的 `option` 元素
    * 特殊选择器 `this`
        * `$("this")` 当前的 `jQuery` 上下文对象
* 属性与样式
    * `attr()` 与 `removeAttr()`
        * `attr("key")` 获取属性值
        * `attr("key","value")` 设置属性值
        * `attr("key",function(){})` 设置属性函数值
        * `attr({"key":"value","key":"value"})` 设置多个属性值
        * `removeAttr("key")` 移除属性
    * `html()` 及 `text()`
        * `html()` 获取集合中第一个匹配元素的 `HTML` 内容或设置每一个匹配元素的 `HTML` 内容
        * `text()` 获取匹配元素集合中每个元素的文本内容结合（包括他们的后代）或设置匹配元素集合中每个元素的文本内容为指定的文本内容
        * 不传入值为获取 传入值为设置
        * 异同
            * `html` 与 `text` 的方法操作一样 只是在具体针对处理对象不同
            * `html` 处理的是元素内容 ; `text` 处理的是文本内容
            * `html` 只能使用在 `HTML` 文档中 ; `text` 在 `XML` 和 `HTML` 文档中都能使用
            * 如果处理的对象只有一个子文本节点 那么 `html` 处理的结果与 `text` 是一样的
            * 火狐不支持 `innerText` 属性 用了类似的 `textContent` 属性 ; `text()` 方法综合了2个属性的支持 所以可以兼容所有浏览器
    * `val()`
        * `val()` 获取匹配的元素集合中第一个元素的当前值
        * `val("value")` 设置匹配的元素集合中每个元素的值
        * `val(function)` 一个用来返回设置值的函数
        * `html()` `text()` `val()` 差异总结
            * 三种方法都是用来读取选定元素的内容；只不过 `html()` 是用来读取元素的
 `html` 内容（包括 `html` 标签），`text()` 用来读取元素的纯文本内容，包括其后代元素，`val()` 是用来读取表单元素的 `"value"` 值。其中 `html()` 和 `text()` 方法不能使用在表单元素上,而 `val()` 只能使用在表单元素上；另外 `html()` 方法使用在多个元素上时，只读取第一个元素；`val()` 方法和 `html()` 相同，如果其应用在多个元素上时，只能读取第一个表单元素的 `"value"` 值，但是 `text()` 和他们不一样，如果 `text()` 应用在多个元素上时，将会读取所有选中元素的文本内容
            * `html(htmlString)` `text(textString)` 和 `val(value)` 三种方法都是用来替换选中元素的内容，如果三个方法同时运用在多个元素上时，那么将会替换所有选中元素的内容
            * `html()` `text()` `val()` 都可以使用回调函数的返回值来动态的改变多个元素的内容
    * `addClass()`
        * `addClass("className")` 为每个匹配元素所要增加的一个或多个样式名
        * `addClass(function(index, currentClass))` 这个函数返回一个或更多用空格隔开的要增加的样式名
        * `addClass()` 方法不会替换一个样式类名 它只是简单的添加一个样式类名到元素上
    * `removeClass()`
        * `removeClass("className")` 每个匹配元素移除的一个或多个用空格隔开的样式名
        * `removeClass(function(index, class))` 一个函数 返回一个或多个将要被移除的样式名
        * 如果一个样式类名作为一个参数 只有这个样式类会被从匹配的元素集合中删除 如果没有样式名作为参数 那么所有的样式类将被移除
    * `toggleClass()`
        * `toggleClass("className")` 在匹配的元素集合中的每个元素上用来切换的一个或多个（用空格隔开）样式类名
        * `toggleClass("className", switch)` 一个布尔值 用于判断样式是否应该被添加或移除
        * `toggleClass([switch])` 一个用来判断样式类添加还是移除的布尔值
        * `toggleClass(function(index, class, switch) [,switch])` 用来返回在匹配的元素集合中的每个元素上用来切换的样式类名的一个函数 接收元素的索引位置和元素旧的样式类作为参数
        * `toggleClass` 是一个互斥的逻辑 也就是通过判断对应的元素上是否存在指定的
 `Class` 名 如果有就删除 如果没有就增加
        * `toggleClass` 会保留原有的 `Class` 名后新增 通过空格隔开
    * `css()`
        * `css("propertyName")` 获取匹配元素集合中的第一个元素的样式属性的计算值
        * `css("propertyNames")` 传递一组数组 返回一个对象结果
    * `css()` 与 `addClass()` 设置样式的区别
        * 可维护性
            * `addClass()` 的本质是通过定义个 `class` 类的样式规则，给元素添加一个或多个类。`css` 方法是通过 `JavaScript` 大量代码进行改变元素的样式
            * 通过 `addClass()` 我们可以批量的给相同的元素设置统一规则，变动起来比较方便，可以统一修改删除。如果通过 `css()` 方法就需要指定每一个元素是一一的修改，日后维护也要一一的修改，比较麻烦
        * 灵活性
            * 通过 `css()` 方式可以很容易动态的去改变一个样式的属性，不需要在去繁琐的定义个 `class` 类的规则。一般来说在不确定开始布局规则，通过动态生成的 `HTML` 代码结构中，都是通过 `css()` 方法处理的
        * 样式值
            * `addClass()` 本质只是针对 `class` 的类的增加删除，不能获取到指定样式的属性的值，`css()` 可以获取到指定的样式值
        * 样式的优先级
            * `css` 的样式是有优先级的，当外部样式、内部样式和内联样式同一样式规则同时应用于同一个元素的时候，优先级如下 : `外部样式 < 内部样式 < 内联样式`
            * `addClass()` 方法是通过增加 `class` 名的方式，那么这个样式是在外部文件或者内部样式中先定义好的，等到需要的时候在附加到元素上
            * 通过 `css()` 方法处理的是内联样式，直接通过元素的 `style` 属性附加到元素上的
            * 通过 `css` 方法设置的样式属性优先级要高于 `addClass` 方法
        * 总结
            * `addClass` 与 `css` 方法各有利弊，一般是静态的结构，都确定了布局的规则，可以用 `addClass` 的方法，增加统一的类规则
            * 如果是动态的 `HTML` 结构，在不确定规则，或者经常变化的情况下，一般多考虑 `css()` 方式
    * 元素的数据存储
        * `jQuery.data(element, key, value)` 静态接口 存数据
        * `jQuery.data(element, key)` 静态接口 取数据
        * `data(key, value)` 实例接口 存数据
        * `data(key)` 实例接口 取数据
        * `jQuery.removeData(element [, name ])` 静态接口 删除数据
        * `removeData([name])` 实例接口 删除数据

##### DOM

* `DOM` 节点的创建
    * `$("html结构")`
* `DOM` 节点的插入
    * `append()` 向匹配的元素内部追加内容
    * `appendTo()` 将内容追加到匹配的元素中
    * `after()` 在匹配的元素后追加兄弟内容
    * `before()` 在匹配的元素前追加兄弟内容
    * `prepend()` 在匹配的元素内部前置内容
    * `prependTo()` 将内容前置到匹配的元素内部
    * `insertAfter()` 将兄弟内容追加到匹配的元素后
    * `insertBefore()` 将兄弟内容追加到匹配的元素前
* `DOM` 节点的删除
    * `empty()` 移除指定元素中的所有子节点
    * `remove()` 移除指定元素及其所有子节点 若指定参数 则只移除符合条件的内容
    * `detach()` 从页面上移除元素 但是还存在内存中
* `DOM` 节点的复制与替换
    * `clone()` 复制所有的内容 参数若为 `true` 则同时复制事件与数据
    * `replaceWith()` 用提供的内容替换集合中所有匹配的元素并且返回被删除元素的集合
    * `replaceAll()` 用集合的匹配元素替换每个目标元素
    * `wrap()` 在集合中匹配的每个元素周围包裹一个 `HTML` 结构
    * `unwrap()` 在集合中匹配的每个元素周围删除一个 `HTML` 结构
    * `wrapAll()` 给集合中匹配的元素增加一个外面包裹 `HTML` 结构
    * `wrapInner()` 给集合中匹配的元素的内部增加包裹的 `HTML` 结构
* `jQuery` 遍历
    * `children()` 所有直接子元素
    * `find()` 符合条件的子元素
    * `parent()` 父元素
    * `parents()` 所有祖先元素
    * `closest()` 符合条件的最近的祖先元素
    * `next()` 紧邻的下一个兄弟元素
    * `prev()` 紧邻的前一个兄弟元素
    * `siblings()` 所有兄弟元素
    * `add()` 将元素追加到匹配元素集合中
    * `each()` 遍历元素

##### 事件

* 鼠标事件
    * `click()` 单击
    * `dblclick()` 双击
    * `mousedown()` 按下
    * `mouseup()` 抬起
    * `mousemove()` 移动
    * `mouseover()` 移入（会传递事件）
    * `mouseout()` 移出（会传递事件）
    * `mouseenter()` 移入（不会传递事件）
    * `mouseleave()` 移出（不会传递事件）
    * `hover()` `mouseenter()` 和 `mouseleave()` 的结合
    * `focusin()` 获得焦点（会传递事件）
    * `focusout()` 失去焦点（会传递事件）
* 表单事件
    * `blur()` 失去焦点（不会传递事件）
    * `focus()` 获得焦点（不会传递事件）
    * `change()` 值改变并失去焦点
    * `select()` 文本被选择
    * `submit()` 提交表单（需要阻止默认事件：`return false`）
* 键盘事件
    * `keydown()` 按键按下
    * `keyup()` 按键抬起
    * `keypress()` `keydown()`后触发 能接收刚按下的字符（主要用来接收字母、数字）
* 事件的绑定与解绑
    * `on()` 绑定事件
    * `off()` 删除事件
* 事件对象的使用
    * `event.target` 代表当前触发事件的元素 可以通过当前元素对象的一系列属性来判断是不是我们想要的元素
    * `event.type` 获取事件的类型
    * `event.pageX` 获取鼠标当前相对于页面的 `X` 坐标
    * `event.pageY` 获取鼠标当前相对于页面的 `Y` 坐标
    * `event.preventDefault()` 阻止默认行为
    * `event.stopPropagation()` 阻止事件冒泡
    * `event.which` 获取在鼠标单击时 单击的是鼠标的哪个键
    * `event.currentTarget` 在事件冒泡过程中的当前元素
* 自定义事件
    * `trigger()` 调用相关事件
    * `triggerHandler()` 调用相关事件 不传递事件 不触发默认事件

##### 动画

* 动画基础隐藏和显示
    * `hide()` 隐藏
    * `show()` 显示
    * `toggle()` 切换隐藏显示
* 上卷下拉效果
    * `slideDown()` 下拉
    * `slideUp()` 上拉
    * `slideToggle()` 切换下拉上拉
* 淡入淡出效果
    * `fadeOut()` 淡出
    * `fadeIn()` 淡入
    * `fadeToggle()` 切换淡出淡入
    * `fadeTo()` 设置透明度
* 自定义动画
    * `animate()` 执行动画
    * `stop()` 停止动画
        * `stop()` 只会停止第一个动画 其他继续
        * `stop(true)` 停止所有动画
        * `stop(true,ture)` 停止动画并直接跳到第一个动画的最终状态 
* `jQuery` 核心
    * `each()` 遍历 `jQuery` 对象
    * `inArray()` 判断元素是否存在数组中
    * `trim()` 去除字符串两端的空白字符
    * `get()` 单独获取合集中的的某一个元素
    * `index()` 从匹配的元素中搜索给定元素的索引值

######第一章 `HTTP`概述
1.`URI`和`URL`

* `URI（Uniform Resource Identifier`）统一资源标识符，在世界范围内唯一标识并定位信息资源。`URI`有两种形式，分别称为`URL`和`URN`
* `URL` 统一资源定位符，描述了一台特定服务器上某资源的特定位置，现在几乎所有`URI`都是`URL`
* `URN` 统一资源名，作为特定内容的唯一名称使用，与目前的资源所在地无关（仍处于试验阶段）

2.常见`HTTP`方法

* `GET` 从服务器向客户端发送命名资源
* `PUT` 将来自客户端的数据存储到一个命名的服务器资源中去
* `DELETE` 从服务器中删除命名资源
* `POST` 将客户端数据发送到一个服务器网关应用程序
* `HEAD` 仅发送命名资源响应中的`HTTP`首部

######第二章 `URL`与资源

1.`URL`组成

* `URL`的第一部分（`http`）是`URL`方案（`scheme`），方案可以告知`Web`客户端怎样访问资源
* `URL`的第二部分（`www.xxx.com`）指的是服务器位置，这部分告知`Web`客户端资源位于何处
* `URL`的第三部分（`/xxx/xxx.html`）是资源路径，路径说明了请求的是服务器上哪个特定的本地资源

2.`URL`的语法  
`<scheme>://<user>:<password>@<host>:<port>/<path>;<params>?<query>#<frag>`

######第三章 `HTTP`报文 

1.报文的组成部分

* 对报文进行描述的起始行（`start line`）
* 包含属性的首部（`header`）块
* 可选的、包含数据的主体（`body`）部分

2.报文的语法

* 请求报文的格式  
  `<method> <request url> <version>`  
  `<headers>`  
  `<entity-body>`
* 响应报文的格式（只有起始行的语法有所不同）  
  `<version> <status> <reason-phrase>`  
  `<headers>`  
  `<entity-body>`

3.状态码

* `100~199` 信息性状态码
 * `100 Continue` 说明收到了请求的初始部分，请客户端继续。发送了这个状态码之后，服务端在收到请求之后必须进行响应
 * `101 Switching Protocols` 说明服务器正在根据客户端的指定，将协议切换成`Update`首部所列的协议
* `200~299` 成功状态码
 * `200 OK` 请求没问题，实体的主体部分包含了所请求的资源
 * `201 Created` 用于创建服务器对象的请求，响应的实体主体部分中应该包含各种引用了已创建的资源的`URL`，`location`首部包含的则是最具体的引用
 * `202 Accepted` 请求已被接受，但服务器还未对其执行任何动作，不能保证服务器会完成这个请求
 * `203 Non-Authoritative Infomation` 实体首部包含的信息不是来自于源端服务器，而是来自资源的一份副本
 * `204 No Content` 响应报文中包含若干首部和一个状态行，但没有实体的主体部分。主要用于在浏览器不转为显示新文档的情况下，对其进行更新
 * `205 Reset Content` 另一个主要用于浏览器的代码，负责告知浏览器清除当前页面中的所有`HTML`表单元素
 * `206 Partial Content` 成功执行了一个部分或`Range（范围）`请求，`206`响应中必须包含`Content-Range`、`Date`以及`ETag`或`Content-Location`首部

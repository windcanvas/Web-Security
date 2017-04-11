# Web-Security
关于Web安全的一些知识总结

# Web安全-XSS
- 具备JavaScript开发能力

- 了解HTTP，Cookie，Ajax等基本常识
## XSS的定义

### XSS的攻击方式

- 反射型

发出请求时，XSS代码出现在URL中，作为输入提交到服务器端，服务器端解析后响应，XSS代码随响应内容一起传回给浏览器，最后浏览器解析执行XSS代码。这个过程像一次反射，故叫反射型XSS。

- 储存型

存储型XSS和反射型XSS的差别仅在于，提交的代码会存储在服务器端（数据库，内存，文件系统等），下次请求目标页面时不用再提交XSS代码。

## XSS的防御措施

- 编码

对用户输入的数据进行HTML Entity编码

![11111.png](https://ooo.0o0.ooo/2017/04/11/58ec7e7a7975b.png)

- 过滤

  - 移除用户上传的DOM属性，如onerror等
  - 移除用户上传的Style节点，Script节点，Iframe节点等
- 校正
  - 避免直接对HTML Entity解码
  - 使用DOM Parse转换，校正不配对的DOM标签
  
##   实战

通过构建Node服务和建立一个评论功能，实例演示XSS的攻击及预防

### XSS的防范措施

- 反转义，DOM Parse
- 过滤，校正

# script标签有哪些属性

## HTML script 标签的属性

### type 和 language 属性

ype 和 language 属性都可用来指定 script 标签中的脚本的类型。

language 属性在 HTML 和 XHTML 标准中受到了非议，这两个标准提倡使用 type 属性。遗憾的是，这两个属性的值是不一样的。

```html
<script language = "JavaScript"></script>

<script type = "text/javascript"></script>
```

### src 和 charset 属性

对特别长的 JavaScript 程序或者经常重复使用的程序来说，你可以希望将这些代码存放到一个单独的文件中。在这样的情况下，让浏览器通过 src 属性来载入那个单独的文件。

src 的值是包含这个 JavaScript 程序的文件的 URL。保存的文件的 MIME 类型应是 application/x-javascript，但如果文件名的后缀为 .js，也能够被正确配置了的服务器进行恰当的处理。

charset 属性与 src 属性一起使用，告诉浏览器用来编码这个 javascript 程序的字符集。它的值是任何一个 ISO 标准字符集编码的名称。

### defer 属性

有的 javascript 脚本 document.write 方法来创建当前的文档内容，其他脚本就不一定是了。

如果您的脚本不会改变文档的内容，可将 defer 属性加入到 script 标签中，以便加快处理文档的速度。因为浏览器知道它将能够安全地读取文档的剩余部分而不用执行脚本，它将推迟对脚本的解释，直到文档已经显示给用户为止。
---
{"dg-publish":true,"permalink":"/02java//xml-java-net-malformed-url-exception/","dgPassFrontmatter":true}
---

# XML文件出现执行的时候java.net.MalformedURLException

今天我在使用这个

出现这个错误的原因是在创建URL对象时，传入的路径字符串不是一个合法的URL格式，

1. 缺少了协议部分（例如`http://`）。

要解决这个问题，您可以使用绝对路径或相对路径来指定XML文件的位置。如果您使用相对路径，请确保文件路径从项目的根目录开始，并使用正斜杠`/`来分隔目录。

2. 路径中包含了中文路径，不合法，尽量使用英文路径，我就是因为图省劲，文件夹命名的时候，并没有命名成中文。


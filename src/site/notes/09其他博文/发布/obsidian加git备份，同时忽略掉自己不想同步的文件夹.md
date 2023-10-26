---
{"dg-publish":true,"permalink":"/09//obsidian-git/","dgPassFrontmatter":true}
---

最近想用这个语雀进行知识库的分享，但是这个语雀的会员费太贵了，思来想去还是用 git 比较好，因为这个知识库的内容都是自己的笔记，为了能够访问的更加方便我选择了这个 gitte，而不是 github
我的知识库链接
[knowledge](https://gitee.com/qiukehao/knowledge)
# 第一步安装 git
[git 的安装网址](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)
# 第二步
在你要同步的文件夹中右键点击 open git base here
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309200854314.png)

# 第三步利用 gitte 新建一个仓库
如果你使用 github 也是一样的，就是访问的时候不是太方便，需要挂代理
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309200857333.png)
然后你去一个仓库的名字，我因为分享的是自己的知识库文件，所以就取名 knowledge 了
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309200858116.png)
创建之后会生成一个 ssh 密匙你复制一下
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309200900935.png)

# 第四步
输入下面的代码
```
git init
git config --global user.name fero
git config --global user.email 123@qq.com（换成你自己的）
```

# 第五步创建一下你的 gitignore 文件
这个文件是自己选择要忽略目录中的文件
比如说我的目录是
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309200902556.png)
但我的临时文件，大创，其他，journal 附件还有模板并不像开方，所以我们就要设置这个 gitignore 文件
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309200904968.png)
就是新建文本文件，更改后缀为 gitignore
然后利用记事本修改里面的内容
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309200904370.png)
这个是我的内容，就是忽略这些内容，这个.trash 和.obsidian 文件不用加/, 后面的别的文件夹都要加上这个/才可以, 否则无法识别

# 第六步, 输入代码
```
git remote add origin (https://gitee.com/qiukehao/knowledge.git)注意这个换成你自己第三步创建gitte仓库复制的ssh
git add --all
git commit -m "abc"
git push -u origin master
```

# 第七步安装这个 obsidian git 插件, 让其自动进行同步
修改我用红框圈着的部分
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202309200908624.png)

[TOC]

# git
## 参考资料
* http://www.jianshu.com/p/86dfc616de68
* http://www.jianshu.com/p/482b32716bbe
* https://git-scm.com/book/zh/v2
* http://res.crossincode.com/wechat/git.html

## 安装
* [Git的官方安装包](http://git-scm.com/download)

* 检查Git版本
```
git --version
```
* 创建用户标识
```
git config --global user.name “xxx”    //用户名
git config --global user.email “xx@xxx”    //邮箱   
git config --global color.ui “auto”    //界面偏好
```

* Git仓库
```
    git init    //创建一个包含所有元数据和仓库变更历史的.git隐藏目录
    git status    //检查当前目录下文件的状态
```

* 查看log时中文乱码

在Bash提示符下输入：

	git config --global i18n.commitencoding utf-8
	git config --global i18n.logoutputencoding gbk


## 操作
* 文件跟踪
```
git add .    //跟踪并记录当前目录下所有文件变化
git add index.html    //添加指定文件到暂存区
git add javascript/    //添加指定文件夹到暂存区
git add *.js    //通过通配符，添加一组文件到暂存区
git add -i    //以交互方式添加文件
git add -p    //只提交部分修改的内容
git commit –m “xxx”    //提交当前目录下的所有内容，并备注提交说明
git commit –-amend    //修改上一次提交的说明
```
* 本地文件操作
```
git mv originalfile.txt newsubdir/newfilename.txt    //移动文件
git rm filetoremove.txt    //将文件标识为删除状态，下一次提交时确认删除

git diff    //查看当前工作树与暂存区的差别，如果暂存区是空的，那么它将显示工作树与最新提交状态之间的差别
git diff --staged    //
git diff HEAD    //

git reset    //回滚到最后一次提交后的状态
git reset --hard    //循环地将所有未提交或未被放入暂存区的文件进行回滚
git checkout modifiedfile.txt    //只回滚某一个文件
```

* 远程交互
```
git remote -v 	//查看关联的远程主机及权限
git push <远程主机名称> <本地主机名称> 	//将本地文件提交至远程
```

## github操作
* 将制定地址的文件克隆到本地
```
git clone git@github.com:xxxx.git
```

# python
## 资料
[笨方法学python在线版](http://www.jb51.net/shouce/Pythonbbf/latest/)

[廖雪峰](http://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000/001374738264643de15c5c4abad47dd9510e3b86286acb8000)

[零基础学python](http://python.xiaoleilu.com/)

http://learnpythonthehardway.org/book/

http://wiki.zoomquiet.io/pythonic/MinimalistPyStart

http://my.oschina.net/deepblue/blog/550452

## 安装
### windows环境
* [activestate.com/activepython](http://www.activestate.com/activepython)

# MD语法
### extra
```
*[关键词]:悬浮注释
```
![]()
123
*[123]:这是123

### wikilinks
[[md语法]]

~~dedw~~

# 正则表达式
- [ ] [https://autohotkey.com/boards/viewtopic.php?t=4308](https://autohotkey.com/boards/viewtopic.php?t=4308)

- [ ] [http://deerchao.net/tutorials/regex/regex.htm](http://deerchao.net/tutorials/regex/regex.htm)

## 查找匹配
匹配中文字符的正则表达式：[u4e00-u9fa5]
评注：匹配中文还真是个头疼的事，有了这个表达式就好办了

匹配双字节字符(包括汉字在内)：[^x00-xff] 
评注：可以用来计算字符串的长度（一个双字节字符长度计2，ASCII字符计1）

匹配空白行的正则表达式：^ *$ 
评注：可以用来删除空白行

匹配HTML标记的正则表达式：<(S*?)[^>]*>.*?</1>|<.*? /> 
评注：网上流传的版本太糟糕，上面这个也仅仅能匹配部分，对于复杂的嵌套标记依旧无能为力

匹配首尾空白字符的正则表达式：^s*|s*$ 
评注：可以用来删除行首行尾的空白字符(包括空格、制表符、换页符等等)，非常有用的表达式

匹配Email地址的正则表达式：w+([-+.]w+)*@w+([-.]w+)*.w+([-.]w+)* 
评注：表单验证时很实用

匹配网址URL的正则表达式：[a-zA-z]+://[^s]* 
评注：网上流传的版本功能很有限，上面这个基本可以满足需求

匹配帐号是否合法(字母开头，允许5-16字节，允许字母数字下划线)：^[a-zA-Z][a-zA-Z0-9_]{4,15}$ 
评注：表单验证时很实用

匹配国内电话号码：d{3}-d{8}|d{4}-d{7} 
评注：匹配形式如0511-4405222或021-87888822

匹配腾讯QQ号：[1-9][0-9]{4,} 
评注：腾讯QQ号从10000开始

匹配中国邮政编码：[1-9]d{5}(?!d) 
评注：中国邮政编码为6位数字

匹配身份证：d{15}|d{18} 
评注：中国的身份证为15位或18位

匹配ip地址：d+.d+.d+.d+ 
评注：提取ip地址时有用

匹配特定数字： 
^[1-9]d*$　　//匹配正整数 
^-[1-9]d*$　//匹配负整数 
^-?[1-9]d*$　　//匹配整数 
^[1-9]d*|0$　//匹配非负整数（正整数+ 0） 
^-[1-9]d*|0$　　//匹配非正整数（负整数+ 0） 
^[1-9]d*.d*|0.d*[1-9]d*$　　//匹配正浮点数 
^-([1-9]d*.d*|0.d*[1-9]d*)$　//匹配负浮点数 
^-?([1-9]d*.d*|0.d*[1-9]d*|0?.0+|0)$　//匹配浮点数 
^[1-9]d*.d*|0.d*[1-9]d*|0?.0+|0$　　//匹配非负浮点数（正浮点数+ 0） 
^(-([1-9]d*.d*|0.d*[1-9]d*))|0?.0+|0$　　//匹配非正浮点数（负浮点数+ 0） 
评注：处理大量数据时有用，具体应用时注意修正

匹配特定字符串： 
^[A-Za-z]+$　　//匹配由26个英文字母组成的字符串 
^[A-Z]+$　　//匹配由26个英文字母的大写组成的字符串 
^[a-z]+$　　//匹配由26个英文字母的小写组成的字符串 
^[A-Za-z0-9]+$　　//匹配由数字和26个英文字母组成的字符串 
^w+$　　//匹配由数字、26个英文字母或者下划线组成的字符串

# sublime
## markdown配置

## 插件
### [MarkdownEditing](https://github.com/SublimeText-Markdown/MarkdownEditing)
* 作用不大，可以不安装
* 语法高亮
* command + option + k 插入链接
* command + shift + k 插入图片

### [OmniMarkupPreviewer](https://github.com/timonwong/OmniMarkupPreviewer)
* 可以局域网内部实时预览，但不能支持待办事项
* Command +Option +O: 在浏览器中预览
* Command+Option+X: 导出HTML
* Ctrl+Alt+C: HTML标记拷贝至剪贴板
* 配置OmniMarkupPreviewer.sublime-settings 文件
    "server_host":设置局域网访问IP，默认127.0.0.1
    "renderer_options-MarkdownRenderer"：渲染扩展项，[toc] 目录；strikeout 删除线；superscript 上标；subscript 下标；codehilite 代码块语法高亮支持

### [MarkdownPreview](https://github.com/revolunet/sublimetext-markdown-preview)
* 生成本地html后预览，支持待办事项
* 生成html文件：ctrl+B

## 自定制代码片段(Code Snippets)


## sublime中文匹配通配符
```
[\x{4e00}-\x{9fa5}]
```

## sublime指南
- [ ] [http://www.kancloud.cn/digest/sublime-text-complete-guide/61431](http://www.kancloud.cn/digest/sublime-text-complete-guide/61431)

# excel
- [ ] vlookup函数，4个参数，匹配值，匹配范围（范围的表示），相对位置（列），匹配模式（可选，默认模糊匹配）

# 数据分析
- [ ] APP产品需要关注的数据
- [ ] 数据的获取来源
- [ ] 专业数据来源的网站

# shell
[http://mp.weixin.qq.com/s?__biz=MzIxNDMyODgyMA==&mid=2247483695&idx=1&sn=54f10d647035a1b572736a7b1731fe29](http://mp.weixin.qq.com/s?__biz=MzIxNDMyODgyMA==&mid=2247483695&idx=1&sn=54f10d647035a1b572736a7b1731fe29)


# 输入法
```
ss,1=|  
xx,1=*
aa,1=[]
zz,1=()
yy,1=>
ee,1=[]
qq,1=()
ff,1=:
rw,1=- [ ] 
zs,1=*[]:
dd,1=
```

rw,1=- [ ]
bb,1=//
dd,1=
\```
\```
```
命令列表
----

COMMAND通用方法

方法

描述

execCommand( String cmd, \* params... )

执行命令的通用接口

该方法的第一个参数是需要执行的命令。剩下的**可选的**参数根据每个命令的不同而有一些差异， 具体请参照相应的命令详情。

queryCommandState( String cmd )

查询给定命令在当前选区内的状态。  
通用的返回状态有：

*   1 => 代表当前命令在当前选区内已执行
*   0 => 代表当前命令在当前选区内未执行， 但处于可用状态
*   \-1 => 代表当前命令在当前选区内处于不可用状态

queryCommandValue()

查询给定命令在当前选区内的值， 默认返回undefined。根据命令的不同其返回值也会不同。

以上列表中的方法对于每一个命令都是适用的。区别在于，对于不同的命令，其需要的参数可能会不同。

COMMAND列表

#

命令

描述

1

[anchor](#COMMAND::anchor)

插入锚点

2

[autosubmit](#COMMAND::autosubmit)

提交表单

3

[autotypeset](#COMMAND::autotypeset)

对当前编辑器的内容执行自动排版， 排版的行为根据config配置文件里的“autotypeset”选项进行控制。

4

[bold](#COMMAND::bold)

字体加粗

5

[italic](#COMMAND::italic)

字体倾斜

6

[subscript](#COMMAND::subscript)

下标文本，与“superscript”命令互斥

7

[superscript](#COMMAND::superscript)

上标文本，与“subscript”命令互斥

8

[blockquote](#COMMAND::blockquote)

添加引用

9

[cleardoc](#COMMAND::cleardoc)

清空文档

10

[touppercase](#COMMAND::touppercase)

把选区内文本变大写，与“tolowercase”命令互斥

11

[tolowercase](#COMMAND::tolowercase)

把选区内文本变小写，与“touppercase”命令互斥

12

[customstyle](#COMMAND::customstyle)

根据config配置文件里“customstyle”选项的值对匹配的标签执行样式替换。

13

[directionality](#COMMAND::directionality)

文字输入方向

14

[forecolor](#COMMAND::forecolor)

字体颜色

15

[backcolor](#COMMAND::backcolor)

字体背景颜色

16

[fontsize](#COMMAND::fontsize)

字体大小

17

[fontfamily](#COMMAND::fontfamily)

字体样式

18

[underline](#COMMAND::underline)

字体下划线,与删除线互斥

19

[strikethrough](#COMMAND::strikethrough)

字体删除线,与下划线互斥

20

[fontborder](#COMMAND::fontborder)

字体边框

21

[formatmatch](#COMMAND::formatmatch)

格式刷

22

[horizontal](#COMMAND::horizontal)

插入分割线

23

[imagefloat](#COMMAND::imagefloat)

图片对齐方式

24

[insertimage](#COMMAND::insertimage)

插入图片

25

[indent](#COMMAND::indent)

缩进

26

[insertcode](#COMMAND::insertcode)

插入代码

27

[inserthtml](#COMMAND::inserthtml)

插入html代码

28

[insertparagraph](#COMMAND::insertparagraph)

插入段落

29

[justify](#COMMAND::justify)

段落对齐方式

30

[lineheight](#COMMAND::lineheight)

行距

31

[link](#COMMAND::link)

插入超链接

32

[unlink](#COMMAND::unlink)

取消超链接

33

[insertorderedlist](#COMMAND::insertorderedlist)

有序列表，与“insertunorderedlist”命令互斥

34

[insertunorderedlist](#COMMAND::insertunorderedlist)

无序列表，与“insertorderedlist”命令互斥

35

[music](#COMMAND::music)

插入音乐

36

[pagebreak](#COMMAND::pagebreak)

插入分页符

37

[paragraph](#COMMAND::paragraph)

段落格式

38

[preview](#COMMAND::preview)

预览

39

[print](#COMMAND::print)

打印

40

[pasteplain](#COMMAND::pasteplain)

启用或取消纯文本粘贴模式

41

[removeformat](#COMMAND::removeformat)

清除文字样式

42

[rowspacing](#COMMAND::rowspacing)

设置段间距

43

[selectall](#COMMAND::selectall)

选中所有内容

44

[source](#COMMAND::source)

切换源码模式和编辑模式

45

[time](#COMMAND::time)

插入时间，默认格式：12:59:59

46

[date](#COMMAND::date)

插入日期，默认格式：2013-08-30

47

[undo](#COMMAND::undo)

撤销上一次执行的命令

48

[redo](#COMMAND::redo)

重做上一次执行的命令

49

[insertvideo](#COMMAND::insertvideo)

插入视频

50

[webapp](#COMMAND::webapp)

插入百度应用

#### anchor

命令

1.2.6.1

插入锚点

方法列表

##### execCommand(String cmd, String name)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

name

[String](#String)

锚点名称字符串

示例

javascript代码：

1
2

 //editor 是编辑器实例
 editor.execCommand('anchor', 'anchor1');

#### autosubmit

命令

1.2.6.1

提交表单

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'autosubmit' );

#### autotypeset

命令

1.2.6.1

对当前编辑器的内容执行自动排版， 排版的行为根据config配置文件里的“autotypeset”选项进行控制。

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'autotypeset' );

#### bold

命令

1.2.6.1

字体加粗

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

*   提示： 对已加粗的文本内容执行该命令， 将取消加粗

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1
2
3
4
5
6
7

 //editor是编辑器实例
 //对当前选中的文本内容执行加粗操作
 //第一次执行， 文本内容加粗
 editor.execCommand( 'bold' );

 //第二次执行， 文本内容取消加粗
 editor.execCommand( 'bold' );

#### italic

命令

1.2.6.1

字体倾斜

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

*   提示： 对已倾斜的文本内容执行该命令， 将取消倾斜

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1
2
3
4
5
6
7

 //editor是编辑器实例
 //对当前选中的文本内容执行斜体操作
 //第一次操作， 文本内容将变成斜体
 editor.execCommand( 'italic' );

 //再次对同一文本内容执行， 则文本内容将恢复正常
 editor.execCommand( 'italic' );

#### subscript

命令

1.2.6.1

下标文本，与“superscript”命令互斥

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

*   提示： 把选中的文本内容切换成下标文本， 如果当前选中的文本已经是下标， 则该操作会把文本内容还原成正常文本

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1
2
3
4
5
6
7

 //editor是编辑器实例
 //对当前选中的文本内容执行下标操作
 //第一次操作， 文本内容将变成下标文本
 editor.execCommand( 'subscript' );

 //再次对同一文本内容执行， 则文本内容将恢复正常
 editor.execCommand( 'subscript' );

#### superscript

命令

1.2.6.1

上标文本，与“subscript”命令互斥

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

*   提示： 把选中的文本内容切换成上标文本， 如果当前选中的文本已经是上标， 则该操作会把文本内容还原成正常文本

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1
2
3
4
5
6
7

 //editor是编辑器实例
 //对当前选中的文本内容执行上标操作
 //第一次操作， 文本内容将变成上标文本
 editor.execCommand( 'superscript' );

 //再次对同一文本内容执行， 则文本内容将恢复正常
 editor.execCommand( 'superscript' );

#### blockquote

命令

1.2.6.1

添加引用

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'blockquote' );

##### execCommand(String cmd, Object attrs)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

attrs

[Object](#Object)

节点属性

示例

javascript代码：

1
2
3

 editor.execCommand( 'blockquote',{
     style: "color: red;"
 } );

#### cleardoc

命令

1.2.6.1

清空文档

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1
2

 //editor 是编辑器实例
 editor.execCommand('cleardoc');

#### touppercase

命令

1.2.6.1

把选区内文本变大写，与“tolowercase”命令互斥

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'touppercase' );

#### tolowercase

命令

1.2.6.1

把选区内文本变小写，与“touppercase”命令互斥

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'tolowercase' );

#### customstyle

命令

1.2.6.1

根据config配置文件里“customstyle”选项的值对匹配的标签执行样式替换。

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'customstyle' );

#### directionality

命令

1.2.6.1

文字输入方向

方法列表

##### execCommand(String cmdName, String forward)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmdName

[String](#String)

命令字符串

forward

[String](#String)

传入'ltr'表示从左向右输入，传入'rtl'表示从右向左输入

示例

javascript代码：

1

 editor.execCommand( 'directionality', 'ltr');

##### queryCommandValue(String cmdName)

命令方法 1.2.6.1

查询当前选区的文字输入方向

参数列表

参数名

类型

描述

cmdName

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回'ltr'表示从左向右输入，返回'rtl'表示从右向左输入

示例

javascript代码：

1

 editor.queryCommandValue( 'directionality');

#### forecolor

命令

1.2.6.1

字体颜色

方法列表

##### execCommand(String cmd, String value)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

value

[String](#String)

色值(必须十六进制)

示例

javascript代码：

1

 editor.execCommand( 'forecolor', '#000' );

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

返回选区字体颜色

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回字体颜色

示例

javascript代码：

1

 editor.queryCommandValue( 'forecolor' );

#### backcolor

命令

1.2.6.1

字体背景颜色

方法列表

##### execCommand(String cmd, String value)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

value

[String](#String)

色值(必须十六进制)

示例

javascript代码：

1

 editor.execCommand( 'backcolor', '#000' );

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

返回选区字体颜色

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回字体背景颜色

示例

javascript代码：

1

 editor.queryCommandValue( 'backcolor' );

#### fontsize

命令

1.2.6.1

字体大小

方法列表

##### execCommand(String cmd, String value)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

value

[String](#String)

字体大小

示例

javascript代码：

1

 editor.execCommand( 'fontsize', '14px' );

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

返回选区字体大小

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回字体大小

示例

javascript代码：

1

 editor.queryCommandValue( 'fontsize' );

#### fontfamily

命令

1.2.6.1

字体样式

方法列表

##### execCommand(String cmd, String value)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

value

[String](#String)

字体样式

示例

javascript代码：

1

 editor.execCommand( 'fontfamily', '微软雅黑' );

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

返回选区字体样式

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回字体样式

示例

javascript代码：

1

 editor.queryCommandValue( 'fontfamily' );

#### underline

命令

1.2.6.1

字体下划线,与删除线互斥

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'underline' );

#### strikethrough

命令

1.2.6.1

字体删除线,与下划线互斥

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'strikethrough' );

#### fontborder

命令

1.2.6.1

字体边框

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'fontborder' );

#### formatmatch

命令

1.2.6.1

格式刷

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

*   提示： 该操作不能复制段落格式

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1
2
3

 //editor是编辑器实例
 //获取格式刷
 editor.execCommand( 'formatmatch' );

#### horizontal

命令

1.2.6.1

插入分割线

方法列表

##### execCommand(String cmdName)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmdName

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'horizontal' );

#### imagefloat

命令

1.2.6.1

图片对齐方式

方法列表

##### execCommand(String cmd, String align)

命令方法 1.2.6.1

执行当前命令

*   提示： 值center为独占一行居中

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

align

[String](#String)

对齐方式，可传left、right、none、center

示例

javascript代码：

1

 editor.execCommand( 'imagefloat', 'center' );

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

如果选区所在位置是图片区域

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回图片对齐方式

示例

javascript代码：

1

 editor.queryCommandValue( 'imagefloat' );

#### insertimage

命令

1.2.6.1

插入图片

方法列表

##### execCommand(String cmd, Object opt)

命令方法 1.2.6.1

执行当前命令

*   提示： 该命令第二个参数可接受一个图片配置项对象的数组，可以插入多张图片， 此时数组的每一个元素都是一个Object类型的图片属性集合。

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

opt

[Object](#Object)

属性键值对，这些属性都将被复制到当前插入图片

示例

javascript代码：

1
2
3
4
5

 editor.execCommand( 'insertimage', {
     src:'a/b/c.jpg',
     width:'100',
     height:'100'
 } );

javascript代码：

1
2
3
4
5
6
7
8
9

 editor.execCommand( 'insertimage', \[{
     src:'a/b/c.jpg',
     width:'100',
     height:'100'
 },{
     src:'a/b/d.jpg',
     width:'100',
     height:'100'
 }\] );

#### indent

命令

1.2.6.1

缩进

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'indent' );

#### insertcode

命令

1.2.6.1

插入代码

方法列表

##### execCommand(String cmd, String lang)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

lang

[String](#String)

插入代码的语言

示例

javascript代码：

1

 editor.execCommand( 'insertcode', 'javascript' );

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

如果选区所在位置是插入插入代码区域，返回代码的语言

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回代码的语言

示例

javascript代码：

1

 editor.queryCommandValue( 'insertcode' );

#### inserthtml

命令

1.2.6.1

插入html代码

方法列表

##### execCommand(String cmd, String html)

命令方法 1.2.6.1

执行当前命令

*   警告： 注意:该命令会对当前选区的位置，对插入的内容进行过滤转换处理。 过滤的规则遵循html语意化的原则。

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

html

[String](#String)

插入的html字符串

示例

javascript代码：

1
2
3
4
5
6
7
8
9

 //xxx\[BB\]xxx 当前选区为非闭合选区，选中BB这两个文本
 //执行命令，插入<b>CC</b>
 //插入后的效果 xxx<b>CC</b>xxx
 //<p>xx|xxx</p> 当前选区为闭合状态
 //插入<p>CC</p>
 //结果 <p>xx</p><p>CC</p><p>xxx</p>
 //<p>xxxx</p>|</p>xxx</p> 当前选区在两个p标签之间
 //插入 xxxx
 //结果 <p>xxxx</p><p>xxxx</p></p>xxx</p>

#### insertparagraph

命令

1.2.6.1

插入段落

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1
2

 //editor是编辑器实例
 editor.execCommand( 'insertparagraph' );

#### justify

命令

1.2.6.1

段落对齐方式

方法列表

##### execCommand(String cmd, String align)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

align

[String](#String)

对齐方式：left => 居左，right => 居右，center => 居中，justify => 两端对齐

示例

javascript代码：

1

 editor.execCommand( 'justify', 'center' );

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

如果选区所在位置是段落区域，返回当前段落对齐方式

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回段落对齐方式

示例

javascript代码：

1

 editor.queryCommandValue( 'justify' );

#### lineheight

命令

1.2.6.1

行距

方法列表

##### execCommand(String cmdName, String value)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmdName

[String](#String)

命令字符串

value

[String](#String)

传入的行高值， 该值是当前字体的倍数， 例如： 1.5, 1.75

示例

javascript代码：

1

 editor.execCommand( 'lineheight', 1.5);

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

查询当前选区内容的行高大小

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回当前行高大小

示例

javascript代码：

1

 editor.queryCommandValue( 'lineheight' );

#### link

命令

1.2.6.1

插入超链接

方法列表

##### execCommand(String cmd, Object options)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

options

[Object](#Object)

设置自定义属性，例如：url、title、target

示例

javascript代码：

1
2
3
4
5

 editor.execCommand( 'link', '{
     url:'ueditor.baidu.com',
     title:'ueditor',
     target:'\_blank'
 }' );

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

返回当前选中的第一个超链接节点

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[Element](#Element)

超链接节点

示例

javascript代码：

1

 editor.queryCommandValue( 'link' );

#### unlink

命令

1.2.6.1

取消超链接

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'unlink');

#### insertorderedlist

命令

1.2.6.1

有序列表，与“insertunorderedlist”命令互斥

方法列表

##### execCommand(String command, String style)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

command

[String](#String)

命令字符串

style

[String](#String)

插入的有序列表类型，值为：decimal,lower-alpha,lower-roman,upper-alpha,upper-roman,cn,cn1,cn2,num,num1,num2

示例

javascript代码：

1

 editor.execCommand( 'insertunorderedlist','decimal');

##### queryCommandState(String cmd)

命令方法 1.2.6.1

查询当前选区内容是否有序列表

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[int](#int)

如果当前选区是有序列表返回1，否则返回0

示例

javascript代码：

1

 editor.queryCommandState( 'insertorderedlist' );

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

查询当前选区内容是否有序列表

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回当前有序列表的类型，值为null或decimal,lower-alpha,lower-roman,upper-alpha,upper-roman,cn,cn1,cn2,num,num1,num2

示例

javascript代码：

1

 editor.queryCommandValue( 'insertorderedlist' );

#### insertunorderedlist

命令

1.2.6.1

无序列表，与“insertorderedlist”命令互斥

方法列表

##### execCommand(String command, String style)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

command

[String](#String)

命令字符串

style

[String](#String)

插入的无序列表类型，值为：circle,disc,square,dash,dot

示例

javascript代码：

1

 editor.execCommand( 'insertunorderedlist','circle');

##### insertunorderedlist(String command)

命令方法 1.2.6.1

查询当前是否有word文档粘贴进来的图片

参数列表

参数名

类型

描述

command

[String](#String)

命令字符串

返回值

类型

描述

[int](#int)

如果当前选区是无序列表返回1，否则返回0

示例

javascript代码：

1

 editor.queryCommandState( 'insertunorderedlist' );

##### queryCommandValue(String command)

命令方法 1.2.6.1

查询当前选区内容是否有序列表

参数列表

参数名

类型

描述

command

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

返回当前无序列表的类型，值为null或circle,disc,square,dash,dot

示例

javascript代码：

1

 editor.queryCommandValue( 'insertunorderedlist' );

#### music

命令

插入音乐

方法列表

##### execCommand(Object musicOptions)

命令方法

执行当前命令

参数列表

参数名

类型

描述

musicOptions

[Object](#Object)

插入音乐的参数项， 支持的key有： url=>音乐地址； width=>音乐容器宽度；height=>音乐容器高度；align=>音乐文件的对齐方式， 可选值有: left, center, right, none

示例

javascript代码：

1
2
3
4
5
6
7
8

 //editor是编辑器实例
 //在编辑器里插入一个“植物大战僵尸”的APP
 editor.execCommand( 'music' , {
     width: 400,
     height: 95,
     align: "center",
     url: "音乐地址"
 } );

#### pagebreak

命令

1.2.6.1

插入分页符

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

*   提示： 在表格中插入分页符会把表格切分成两部分

*   提示： 获取编辑器内的数据时， 编辑器会把分页符转换成“\_ueditor\_page\_break\_tag\_”字符串， 以便于提交数据到服务器端后处理分页。

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'pagebreak'); //插入一个hr标签，带有样式类名pagebreak

#### paragraph

命令

1.2.6.1

段落格式

方法列表

##### execCommand(String cmd, String style, Object attrs)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

style

[String](#String)

标签值为：'p', 'h1', 'h2', 'h3', 'h4', 'h5', 'h6'

attrs

[Object](#Object)

标签的属性

示例

javascript代码：

1
2
3

 editor.execCommand( 'Paragraph','h1','{
     class:'test'
 }' );

##### queryCommandValue(String cmd)

命令方法 1.2.6.1

返回选区内节点标签名

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[String](#String)

节点标签名

示例

javascript代码：

1

 editor.queryCommandValue( 'Paragraph' );

#### preview

命令

1.2.6.1

预览

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'preview' );

#### print

命令

1.2.6.1

打印

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'print' );

#### pasteplain

命令

1.2.6.1

启用或取消纯文本粘贴模式

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.queryCommandState( 'pasteplain' );

##### queryCommandState(String cmd)

命令方法 1.2.6.1

查询当前是否处于纯文本粘贴模式

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[int](#int)

如果处于纯文本模式，返回1，否则，返回0

示例

javascript代码：

1

 editor.queryCommandState( 'pasteplain' );

#### removeformat

命令

1.2.6.1

清除文字样式

方法列表

##### execCommand(String cmd, String tags, String style, String attrs)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

tags

[String](#String)

以逗号隔开的标签。如：strong

style

[String](#String)

样式如：color

attrs

[String](#String)

属性如:width

示例

javascript代码：

1

 editor.execCommand( 'removeformat', 'strong','color','width' );

#### rowspacing

命令

1.2.6.1

设置段间距

方法列表

##### execCommand(String cmd, String value, String dir)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

value

[String](#String)

段间距的值，以px为单位

dir

[String](#String)

间距位置，top或bottom，分别表示段前和段后

示例

javascript代码：

1

 editor.execCommand( 'rowspacing', '10', 'top' );

#### selectall

命令

1.2.6.1

选中所有内容

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'selectall' );

#### source

命令

1.2.6.1

切换源码模式和编辑模式

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'source');

##### queryCommandState(String cmd)

命令方法 1.2.6.1

查询当前编辑区域的状态是源码模式还是可视化模式

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

返回值

类型

描述

[int](#int)

如果当前是源码编辑模式，返回1，否则返回0

示例

javascript代码：

1

 editor.queryCommandState( 'source' );

#### time

命令

1.2.6.1

插入时间，默认格式：12:59:59

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'time');

#### date

命令

1.2.6.1

插入日期，默认格式：2013-08-30

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'date');

#### undo

命令

1.2.6.1

撤销上一次执行的命令

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'undo' );

#### redo

命令

1.2.6.1

重做上一次执行的命令

方法列表

##### execCommand(String cmd)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

示例

javascript代码：

1

 editor.execCommand( 'redo' );

#### insertvideo

命令

1.2.6.1

插入视频

方法列表

##### execCommand(String cmd, Object videoAttr)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

videoAttr

[Object](#Object)

键值对对象， 描述一个视频的所有属性

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 var videoAttr \= {
      //视频地址
      url: 'http://www.youku.com/xxx',
      //视频宽高值， 单位px
      width: 200,
      height: 100
 };

 //editor 是编辑器实例
 //向编辑器插入单个视频
 editor.execCommand( 'insertvideo', videoAttr );

##### execCommand(String cmd, Array videoArr)

命令方法 1.2.6.1

执行当前命令

参数列表

参数名

类型

描述

cmd

[String](#String)

命令字符串

videoArr

[Array](#Array)

需要插入的视频的数组， 其中的每一个元素都是一个键值对对象， 描述了一个视频的所有属性

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18

 var videoAttr1 \= {
      //视频地址
      url: 'http://www.youku.com/xxx',
      //视频宽高值， 单位px
      width: 200,
      height: 100
 },
 videoAttr2 \= {
      //视频地址
      url: 'http://www.youku.com/xxx',
      //视频宽高值， 单位px
      width: 200,
      height: 100
 }

 //editor 是编辑器实例
 //该方法将会向编辑器内插入两个视频
 editor.execCommand( 'insertvideo', \[ videoAttr1, videoAttr2 \] );

##### queryCommandState(String cmd)

命令方法 1.2.6.1

查询当前光标所在处是否是一个视频

参数列表

参数名

类型

描述

cmd

[String](#String)

需要查询的命令字符串

返回值

类型

描述

[int](#int)

如果当前光标所在处的元素是一个视频对象， 则返回1，否则返回0

示例

javascript代码：

1
2

 //editor 是编辑器实例
 editor.queryCommandState( 'insertvideo' );

#### webapp

命令

1.2.6.1

插入百度应用

方法列表

##### execCommand(Object appOptions)

命令方法 1.2.6.1

执行当前命令

*   提示： 需要百度APPKey

*   提示： 百度应用主页： [http://app.baidu.com/](http://app.baidu.com/)

参数列表

参数名

类型

描述

appOptions

[Object](#Object)

应用所需的参数项， 支持的key有： title=>应用标题， width=>应用容器宽度， height=>应用容器高度，logo=>应用logo，url=>应用地址

示例

javascript代码：

1
2
3
4
5
6
7
8
9

 //editor是编辑器实例
 //在编辑器里插入一个“植物大战僵尸”的APP
 editor.execCommand( 'webapp' , {
     title: '植物大战僵尸',
     width: 560,
     height: 465,
     logo: '应用展示的图片',
     url: '百度应用的地址'
 } );

UE
--

模块

UEditor公用空间，UEditor所有的功能都挂载在该空间下

方法列表

方法签名

静态

描述

[getListener(Object obj, String type, Boolean force)](#UE.getListener(Object,String,Boolean))

是

获得对象所拥有监听类型的所有监听器

[filterNode(Object root, Object rules)](#UE.filterNode(Object,Object))

是

根据传入节点和过滤规则过滤相应节点

[filterWord(String html)](#UE.filterWord(String))

是

根据传入html字符串过滤word

[htmlparser(String htmlstr, Boolean ignoreBlank)](#UE.htmlparser(String,Boolean))

是

html字符串转换成uNode节点的静态方法

类列表

类名

描述

[Editor](#UE.Editor)

UEditor的核心类，为用户提供与编辑器交互的接口。

[EventBase](#UE.EventBase)

UE采用的事件基类，继承此类的对应类将获取addListener,removeListener,fireEvent方法。 在UE中，Editor以及所有ui实例都继承了该类，故可以在对应的ui对象以及editor对象上使用上述方法。

[uNode](#UE.uNode)

编辑器模拟的节点类

模块成员详细描述([UE](#UE))

#### getListener([Object](#Object) obj, [String](#String) type, [Boolean](#Boolean) force)

方法 静态

1.2.6.1

获得对象所拥有监听类型的所有监听器

所属模块： [UE](#UE)

参数列表

参数名

类型

描述

obj

[Object](#Object)

查询监听器的对象

type

[String](#String)

事件类型

force

[Boolean](#Boolean)

为true且当前所有type类型的侦听器不存在时，创建一个空监听器数组

返回值

类型

描述

[Array](#Array)

监听器数组

#### filterNode([Object](#Object) root, [Object](#Object) rules)

方法 静态

1.2.6.1

根据传入节点和过滤规则过滤相应节点

所属模块： [UE](#UE)

参数列表

参数名

类型

描述

root

[Object](#Object)

指定root节点

rules

[Object](#Object)

过滤规则json对象

示例

javascript代码：

1

 UE.filterNode(root,editor.options.filterRules);

#### filterWord([String](#String) html)

方法 静态

1.2.6.1

根据传入html字符串过滤word

所属模块： [UE](#UE)

参数列表

参数名

类型

描述

html

[String](#String)

html字符串

返回值

类型

描述

[String](#String)

已过滤后的结果字符串

示例

javascript代码：

1

 UE.filterWord(html);

#### htmlparser([String](#String) htmlstr, [Boolean](#Boolean) ignoreBlank)

方法 静态

1.2.6.1

html字符串转换成uNode节点的静态方法

所属模块： [UE](#UE)

参数列表

参数名

类型

描述

htmlstr

[String](#String)

要转换的html代码

ignoreBlank

[Boolean](#Boolean)

若设置为true，转换的时候忽略\\n\\r\\t等空白字符

返回值

类型

描述

[uNode](#uNode)

给定的html片段转换形成的uNode对象

示例

javascript代码：

1

 var root \= UE.htmlparser('<p><b>htmlparser</b></p>', true);

### Editor

类

UEditor的核心类，为用户提供与编辑器交互的接口。

所属模块： [UE](#UE)

事件列表

事件名

描述

[ready](#UE.Editor:ready)

编辑器准备就绪后会触发该事件

[destroy](#UE.Editor:destroy)

执行destroy方法,会触发该事件

[reset](#UE.Editor:reset)

执行reset方法,会触发该事件

[focus](#UE.Editor:focus)

执行focus方法,会触发该事件

[langReady](#UE.Editor:langReady)

语言加载完成会触发该事件

[beforeExecCommand](#UE.Editor:beforeExecCommand)

运行命令之后会触发该命令

[afterExecCommand](#UE.Editor:afterExecCommand)

运行命令之后会触发该命令

[firstBeforeExecCommand](#UE.Editor:firstBeforeExecCommand)

运行命令之前会触发该命令

[beforeGetContent](#UE.Editor:beforeGetContent)

在getContent方法执行之前会触发该事件

[afterGetContent](#UE.Editor:afterGetContent)

在getContent方法执行之后会触发该事件

[getAllHtml](#UE.Editor:getAllHtml)

在getAllHtml方法执行时会触发该事件

[beforeSetContent](#UE.Editor:beforeSetContent)

在setContent方法执行之前会触发该事件

[afterSetContent](#UE.Editor:afterSetContent)

在setContent方法执行之后会触发该事件

[selectionchange](#UE.Editor:selectionchange)

每当编辑器内部选区发生改变时，将触发该事件

[beforeSelectionChange](#UE.Editor:beforeSelectionChange)

在所有selectionchange的监听函数执行之前，会触发该事件

[afterSelectionChange](#UE.Editor:afterSelectionChange)

在所有selectionchange的监听函数执行完之后，会触发该事件

[contentChange](#UE.Editor:contentChange)

编辑器内容发生改变时会触发该事件

构造器列表

方法签名

描述

[Editor()](#UE.Editor:Editor())

以默认参数构建一个编辑器实例

[Editor(Object setting)](#UE.Editor:Editor(Object))

以给定的参数集合创建一个编辑器实例，对于未指定的参数，将应用默认参数。

方法列表

方法签名

静态

描述

[ready(Function fn)](#UE.Editor:ready(Function))

否

编辑器对外提供的监听ready事件的接口， 通过调用该方法，达到的效果与监听ready事件是一致的

[setOpt(String key, \* val)](#UE.Editor:setOpt(String,*))

否

该方法是提供给插件里面使用，设置配置项默认值

[setOpt(Object options)](#UE.Editor:setOpt(Object))

否

该方法是提供给插件里面使用，以{key:value}集合的方式设置插件内用到的配置项默认值

[destroy()](#UE.Editor:destroy())

否

销毁编辑器实例，使用textarea代替

[render(String containerId)](#UE.Editor:render(String))

否

渲染编辑器的DOM到指定容器

[render(Element containerDom)](#UE.Editor:render(Element))

否

渲染编辑器的DOM到指定容器

[sync()](#UE.Editor:sync())

否

同步数据到编辑器所在的form 从编辑器的容器节点向上查找form元素，若找到，就同步编辑内容到找到的form里，为提交数据做准备，主要用于是手动提交的情况 后台取得数据的键值，使用你容器上的name属性，如果没有就使用参数里的textarea项

[sync(String formID)](#UE.Editor:sync(String))

否

根据传入的formId，在页面上查找要同步数据的表单，若找到，就同步编辑内容到找到的form里，为提交数据做准备 后台取得数据的键值，该键值默认使用给定的编辑器容器的name属性，如果没有name属性则使用参数项里给定的“textarea”项

[setHeight(Number number)](#UE.Editor:setHeight(Number))

否

设置编辑器高度

[addshortcutkey(Object keyset)](#UE.Editor:addshortcutkey(Object))

否

为编辑器的编辑命令提供快捷键 这个接口是为插件扩展提供的接口,主要是为新添加的插件，如果需要添加快捷键，所提供的接口

[addshortcutkey(String cmd, String keys)](#UE.Editor:addshortcutkey(String,String))

否

这个接口是为插件扩展提供的接口,主要是为新添加的插件，如果需要添加快捷键，所提供的接口

[getContent()](#UE.Editor:getContent())

否

获取编辑器的内容

[getContent(Function fn)](#UE.Editor:getContent(Function))

否

获取编辑器的内容。 可以通过参数定义编辑器内置的判空规则

[getAllHtml()](#UE.Editor:getAllHtml())

否

取得完整的html代码，可以直接显示成完整的html文档

[getPlainTxt()](#UE.Editor:getPlainTxt())

否

得到编辑器的纯文本内容，但会保留段落格式

[getContentTxt()](#UE.Editor:getContentTxt())

否

获取编辑器中的纯文本内容,没有段落格式

[setContent(String html)](#UE.Editor:setContent(String))

否

设置编辑器的内容，可修改编辑器当前的html内容

[setContent(String html, Boolean isAppendTo)](#UE.Editor:setContent(String,Boolean))

否

设置编辑器的内容，可修改编辑器当前的html内容

[focus()](#UE.Editor:focus())

否

让编辑器获得焦点，默认focus到编辑器头部

[focus(Boolean toEnd)](#UE.Editor:focus(Boolean))

否

让编辑器获得焦点，toEnd确定focus位置

[execCommand(String cmdName)](#UE.Editor:execCommand(String))

否

执行编辑命令cmdName，完成富文本编辑效果

[queryCommandState(String cmdName)](#UE.Editor:queryCommandState(String))

否

根据传入的command命令，查选编辑器当前的选区，返回命令的状态

[queryCommandValue(String cmdName)](#UE.Editor:queryCommandValue(String))

否

根据传入的command命令，查选编辑器当前的选区，根据命令返回相关的值

[hasContents()](#UE.Editor:hasContents())

否

检查编辑区域中是否有内容

[hasContents(Array tags)](#UE.Editor:hasContents(Array))

否

检查编辑区域中是否有内容，若包含参数tags中的节点类型，直接返回true

[reset()](#UE.Editor:reset())

否

重置编辑器，可用来做多个tab使用同一个编辑器实例

[setEnabled()](#UE.Editor:setEnabled())

否

设置当前编辑区域可以编辑

[setDisabled()](#UE.Editor:setDisabled())

否

设置当前编辑区域不可编辑

[setDisabled(String except)](#UE.Editor:setDisabled(String))

否

设置当前编辑区域不可编辑,except中的命令除外

[setDisabled(Array except)](#UE.Editor:setDisabled(Array))

否

设置当前编辑区域不可编辑,except中的命令除外

[setShow()](#UE.Editor:setShow())

否

显示编辑器

[setHide()](#UE.Editor:setHide())

否

隐藏编辑器

[getLang(String path)](#UE.Editor:getLang(String))

否

根据指定的路径，获取对应的语言资源

[getContentLength()](#UE.Editor:getContentLength())

否

计算编辑器html内容字符串的长度

[getContentLength(Boolean ingoneHtml)](#UE.Editor:getContentLength(Boolean))

否

计算编辑器当前纯文本内容的长度

[addInputRule(Function rule)](#UE.Editor:addInputRule(Function))

否

注册输入过滤规则

[filterInputRule(UE.uNode root)](#UE.Editor:filterInputRule(UE.uNode))

否

执行注册的过滤规则

[addOutputRule(Function rule)](#UE.Editor:addOutputRule(Function))

否

注册输出过滤规则

[filterOutputRule(UE.uNode root)](#UE.Editor:filterOutputRule(UE.uNode))

否

根据输出过滤规则，过滤编辑器内容

类成员详细描述([Editor](#UE.Editor))

#### ready

事件

1.2.6.1

编辑器准备就绪后会触发该事件

*   提示： render方法执行完成之后,会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

示例

javascript代码：

1
2
3

 editor.addListener( 'ready', function( editor ) {
     editor.execCommand( 'focus' ); //编辑器家在完成后，让编辑器拿到焦点
 } );

#### destroy

事件

1.2.6.1

执行destroy方法,会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:destroy()](#UE.Editor:destroy())

#### reset

事件

1.2.6.1

执行reset方法,会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:reset()](#UE.Editor:reset())

#### focus

事件

1.2.6.1

执行focus方法,会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:focus(Boolean)](#UE.Editor:focus(Boolean))

#### langReady

事件

1.2.6.1

语言加载完成会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

#### beforeExecCommand

事件

1.2.6.1

运行命令之后会触发该命令

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

#### afterExecCommand

事件

1.2.6.1

运行命令之后会触发该命令

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

#### firstBeforeExecCommand

事件

1.2.6.1

运行命令之前会触发该命令

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

#### beforeGetContent

事件

1.2.6.1

在getContent方法执行之前会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:getContent()](#UE.Editor:getContent())

#### afterGetContent

事件

1.2.6.1

在getContent方法执行之后会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:getContent()](#UE.Editor:getContent())

#### getAllHtml

事件

1.2.6.1

在getAllHtml方法执行时会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:getAllHtml()](#UE.Editor:getAllHtml())

#### beforeSetContent

事件

1.2.6.1

在setContent方法执行之前会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:setContent(String)](#UE.Editor:setContent(String))

#### afterSetContent

事件

1.2.6.1

在setContent方法执行之后会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:setContent(String)](#UE.Editor:setContent(String))

#### selectionchange

事件

1.2.6.1

每当编辑器内部选区发生改变时，将触发该事件

*   警告： 该事件的触发非常频繁，不建议在该事件的处理过程中做重量级的处理

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

示例

javascript代码：

1
2
3

 editor.addListener( 'selectionchange', function( editor ) {
     console.log('选区发生改变');
 }

#### beforeSelectionChange

事件

1.2.6.1

在所有selectionchange的监听函数执行之前，会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:selectionchange](#UE.Editor:selectionchange)

#### afterSelectionChange

事件

1.2.6.1

在所有selectionchange的监听函数执行完之后，会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:selectionchange](#UE.Editor:selectionchange)

#### contentChange

事件

1.2.6.1

编辑器内容发生改变时会触发该事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

#### Editor()

构造器

1.2.6.1

以默认参数构建一个编辑器实例

*   提示： 通过 改构造方法实例化的编辑器,不带ui层.需要render到一个容器,编辑器实例才能正常渲染到页面

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Config](#UE.Config)

示例

javascript代码：

1
2

 var editor \= new UE.Editor();
 editor.execCommand('blod');

#### Editor([Object](#Object) setting)

构造器

1.2.6.1

以给定的参数集合创建一个编辑器实例，对于未指定的参数，将应用默认参数。

*   提示： 通过 改构造方法实例化的编辑器,不带ui层.需要render到一个容器,编辑器实例才能正常渲染到页面

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Config](#UE.Config)

参数列表

参数名

类型

描述

setting

[Object](#Object)

创建编辑器的参数

示例

javascript代码：

1
2

 var editor \= new UE.Editor();
 editor.execCommand('blod');

#### ready([Function](#Function) fn)

方法

1.2.6.1

编辑器对外提供的监听ready事件的接口， 通过调用该方法，达到的效果与监听ready事件是一致的

*   提示： 需要等待编辑器加载完成后才能执行的代码,可以使用该方法传入

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor.event:ready](#UE.Editor.event:ready)

参数列表

参数名

类型

描述

fn

[Function](#Function)

编辑器ready之后所执行的回调, 如果在注册事件之前编辑器已经ready，将会 立即触发该回调。

示例

javascript代码：

1
2
3

 editor.ready( function( editor ) {
     editor.setContent('初始化完毕');
 } );

#### setOpt([String](#String) key, [\*](#*) val)

方法

1.2.6.1

该方法是提供给插件里面使用，设置配置项默认值

*   警告： 三处设置配置项的优先级: 实例化时传入参数 > setOpt()设置 > config文件里设置

*   警告： 该方法仅供编辑器插件内部和编辑器初始化时调用，其他地方不能调用。

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

key

[String](#String)

编辑器的可接受的选项名称

val

[\*](#*)

该选项可接受的值

示例

javascript代码：

1

 editor.setOpt( 'initContent', '欢迎使用编辑器' );

#### setOpt([Object](#Object) options)

方法

1.2.6.1

该方法是提供给插件里面使用，以{key:value}集合的方式设置插件内用到的配置项默认值

*   警告： 三处设置配置项的优先级: 实例化时传入参数 > setOpt()设置 > config文件里设置

*   警告： 该方法仅供编辑器插件内部和编辑器初始化时调用，其他地方不能调用。

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

options

[Object](#Object)

将要设置的选项的键值对对象

示例

javascript代码：

1
2
3

 editor.setOpt( {
     'initContent': '欢迎使用编辑器'
 } );

#### destroy()

方法

1.2.6.1

销毁编辑器实例，使用textarea代替

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

示例

javascript代码：

1

 editor.destroy();

#### render([String](#String) containerId)

方法

1.2.6.1

渲染编辑器的DOM到指定容器

*   提示： 执行该方法,会触发ready事件

*   警告： 必须且只能调用一次

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

containerId

[String](#String)

指定一个容器ID

#### render([Element](#Element) containerDom)

方法

1.2.6.1

渲染编辑器的DOM到指定容器

*   提示： 执行该方法,会触发ready事件

*   警告： 必须且只能调用一次

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

containerDom

[Element](#Element)

直接指定容器对象

#### sync()

方法

1.2.6.1

同步数据到编辑器所在的form 从编辑器的容器节点向上查找form元素，若找到，就同步编辑内容到找到的form里，为提交数据做准备，主要用于是手动提交的情况 后台取得数据的键值，使用你容器上的name属性，如果没有就使用参数里的textarea项

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

示例

javascript代码：

1
2

 editor.sync();
 form.sumbit(); //form变量已经指向了form元素

#### sync([String](#String) formID)

方法

1.2.6.1

根据传入的formId，在页面上查找要同步数据的表单，若找到，就同步编辑内容到找到的form里，为提交数据做准备 后台取得数据的键值，该键值默认使用给定的编辑器容器的name属性，如果没有name属性则使用参数项里给定的“textarea”项

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

formID

[String](#String)

指定一个要同步数据的form的id,编辑器的数据会同步到你指定form下

#### setHeight([Number](#Number) number)

方法

1.2.6.1

设置编辑器高度

*   提示： 当配置项autoHeightEnabled为真时,该方法无效

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

number

[Number](#Number)

设置的高度值，纯数值，不带单位

示例

javascript代码：

1

 editor.setHeight(number);

#### addshortcutkey([Object](#Object) keyset)

方法

1.2.6.1

为编辑器的编辑命令提供快捷键 这个接口是为插件扩展提供的接口,主要是为新添加的插件，如果需要添加快捷键，所提供的接口

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

keyset

[Object](#Object)

命令名和快捷键键值对对象，多个按钮的快捷键用“＋”分隔

示例

javascript代码：

1
2
3
4

 editor.addshortcutkey({
     "Bold" : "ctrl+66",//^B
     "Italic" : "ctrl+73", //^I
 });

#### addshortcutkey([String](#String) cmd, [String](#String) keys)

方法

1.2.6.1

这个接口是为插件扩展提供的接口,主要是为新添加的插件，如果需要添加快捷键，所提供的接口

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

cmd

[String](#String)

触发快捷键时，响应的命令

keys

[String](#String)

快捷键的字符串，多个按钮用“＋”分隔

示例

javascript代码：

1

 editor.addshortcutkey("Underline", "ctrl+85"); //^U

#### getContent()

方法

1.2.6.1

获取编辑器的内容

*   警告： 该方法获取到的是经过编辑器内置的过滤规则进行过滤后得到的内容

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

返回值

类型

描述

[String](#String)

编辑器的内容字符串, 如果编辑器的内容为空，或者是空的标签内容（如:”<p><br/></p>“）， 则返回空字符串

示例

javascript代码：

1
2

 //编辑器html内容:<p>1<strong>2<em>34</em>5</strong>6</p>
 var content \= editor.getContent(); //返回值:<p>1<strong>2<em>34</em>5</strong>6</p>

#### getContent([Function](#Function) fn)

方法

1.2.6.1

获取编辑器的内容。 可以通过参数定义编辑器内置的判空规则

*   提示： 该方法在处理包含有初始化内容的时候能起到很好的作用。

*   警告： 该方法获取到的是经过编辑器内置的过滤规则进行过滤后得到的内容

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

fn

[Function](#Function)

自定的判空规则， 要求该方法返回一个boolean类型的值， 代表当前编辑器的内容是否空， 如果返回true， 则该方法将直接返回空字符串；如果返回false，则编辑器将返回 经过内置过滤规则处理后的内容。

返回值

类型

描述

[String](#String)

编辑器的内容字符串

示例

javascript代码：

1
2
3
4

 // editor 是一个编辑器的实例
 var content \= editor.getContent( function ( editor ) {
      return editor.body.innerHTML \=== '欢迎使用UEditor'; //返回空字符串
 } );

#### getAllHtml()

方法

1.2.6.1

取得完整的html代码，可以直接显示成完整的html文档

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

返回值

类型

描述

[String](#String)

编辑器的内容html文档字符串

#### getPlainTxt()

方法

1.2.6.1

得到编辑器的纯文本内容，但会保留段落格式

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

返回值

类型

描述

[String](#String)

编辑器带段落格式的纯文本内容字符串

示例

javascript代码：

1
2

 //编辑器html内容:<p><strong>1</strong></p><p><strong>2</strong></p>
 console.log(editor.getPlainTxt()); //输出:"1\\n2\\n

#### getContentTxt()

方法

1.2.6.1

获取编辑器中的纯文本内容,没有段落格式

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

返回值

类型

描述

[String](#String)

编辑器不带段落格式的纯文本内容字符串

示例

javascript代码：

1
2

 //编辑器html内容:<p><strong>1</strong></p><p><strong>2</strong></p>
 console.log(editor.getPlainTxt()); //输出:"12

#### setContent([String](#String) html)

方法

1.2.6.1

设置编辑器的内容，可修改编辑器当前的html内容

*   警告： 通过该方法插入的内容，是经过编辑器内置的过滤规则进行过滤后得到的内容

*   警告： 该方法会触发selectionchange事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

html

[String](#String)

要插入的html内容

示例

javascript代码：

1

 editor.getContent('<p>test</p>');

#### setContent([String](#String) html, [Boolean](#Boolean) isAppendTo)

方法

1.2.6.1

设置编辑器的内容，可修改编辑器当前的html内容

*   警告： 通过该方法插入的内容，是经过编辑器内置的过滤规则进行过滤后得到的内容

*   警告： 该方法会触发selectionchange事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

html

[String](#String)

要插入的html内容

isAppendTo

[Boolean](#Boolean)

若传入true，不清空原来的内容，在最后插入内容，否则，清空内容再插入

示例

javascript代码：

1
2

 //假设设置前的编辑器内容是 <p>old text</p>
 editor.setContent('<p>new text</p>', true); //插入的结果是<p>old text</p><p>new text</p>

#### focus()

方法

1.2.6.1

让编辑器获得焦点，默认focus到编辑器头部

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

示例

javascript代码：

1

 editor.focus()

#### focus([Boolean](#Boolean) toEnd)

方法

1.2.6.1

让编辑器获得焦点，toEnd确定focus位置

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

toEnd

[Boolean](#Boolean)

默认focus到编辑器头部，toEnd为true时focus到内容尾部

示例

javascript代码：

1

 editor.focus(true)

#### execCommand([String](#String) cmdName)

方法

1.2.6.1

执行编辑命令cmdName，完成富文本编辑效果

*   提示： 具体命令的使用请参考[命令列表](#COMMAND.LIST)

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

cmdName

[String](#String)

需要执行的命令

返回值

类型

描述

[\*](#*)

返回命令函数运行的返回值

示例

javascript代码：

1

 editor.execCommand(cmdName);

#### queryCommandState([String](#String) cmdName)

方法

1.2.6.1

根据传入的command命令，查选编辑器当前的选区，返回命令的状态

*   提示： 具体命令的使用请参考[命令列表](#COMMAND.LIST)

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[COMMAND.LIST](#COMMAND.LIST)

参数列表

参数名

类型

描述

cmdName

[String](#String)

需要查询的命令名称

返回值

类型

描述

[Number](#Number)

number 返回放前命令的状态，返回值三种情况：(-1|0|1)

示例

javascript代码：

1

 editor.queryCommandState(cmdName)  \=> (\-1|0|1)

#### queryCommandValue([String](#String) cmdName)

方法

1.2.6.1

根据传入的command命令，查选编辑器当前的选区，根据命令返回相关的值

*   提示： 具体命令的使用请参考[命令列表](#COMMAND.LIST)

*   提示： 只有部分插件有此方法

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[COMMAND.LIST](#COMMAND.LIST)

参数列表

参数名

类型

描述

cmdName

[String](#String)

需要查询的命令名称

返回值

类型

描述

[\*](#*)

返回每个命令特定的当前状态值

#### hasContents()

方法

1.2.6.1

检查编辑区域中是否有内容

*   提示： 默认有文本内容，或者有以下节点都不认为是空 table,ul,ol,dl,iframe,area,base,col,hr,img,embed,input,link,meta,param

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

返回值

类型

描述

[Boolean](#Boolean)

检查有内容返回true，否则返回false

示例

javascript代码：

1

 editor.hasContents()

#### hasContents([Array](#Array) tags)

方法

1.2.6.1

检查编辑区域中是否有内容，若包含参数tags中的节点类型，直接返回true

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

tags

[Array](#Array)

传入数组判断时用到的节点类型

返回值

类型

描述

[Boolean](#Boolean)

若文档中包含tags数组里对应的tag，返回true，否则返回false

示例

javascript代码：

1

 editor.hasContents(\['span'\]);

#### reset()

方法

1.2.6.1

重置编辑器，可用来做多个tab使用同一个编辑器实例

*   提示： 此方法会清空编辑器内容，清空回退列表，会触发reset事件

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

示例

javascript代码：

1

 editor.reset()

#### setEnabled()

方法

1.2.6.1

设置当前编辑区域可以编辑

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

示例

javascript代码：

1

 editor.setEnabled()

#### setDisabled()

方法

1.2.6.1

设置当前编辑区域不可编辑

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

#### setDisabled([String](#String) except)

方法

1.2.6.1

设置当前编辑区域不可编辑,except中的命令除外

*   提示： 即使设置了disable，此处配置的例外命令仍然可以执行

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

except

[String](#String)

例外命令的字符串

示例

javascript代码：

1

 editor.setDisabled('bold'); //禁用工具栏中除加粗之外的所有功能

#### setDisabled([Array](#Array) except)

方法

1.2.6.1

设置当前编辑区域不可编辑,except中的命令除外

*   提示： 即使设置了disable，此处配置的例外命令仍然可以执行

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

except

[Array](#Array)

例外命令的字符串数组，数组中的命令仍然可以执行

示例

javascript代码：

1

 editor.setDisabled(\['bold','insertimage'\]); //禁用工具栏中除加粗和插入图片之外的所有功能

#### setShow()

方法

1.2.6.1

显示编辑器

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

示例

javascript代码：

1

 editor.setShow()

#### setHide()

方法

1.2.6.1

隐藏编辑器

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

示例

javascript代码：

1

 editor.setHide()

#### getLang([String](#String) path)

方法

1.2.6.1

根据指定的路径，获取对应的语言资源

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

path

[String](#String)

路径根据的是lang目录下的语言文件的路径结构

返回值

类型

描述

[Object | String](#Object | String)

根据路径返回语言资源的Json格式对象或者语言字符串

示例

javascript代码：

1

 editor.getLang('contextMenu.delete'); //如果当前是中文，那返回是的是'删除'

#### getContentLength()

方法

1.2.6.1

计算编辑器html内容字符串的长度

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

返回值

类型

描述

[Number](#Number)

返回计算的长度

示例

javascript代码：

1
2

 //编辑器html内容<p><strong>132</strong></p>
 editor.getContentLength() //返回27

#### getContentLength([Boolean](#Boolean) ingoneHtml)

方法

1.2.6.1

计算编辑器当前纯文本内容的长度

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

ingoneHtml

[Boolean](#Boolean)

传入true时，只按照纯文本来计算

返回值

类型

描述

[Number](#Number)

返回计算的长度，内容中有hr/img/iframe标签，长度加1

示例

javascript代码：

1
2

 //编辑器html内容<p><strong>132</strong></p>
 editor.getContentLength() //返回3

#### addInputRule([Function](#Function) rule)

方法

1.2.6.1

注册输入过滤规则

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

rule

[Function](#Function)

要添加的过滤规则

示例

javascript代码：

1
2
3
4
5

 editor.addInputRule(function(root){
   $.each(root.getNodesByTagName('div'),function(i,node){
       node.tagName\="p";
   });
 });

#### filterInputRule([UE.uNode](#UE.uNode) root)

方法

1.2.6.1

执行注册的过滤规则

*   提示： 执行editor.setContent方法和执行'inserthtml'命令后，会运行该过滤函数

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:addInputRule](#UE.Editor:addInputRule)

参数列表

参数名

类型

描述

root

[UE.uNode](#UE.uNode)

要过滤的uNode节点

示例

javascript代码：

1

 editor.filterInputRule(editor.body);

#### addOutputRule([Function](#Function) rule)

方法

1.2.6.1

注册输出过滤规则

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参数列表

参数名

类型

描述

rule

[Function](#Function)

要添加的过滤规则

示例

javascript代码：

1
2
3
4
5

 editor.addOutputRule(function(root){
   $.each(root.getNodesByTagName('p'),function(i,node){
       node.tagName\="div";
   });
 });

#### filterOutputRule([UE.uNode](#UE.uNode) root)

方法

1.2.6.1

根据输出过滤规则，过滤编辑器内容

*   提示： 执行editor.getContent方法的时候，会先运行该过滤函数

所属模块： [UE](#UE)

所属类： [UE.Editor](#UE.Editor)

参考

[UE.Editor:addOutputRule](#UE.Editor:addOutputRule)

参数列表

参数名

类型

描述

root

[UE.uNode](#UE.uNode)

要过滤的uNode节点

示例

javascript代码：

1

 editor.filterOutputRule(editor.body);

### EventBase

类

UE采用的事件基类，继承此类的对应类将获取addListener,removeListener,fireEvent方法。 在UE中，Editor以及所有ui实例都继承了该类，故可以在对应的ui对象以及editor对象上使用上述方法。

所属模块： [UE](#UE)

构造器列表

方法签名

描述

[EventBase()](#UE.EventBase:EventBase())

通过此构造器，子类可以继承EventBase获取事件监听的方法

方法列表

方法签名

静态

描述

[addListener(String types, Function fn)](#UE.EventBase:addListener(String,Function))

否

注册事件监听器

[removeListener(String types, Function fn)](#UE.EventBase:removeListener(String,Function))

否

移除事件监听器

[fireEvent(String types)](#UE.EventBase:fireEvent(String))

否

触发事件

[fireEvent(String types, \*... options)](#UE.EventBase:fireEvent(String,*...))

否

触发事件

类成员详细描述([EventBase](#UE.EventBase))

#### EventBase()

构造器

1.2.6.1

通过此构造器，子类可以继承EventBase获取事件监听的方法

所属模块： [UE](#UE)

所属类： [UE.EventBase](#UE.EventBase)

示例

javascript代码：

1

 UE.EventBase.call(editor);

#### addListener([String](#String) types, [Function](#Function) fn)

方法

1.2.6.1

注册事件监听器

所属模块： [UE](#UE)

所属类： [UE.EventBase](#UE.EventBase)

参考

[UE.EventBase:fireEvent(String)](#UE.EventBase:fireEvent(String))

参数列表

参数名

类型

描述

types

[String](#String)

监听的事件名称，同时监听多个事件使用空格分隔

fn

[Function](#Function)

监听的事件被触发时，会执行该回调函数

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 editor.addListener('selectionchange',function(){
      console.log("选区已经变化！");
 })
 editor.addListener('beforegetcontent aftergetcontent',function(type){
         if(type \== 'beforegetcontent'){
             //do something
         }else{
             //do something
         }
         console.log(this.getContent) // this是注册的事件的编辑器实例
 })

#### removeListener([String](#String) types, [Function](#Function) fn)

方法

1.2.6.1

移除事件监听器

所属模块： [UE](#UE)

所属类： [UE.EventBase](#UE.EventBase)

参数列表

参数名

类型

描述

types

[String](#String)

移除的事件名称，同时移除多个事件使用空格分隔

fn

[Function](#Function)

移除监听事件的函数引用

示例

javascript代码：

1
2

 //changeCallback为方法体
 editor.removeListener("selectionchange",changeCallback);

#### fireEvent([String](#String) types)

方法

1.2.6.1

触发事件

*   提示： 该方法会触发addListener

所属模块： [UE](#UE)

所属类： [UE.EventBase](#UE.EventBase)

参数列表

参数名

类型

描述

types

[String](#String)

触发的事件名称，同时触发多个事件使用空格分隔

返回值

类型

描述

[\*](#*)

返回触发事件的队列中，最后执行的回调函数的返回值

示例

javascript代码：

1

 editor.fireEvent("selectionchange");

#### fireEvent([String](#String) types, [\*...](#*...) options)

方法

1.2.6.1

触发事件

所属模块： [UE](#UE)

所属类： [UE.EventBase](#UE.EventBase)

参数列表

参数名

类型

描述

types

[String](#String)

触发的事件名称，同时触发多个事件使用空格分隔

options

[\*...](#*...)

可选参数，可以传入一个或多个参数，会传给事件触发的回调函数

返回值

类型

描述

[\*](#*)

返回触发事件的队列中，最后执行的回调函数的返回值

示例

javascript代码：

1
2
3
4
5
6
7
8
9

 editor.addListener( "selectionchange", function ( type, arg1, arg2 ) {

     console.log( arg1 + " " + arg2 );

 } );

 //触发selectionchange事件， 会执行上面的事件监听器
 //output: Hello World
 editor.fireEvent("selectionchange", "Hello", "World");

### uNode

类

编辑器模拟的节点类

所属模块： [UE](#UE)

构造器列表

方法签名

描述

[uNode(Object attr)](#UE.uNode:uNode(Object))

通过一个键值对，创建一个uNode对象

方法列表

方法签名

静态

描述

[toHtml()](#UE.uNode:toHtml())

否

当前节点对象，转换成html文本

[toHtml(Boolean formatter)](#UE.uNode:toHtml(Boolean))

否

当前节点对象，转换成html文本

[innerHTML()](#UE.uNode:innerHTML())

否

获取节点的html内容

[innerHTML(String htmlstr)](#UE.uNode:innerHTML(String))

否

设置节点的html内容

[innerText()](#UE.uNode:innerText())

否

获取节点的纯文本内容

[innerText(String textStr)](#UE.uNode:innerText(String))

否

设置节点的纯文本内容

[getData()](#UE.uNode:getData())

否

获取当前对象的data属性

[firstChild()](#UE.uNode:firstChild())

否

获取当前节点下的第一个子节点

[lastChild()](#UE.uNode:lastChild())

否

获取当前节点下的最后一个子节点

[previousSibling()](#UE.uNode:previousSibling())

否

获取和当前节点有相同父亲节点的前一个节点

[nextSibling()](#UE.uNode:nextSibling())

否

获取和当前节点有相同父亲节点的后一个节点

[replaceChild(UE.uNode target, UE.uNode source)](#UE.uNode:replaceChild(UE.uNode,UE.uNode))

否

用新的节点替换当前节点

[appendChild(UE.uNode node)](#UE.uNode:appendChild(UE.uNode))

否

在节点的子节点列表最后位置插入一个节点

[insertBefore(UE.uNode target, UE.uNode source)](#UE.uNode:insertBefore(UE.uNode,UE.uNode))

否

在传入节点的前面插入一个节点

[insertAfter(UE.uNode target, UE.uNode source)](#UE.uNode:insertAfter(UE.uNode,UE.uNode))

否

在传入节点的后面插入一个节点

[removeChild(UE.uNode node, Boolean keepChildren)](#UE.uNode:removeChild(UE.uNode,Boolean))

否

从当前节点的子节点列表中，移除节点

[getAttr(String attrName)](#UE.uNode:getAttr(String))

否

获取当前节点所代表的元素属性，即获取attrs对象下的属性值

[setAttr(String attrName, \* attrVal)](#UE.uNode:setAttr(String,*))

否

设置当前节点所代表的元素属性，即设置attrs对象下的属性值

[getIndex()](#UE.uNode:getIndex())

否

获取当前节点在父节点下的位置索引

[getNodeById(String id)](#UE.uNode:getNodeById(String))

否

在当前节点下，根据id查找节点

[getNodesByTagName(String tagNames)](#UE.uNode:getNodesByTagName(String))

否

在当前节点下，根据元素名称查找节点列表

[getStyle(String name)](#UE.uNode:getStyle(String))

否

根据样式名称，获取节点的样式值

[setStyle(String name, String val)](#UE.uNode:setStyle(String,String))

否

给节点设置样式

[traversal(Function fn)](#UE.uNode:traversal(Function))

否

传入一个函数，递归遍历当前节点下的所有节点

类成员详细描述([uNode](#UE.uNode))

#### uNode([Object](#Object) attr)

构造器

1.2.6.1

通过一个键值对，创建一个uNode对象

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

attr

[Object](#Object)

传入要创建的uNode的初始属性

示例

javascript代码：

1
2
3
4
5

 var node \= new uNode({
     type:'element',
     tagName:'span',
     attrs:{style:'font-size:14px;'}
 }

#### toHtml()

方法

1.2.6.1

当前节点对象，转换成html文本

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

返回值

类型

描述

[String](#String)

返回转换后的html字符串

示例

javascript代码：

1

 node.toHtml();

#### toHtml([Boolean](#Boolean) formatter)

方法

1.2.6.1

当前节点对象，转换成html文本

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

formatter

[Boolean](#Boolean)

是否格式化返回值

返回值

类型

描述

[String](#String)

返回转换后的html字符串

示例

javascript代码：

1

 node.toHtml( true );

#### innerHTML()

方法

1.2.6.1

获取节点的html内容

*   警告： 假如节点的type不是'element'，或节点的标签名称不在dtd列表里，直接返回当前节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

返回值

类型

描述

[String](#String)

返回节点的html内容

示例

javascript代码：

1

 var htmlstr \= node.innerHTML();

#### innerHTML([String](#String) htmlstr)

方法

1.2.6.1

设置节点的html内容

*   警告： 假如节点的type不是'element'，或节点的标签名称不在dtd列表里，直接返回当前节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

htmlstr

[String](#String)

传入要设置的html内容

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回节点本身

示例

javascript代码：

1

 node.innerHTML('<span>text</span>');

#### innerText()

方法

1.2.6.1

获取节点的纯文本内容

*   警告： 假如节点的type不是'element'，或节点的标签名称不在dtd列表里，直接返回当前节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

返回值

类型

描述

[String](#String)

返回节点的存文本内容

示例

javascript代码：

1

 var textStr \= node.innerText();

#### innerText([String](#String) textStr)

方法

1.2.6.1

设置节点的纯文本内容

*   警告： 假如节点的type不是'element'，或节点的标签名称不在dtd列表里，直接返回当前节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

textStr

[String](#String)

传入要设置的文本内容

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回节点本身

示例

javascript代码：

1

 node.innerText('<span>text</span>');

#### getData()

方法

1.2.6.1

获取当前对象的data属性

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

返回值

类型

描述

[Object](#Object)

若节点的type值是elemenet，返回空字符串，否则返回节点的data属性

示例

javascript代码：

1

 node.getData();

#### firstChild()

方法

1.2.6.1

获取当前节点下的第一个子节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回第一个子节点

示例

javascript代码：

1

 node.firstChild(); //返回第一个子节点

#### lastChild()

方法

1.2.6.1

获取当前节点下的最后一个子节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回最后一个子节点

示例

javascript代码：

1

 node.lastChild(); //返回最后一个子节点

#### previousSibling()

方法

1.2.6.1

获取和当前节点有相同父亲节点的前一个节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回前一个节点

示例

javascript代码：

1

 node.children\[2\].previousSibling(); //返回子节点node.children\[1\]

#### nextSibling()

方法

1.2.6.1

获取和当前节点有相同父亲节点的后一个节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回后一个节点,找不到返回null

示例

javascript代码：

1

 node.children\[2\].nextSibling(); //如果有，返回子节点node.children\[3\]

#### replaceChild([UE.uNode](#UE.uNode) target, [UE.uNode](#UE.uNode) source)

方法

1.2.6.1

用新的节点替换当前节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

target

[UE.uNode](#UE.uNode)

要替换成该节点参数

source

[UE.uNode](#UE.uNode)

要被替换掉的节点

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回替换之后的节点对象

示例

javascript代码：

1

 node.replaceChild(newNode, childNode); //用newNode替换childNode,childNode是node的子节点

#### appendChild([UE.uNode](#UE.uNode) node)

方法

1.2.6.1

在节点的子节点列表最后位置插入一个节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

node

[UE.uNode](#UE.uNode)

要插入的节点

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回刚插入的子节点

示例

javascript代码：

1

 node.appendChild( newNode ); //在node内插入子节点newNode

#### insertBefore([UE.uNode](#UE.uNode) target, [UE.uNode](#UE.uNode) source)

方法

1.2.6.1

在传入节点的前面插入一个节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

target

[UE.uNode](#UE.uNode)

要插入的节点

source

[UE.uNode](#UE.uNode)

在该参数节点前面插入

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回刚插入的子节点

示例

javascript代码：

1

 node.parentNode.insertBefore(newNode, node); //在node节点后面插入newNode

#### insertAfter([UE.uNode](#UE.uNode) target, [UE.uNode](#UE.uNode) source)

方法

1.2.6.1

在传入节点的后面插入一个节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

target

[UE.uNode](#UE.uNode)

要插入的节点

source

[UE.uNode](#UE.uNode)

在该参数节点后面插入

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回刚插入的子节点

示例

javascript代码：

1

 node.parentNode.insertAfter(newNode, node); //在node节点后面插入newNode

#### removeChild([UE.uNode](#UE.uNode) node, [Boolean](#Boolean) keepChildren)

方法

1.2.6.1

从当前节点的子节点列表中，移除节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

node

[UE.uNode](#UE.uNode)

要移除的节点引用

keepChildren

[Boolean](#Boolean)

是否保留移除节点的子节点，若传入true，自动把移除节点的子节点插入到移除的位置

返回值

类型

描述

[\*](#*)

返回刚移除的子节点

示例

javascript代码：

1

 node.removeChild(childNode,true); //在node的子节点列表中移除child节点，并且吧child的子节点插入到移除的位置

#### getAttr([String](#String) attrName)

方法

1.2.6.1

获取当前节点所代表的元素属性，即获取attrs对象下的属性值

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

attrName

[String](#String)

要获取的属性名称

返回值

类型

描述

[\*](#*)

返回attrs对象下的属性值

示例

javascript代码：

1

 node.getAttr('title');

#### setAttr([String](#String) attrName, [\*](#*) attrVal)

方法

1.2.6.1

设置当前节点所代表的元素属性，即设置attrs对象下的属性值

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

attrName

[String](#String)

要设置的属性名称

attrVal

[\*](#*)

要设置的属性值，类型视设置的属性而定

返回值

类型

描述

[\*](#*)

返回attrs对象下的属性值

示例

javascript代码：

1

 node.setAttr('title','标题');

#### getIndex()

方法

1.2.6.1

获取当前节点在父节点下的位置索引

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

返回值

类型

描述

[Number](#Number)

返回索引数值，如果没有父节点，返回-1

示例

javascript代码：

1

 node.getIndex();

#### getNodeById([String](#String) id)

方法

1.2.6.1

在当前节点下，根据id查找节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

id

[String](#String)

要查找的id

返回值

类型

描述

[UE.uNode](#UE.uNode)

返回找到的节点

示例

javascript代码：

1

 node.getNodeById('textId');

#### getNodesByTagName([String](#String) tagNames)

方法

1.2.6.1

在当前节点下，根据元素名称查找节点列表

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

tagNames

[String](#String)

要查找的元素名称

返回值

类型

描述

[Array](#Array)

返回找到的节点列表

示例

javascript代码：

1

 node.getNodesByTagName('span');

#### getStyle([String](#String) name)

方法

1.2.6.1

根据样式名称，获取节点的样式值

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

name

[String](#String)

要获取的样式名称

返回值

类型

描述

[String](#String)

返回样式值

示例

javascript代码：

1

 node.getStyle('font-size');

#### setStyle([String](#String) name, [String](#String) val)

方法

1.2.6.1

给节点设置样式

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

name

[String](#String)

要设置的的样式名称

val

[String](#String)

要设置的的样值

示例

javascript代码：

1

 node.setStyle('font-size', '12px');

#### traversal([Function](#Function) fn)

方法

1.2.6.1

传入一个函数，递归遍历当前节点下的所有节点

所属模块： [UE](#UE)

所属类： [UE.uNode](#UE.uNode)

参数列表

参数名

类型

描述

fn

[Function](#Function)

遍历到节点的时，传入节点作为参数，运行此函数

示例

javascript代码：

1
2
3

 traversal(node, function(){
     console.log(node.type);
 });

UE.dom
------

模块

dom操作封装

类列表

类名

描述

[Range](#UE.dom.Range)

Range实现类，本类是UEditor底层核心类，封装不同浏览器之间的Range操作。

[Selection](#UE.dom.Selection)

选区集合

模块成员详细描述([UE.dom](#UE.dom))

### Range

类

Range实现类，本类是UEditor底层核心类，封装不同浏览器之间的Range操作。

所属模块： [UE.dom](#UE.dom)

属性列表

属性名

类型

静态

描述

[startContainer](#UE.dom.Range:startContainer)

Node

否

当前Range的开始边界的容器节点, 可以是一个元素节点或者是文本节点

[startOffset](#UE.dom.Range:startOffset)

Node

否

当前Range的开始边界容器节点的偏移量, 如果是元素节点， 该值就是childNodes中的第几个节点， 如果是文本节点就是文本内容的第几个字符

[endContainer](#UE.dom.Range:endContainer)

Node

否

当前Range的结束边界的容器节点, 可以是一个元素节点或者是文本节点

[endOffset](#UE.dom.Range:endOffset)

Node

否

当前Range的结束边界容器节点的偏移量, 如果是元素节点， 该值就是childNodes中的第几个节点， 如果是文本节点就是文本内容的第几个字符

[collapsed](#UE.dom.Range:collapsed)

Boolean

否

当前Range是否闭合

[document](#UE.dom.Range:document)

Document

否

当前Range所属的Document对象

构造器列表

方法签名

描述

[Range(Document document)](#UE.dom.Range:Range(Document))

创建一个跟document绑定的空的Range实例

方法列表

方法签名

静态

描述

[cloneContents()](#UE.dom.Range:cloneContents())

否

克隆选区的内容到一个DocumentFragment里

[deleteContents()](#UE.dom.Range:deleteContents())

否

删除当前选区范围中的所有内容

[extractContents()](#UE.dom.Range:extractContents())

否

将当前选区的内容提取到一个DocumentFragment里

[setStart(Node node, int offset)](#UE.dom.Range:setStart(Node,int))

否

设置Range的开始容器节点和偏移量

[setEnd(Node node, int offset)](#UE.dom.Range:setEnd(Node,int))

否

设置Range的结束容器和偏移量

[setStartAfter(Node node)](#UE.dom.Range:setStartAfter(Node))

否

将Range开始位置设置到node节点之后

[setStartBefore(Node node)](#UE.dom.Range:setStartBefore(Node))

否

将Range开始位置设置到node节点之前

[setEndAfter(Node node)](#UE.dom.Range:setEndAfter(Node))

否

将Range结束位置设置到node节点之后

[setEndBefore(Node node)](#UE.dom.Range:setEndBefore(Node))

否

将Range结束位置设置到node节点之前

[setStartAtFirst(Node node)](#UE.dom.Range:setStartAtFirst(Node))

否

设置Range的开始位置到node节点内的第一个子节点之前

[setStartAtLast(Node node)](#UE.dom.Range:setStartAtLast(Node))

否

设置Range的开始位置到node节点内的最后一个节点之后

[setEndAtFirst(Node node)](#UE.dom.Range:setEndAtFirst(Node))

否

设置Range的结束位置到node节点内的第一个节点之前

[setEndAtLast(Node node)](#UE.dom.Range:setEndAtLast(Node))

否

设置Range的结束位置到node节点内的最后一个节点之后

[selectNode(Node node)](#UE.dom.Range:selectNode(Node))

否

选中给定节点

[selectNodeContents(Node node)](#UE.dom.Range:selectNodeContents(Node))

否

选中给定节点内部的所有节点

[cloneRange()](#UE.dom.Range:cloneRange())

否

clone当前Range对象

[collapse()](#UE.dom.Range:collapse())

否

向当前选区的结束处闭合选区

[collapse(Boolean toStart)](#UE.dom.Range:collapse(Boolean))

否

闭合当前选区，根据给定的toStart参数项决定是向当前选区开始处闭合还是向结束处闭合， 如果toStart的值为true，则向开始位置闭合， 反之，向结束位置闭合。

[shrinkBoundary()](#UE.dom.Range:shrinkBoundary())

否

调整range的开始位置和结束位置，使其"收缩"到最小的位置

[shrinkBoundary(Boolean ignoreEnd)](#UE.dom.Range:shrinkBoundary(Boolean))

否

调整range的开始位置和结束位置，使其"收缩"到最小的位置， 如果ignoreEnd的值为true，则忽略对结束位置的调整

[getCommonAncestor()](#UE.dom.Range:getCommonAncestor())

否

获取离当前选区内包含的所有节点最近的公共祖先节点，

[getCommonAncestor(Boolean includeSelf)](#UE.dom.Range:getCommonAncestor(Boolean))

否

获取当前选区所包含的所有节点的公共祖先节点， 可以根据给定的参数 includeSelf 决定获取到 的公共祖先节点是否可以是当前选区的startContainer或endContainer节点， 如果 includeSelf 的取值为true， 则返回的节点可以是自身的容器节点， 否则， 则不能是容器节点

[getCommonAncestor(Boolean includeSelf, Boolean ignoreTextNode)](#UE.dom.Range:getCommonAncestor(Boolean,Boolean))

否

获取当前选区所包含的所有节点的公共祖先节点， 可以根据给定的参数 includeSelf 决定获取到 的公共祖先节点是否可以是当前选区的startContainer或endContainer节点， 如果 includeSelf 的取值为true， 则返回的节点可以是自身的容器节点， 否则， 则不能是容器节点； 同时可以根据 ignoreTextNode 参数的取值决定是否忽略类型为文本节点的祖先节点。

[trimBoundary()](#UE.dom.Range:trimBoundary())

否

调整当前Range的开始和结束边界容器，如果是容器节点是文本节点,就调整到包含该文本节点的父节点上

[trimBoundary(Boolean ignoreEnd)](#UE.dom.Range:trimBoundary(Boolean))

否

调整当前Range的开始和结束边界容器，如果是容器节点是文本节点,就调整到包含该文本节点的父节点上， 可以根据 ignoreEnd 参数的值决定是否调整对结束边界的调整

[txtToElmBoundary()](#UE.dom.Range:txtToElmBoundary())

否

如果选区在文本的边界上，就扩展选区到文本的父节点上, 如果当前选区是闭合的， 则什么也不做

[txtToElmBoundary(Boolean ignoreCollapsed)](#UE.dom.Range:txtToElmBoundary(Boolean))

否

如果选区在文本的边界上，就扩展选区到文本的父节点上, 如果当前选区是闭合的， 则根据参数项 ignoreCollapsed 的值决定是否执行该调整

[insertNode(Node node)](#UE.dom.Range:insertNode(Node))

否

在当前选区的开始位置前插入节点，新插入的节点会被该range包含

[setCursor()](#UE.dom.Range:setCursor())

否

闭合选区到当前选区的开始位置， 并且定位光标到闭合后的位置

[setCursor(Boolean toEnd)](#UE.dom.Range:setCursor(Boolean))

否

闭合选区，可以根据参数toEnd的值控制选区是向前闭合还是向后闭合， 并且定位光标到闭合后的位置。

[createBookmark(Boolean serialize)](#UE.dom.Range:createBookmark(Boolean))

否

创建当前range的一个书签，记录下当前range的位置，方便当dom树改变时，还能找回原来的选区位置

[moveToBookmark(BookMark bookmark)](#UE.dom.Range:moveToBookmark(BookMark))

否

调整当前range的边界到书签位置，并删除该书签对象所标记的位置内的节点

[enlarge()](#UE.dom.Range:enlarge())

否

调整range的边界，使其"放大"到最近的父节点

[enlarge(Boolean toBlock)](#UE.dom.Range:enlarge(Boolean))

否

调整range的边界，使其"放大"到最近的父节点，根据参数 toBlock 的取值， 可以 要求扩大之后的父节点是block节点

[adjustmentBoundary()](#UE.dom.Range:adjustmentBoundary())

否

调整Range的边界，使其"缩小"到最合适的位置

[applyInlineStyle(String tagName)](#UE.dom.Range:applyInlineStyle(String))

否

给range选区中的内容添加给定的inline标签

[applyInlineStyle(String tagName, Object attrs)](#UE.dom.Range:applyInlineStyle(String,Object))

否

给range选区中的内容添加给定的inline标签， 并且为标签附加上一些初始化属性。

[removeInlineStyle(String tagName)](#UE.dom.Range:removeInlineStyle(String))

否

移除当前选区内指定的inline标签，但保留其中的内容

[removeInlineStyle(Array tagNameArr)](#UE.dom.Range:removeInlineStyle(Array))

否

移除当前选区内指定的一组inline标签，但保留其中的内容

[getClosedNode()](#UE.dom.Range:getClosedNode())

否

获取当前选中的自闭合的节点

[select()](#UE.dom.Range:select())

否

在页面上高亮range所表示的选区

[scrollToView(Window win)](#UE.dom.Range:scrollToView(Window))

否

滚动到当前range开始的位置

[scrollToView(Window win, Number offset)](#UE.dom.Range:scrollToView(Window,Number))

否

滚动到距离当前range开始位置 offset 的位置处

[equals()](#UE.dom.Range:equals())

否

判断给定的Range对象是否和当前Range对象表示的是同一个选区

[traversal(Function doFn)](#UE.dom.Range:traversal(Function))

否

遍历range内的节点。每当遍历一个节点时， 都会执行参数项 doFn 指定的函数， 该函数的接受当前遍历的节点 作为其参数。

[traversal(Function doFn, Function filterFn)](#UE.dom.Range:traversal(Function,Function))

否

遍历range内的节点。 每当遍历一个节点时， 都会执行参数项 doFn 指定的函数， 该函数的接受当前遍历的节点 作为其参数。 可以通过参数项 filterFn 来指定一个过滤器， 只有符合该过滤器过滤规则的节点才会触 发doFn函数的执行

类成员详细描述([Range](#UE.dom.Range))

#### startContainer

属性

1.2.6.1

当前Range的开始边界的容器节点, 可以是一个元素节点或者是文本节点

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

类型

默认值

描述

Node

无

当前Range的开始边界的容器节点, 可以是一个元素节点或者是文本节点

#### startOffset

属性

1.2.6.1

当前Range的开始边界容器节点的偏移量, 如果是元素节点， 该值就是childNodes中的第几个节点， 如果是文本节点就是文本内容的第几个字符

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

类型

默认值

描述

Node

无

当前Range的开始边界容器节点的偏移量, 如果是元素节点， 该值就是childNodes中的第几个节点， 如果是文本节点就是文本内容的第几个字符

#### endContainer

属性

1.2.6.1

当前Range的结束边界的容器节点, 可以是一个元素节点或者是文本节点

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

类型

默认值

描述

Node

无

当前Range的结束边界的容器节点, 可以是一个元素节点或者是文本节点

#### endOffset

属性

1.2.6.1

当前Range的结束边界容器节点的偏移量, 如果是元素节点， 该值就是childNodes中的第几个节点， 如果是文本节点就是文本内容的第几个字符

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

类型

默认值

描述

Node

无

当前Range的结束边界容器节点的偏移量, 如果是元素节点， 该值就是childNodes中的第几个节点， 如果是文本节点就是文本内容的第几个字符

#### collapsed

属性

1.2.6.1

当前Range是否闭合

*   提示： Range是闭合的时候， startContainer === endContainer && startOffset === endOffset

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

类型

默认值

描述

Boolean

true

当前Range是否闭合

#### document

属性

1.2.6.1

当前Range所属的Document对象

*   提示： 不同range的的document属性可以是不同的

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

类型

默认值

描述

Document

无

当前Range所属的Document对象

#### Range([Document](#Document) document)

构造器

1.2.6.1

创建一个跟document绑定的空的Range实例

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

document

[Document](#Document)

新建的选区所属的文档对象

#### cloneContents()

方法

1.2.6.1

克隆选区的内容到一个DocumentFragment里

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[DocumentFragment | NULL](#DocumentFragment | NULL)

如果选区是闭合的将返回null， 否则， 返回包含所clone内容的DocumentFragment元素

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16

 <body>
      <!-- 中括号表示选区 -->
      <b>x<i>x\[x</i>xx\]x</b>

      <script>
          //range是已选中的选区
          var fragment \= range.cloneContents(),
              node \= document.createElement("div");

          node.appendChild( fragment );

          //output: <i>x</i>xx
          console.log( node.innerHTML );

      </script>
 </body>

#### deleteContents()

方法

1.2.6.1

删除当前选区范围中的所有内容

*   提示： 执行完该操作后， 当前Range对象变成了闭合状态

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前操作的Range对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26

 <body>
      <!-- 中括号表示选区 -->
      <b>x<i>x\[x</i>xx\]x</b>

      <script>
          //range是已选中的选区
          range.deleteContents();

          //竖线表示闭合后的选区位置
          //output: <b>x<i>x</i>|x</b>
          console.log( document.body.innerHTML );

          //此时， range的各项属性为
          //output: B
          console.log( range.startContainer.tagName );
          //output: 2
          console.log( range.startOffset );
          //output: B
          console.log( range.endContainer.tagName );
          //output: 2
          console.log( range.endOffset );
          //output: true
          console.log( range.collapsed );

      </script>
 </body>

#### extractContents()

方法

1.2.6.1

将当前选区的内容提取到一个DocumentFragment里

*   提示： 执行该操作后， 选区将变成闭合状态

*   警告： 执行该操作后， 原来选区所选中的内容将从dom树上剥离出来

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[DocumentFragment](#DocumentFragment)

返回包含所提取内容的DocumentFragment对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32

 <body>
      <!-- 中括号表示选区 -->
      <b>x<i>x\[x</i>xx\]x</b>

      <script>
          //range是已选中的选区
          var fragment \= range.extractContents(),
              node \= document.createElement( "div" );

          node.appendChild( fragment );

          //竖线表示闭合后的选区位置

          //output: <b>x<i>x</i>|x</b>
          console.log( document.body.innerHTML );
          //output: <i>x</i>xx
          console.log( node.innerHTML );

          //此时， range的各项属性为
          //output: B
          console.log( range.startContainer.tagName );
          //output: 2
          console.log( range.startOffset );
          //output: B
          console.log( range.endContainer.tagName );
          //output: 2
          console.log( range.endOffset );
          //output: true
          console.log( range.collapsed );

      </script>
 </body>

#### setStart([Node](#Node) node, [int](#int) offset)

方法

1.2.6.1

设置Range的开始容器节点和偏移量

*   提示： 如果给定的节点是元素节点，那么offset指的是其子元素中索引为offset的元素， 如果是文本节点，那么offset指的是其文本内容的第offset个字符

*   提示： 如果提供的容器节点是一个不能包含子元素的节点， 则该选区的开始容器将被设置 为该节点的父节点， 此时， 其距离开始容器的偏移量也变成了该节点在其父节点 中的索引

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

node

[Node](#Node)

将被设为当前选区开始边界容器的节点对象

offset

[int](#int)

选区的开始位置偏移量

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <!-- 选区 -->
 <b>xxx<i>x<span>xx</span>xx<em>xx</em>xxx</i>\[xxx\]</b>

 <script>

     //执行操作
     range.setStart( document.getElementsByTagName("i")\[0\], 1 );

     //此时， 选区变成了
     //<b>xxx<i>x\[<span>xx</span>xx<em>xx</em>xxx</i>xxx\]</b>

 </script>

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <!-- 选区 -->
 <b>xxx<img>\[xx\]x</b>

 <script>

     //执行操作
     range.setStart( document.getElementsByTagName("img")\[0\], 3 );

     //此时， 选区变成了
     //<b>xxx\[<img>xx\]x</b>

 </script>

#### setEnd([Node](#Node) node, [int](#int) offset)

方法

1.2.6.1

设置Range的结束容器和偏移量

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:setStart(Node,int)](#UE.dom.Range:setStart(Node,int))

参数列表

参数名

类型

描述

node

[Node](#Node)

作为当前选区结束边界容器的节点对象

offset

[int](#int)

结束边界的偏移量

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### setStartAfter([Node](#Node) node)

方法

1.2.6.1

将Range开始位置设置到node节点之后

*   提示： 该操作将会把给定节点的父节点作为range的开始容器， 且偏移量是该节点在其父节点中的位置索引+1

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

node

[Node](#Node)

选区的开始边界将紧接着该节点之后

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <!-- 选区示例 -->
 <b>xx<i>xxx</i><span>xx\[x</span>xxx\]</b>

 <script>

     //执行操作
     range.setStartAfter( document.getElementsByTagName("i")\[0\] );

     //结果选区
     //<b>xx<i>xxx</i>\[<span>xxx</span>xxx\]</b>

 </script>

#### setStartBefore([Node](#Node) node)

方法

1.2.6.1

将Range开始位置设置到node节点之前

*   提示： 该操作将会把给定节点的父节点作为range的开始容器， 且偏移量是该节点在其父节点中的位置索引

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:setStartAfter(Node)](#UE.dom.Range:setStartAfter(Node))

参数列表

参数名

类型

描述

node

[Node](#Node)

新的选区开始位置在该节点之前

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### setEndAfter([Node](#Node) node)

方法

1.2.6.1

将Range结束位置设置到node节点之后

*   提示： 该操作将会把给定节点的父节点作为range的结束容器， 且偏移量是该节点在其父节点中的位置索引+1

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:setStartAfter(Node)](#UE.dom.Range:setStartAfter(Node))

参数列表

参数名

类型

描述

node

[Node](#Node)

目标节点

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <!-- 选区示例 -->
 <b>\[xx<i>xxx</i><span>xx\]x</span>xxx</b>

 <script>

     //执行操作
     range.setStartAfter( document.getElementsByTagName("span")\[0\] );

     //结果选区
     //<b>\[xx<i>xxx</i><span>xxx</span>\]xxx</b>

 </script>

#### setEndBefore([Node](#Node) node)

方法

1.2.6.1

将Range结束位置设置到node节点之前

*   提示： 该操作将会把给定节点的父节点作为range的结束容器， 且偏移量是该节点在其父节点中的位置索引

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:setEndAfter(Node)](#UE.dom.Range:setEndAfter(Node))

参数列表

参数名

类型

描述

node

[Node](#Node)

目标节点

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### setStartAtFirst([Node](#Node) node)

方法

1.2.6.1

设置Range的开始位置到node节点内的第一个子节点之前

*   提示： 选区的开始容器将变成给定的节点， 且偏移量为0

*   提示： 如果给定的节点是元素节点， 则该节点必须是允许包含子节点的元素。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:setStartBefore(Node)](#UE.dom.Range:setStartBefore(Node))

参数列表

参数名

类型

描述

node

[Node](#Node)

目标节点

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <!-- 选区示例 -->
 <b>xx<i>xxx</i><span>\[xx\]x</span>xxx</b>

 <script>

     //执行操作
     range.setStartAtFirst( document.getElementsByTagName("i")\[0\] );

     //结果选区
     //<b>xx<i>\[xxx</i><span>xx\]x</span>xxx</b>

 </script>

#### setStartAtLast([Node](#Node) node)

方法

1.2.6.1

设置Range的开始位置到node节点内的最后一个节点之后

*   提示： 选区的开始容器将变成给定的节点， 且偏移量为该节点的子节点数

*   提示： 如果给定的节点是元素节点， 则该节点必须是允许包含子节点的元素。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:setStartAtFirst(Node)](#UE.dom.Range:setStartAtFirst(Node))

参数列表

参数名

类型

描述

node

[Node](#Node)

目标节点

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### setEndAtFirst([Node](#Node) node)

方法

1.2.6.1

设置Range的结束位置到node节点内的第一个节点之前

*   提示： 选区的结束容器将变成给定的节点， 且偏移量为0

*   提示： node必须是一个元素节点， 且必须是允许包含子节点的元素。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:setStartAtFirst(Node)](#UE.dom.Range:setStartAtFirst(Node))

参数列表

参数名

类型

描述

node

[Node](#Node)

目标节点

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### setEndAtLast([Node](#Node) node)

方法

1.2.6.1

设置Range的结束位置到node节点内的最后一个节点之后

*   提示： 选区的结束容器将变成给定的节点， 且偏移量为该节点的子节点数量

*   提示： node必须是一个元素节点， 且必须是允许包含子节点的元素。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:setStartAtFirst(Node)](#UE.dom.Range:setStartAtFirst(Node))

参数列表

参数名

类型

描述

node

[Node](#Node)

目标节点

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### selectNode([Node](#Node) node)

方法

1.2.6.1

选中给定节点

*   提示： 此时， 选区的开始容器和结束容器都是该节点的父节点， 其startOffset是该节点在父节点中的位置索引， 而endOffset为startOffset+1

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要选中的节点

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象，此时的range仅包含当前给定的节点对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <!-- 选区示例 -->
 <b>xx<i>xxx</i><span>\[xx\]x</span>xxx</b>

 <script>

     //执行操作
     range.selectNode( document.getElementsByTagName("i")\[0\] );

     //结果选区
     //<b>xx\[<i>xxx</i>\]<span>xxx</span>xxx</b>

 </script>

#### selectNodeContents([Node](#Node) node)

方法

1.2.6.1

选中给定节点内部的所有节点

*   提示： 此时， 选区的开始容器和结束容器都是该节点， 其startOffset为0， 而endOffset是该节点的子节点数。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

node

[Node](#Node)

目标节点， 当前range将包含该节点内的所有节点

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象， 此时range仅包含给定节点的所有子节点

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <!-- 选区示例 -->
 <b>xx<i>xxx</i><span>\[xx\]x</span>xxx</b>

 <script>

     //执行操作
     range.selectNode( document.getElementsByTagName("b")\[0\] );

     //结果选区
     //<b>\[xx<i>xxx</i><span>xxx</span>xxx\]</b>

 </script>

#### cloneRange()

方法

1.2.6.1

clone当前Range对象

*   提示： 返回的range是一个全新的range对象， 其内部所有属性与当前被clone的range相同。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象的一个副本

#### collapse()

方法

1.2.6.1

向当前选区的结束处闭合选区

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13

 <!-- 选区示例 -->
 <b>xx<i>xxx</i><span>\[xx\]x</span>xxx</b>

 <script>

     //执行操作
     range.collapse();

     //结果选区
     //“|”表示选区已闭合
     //<b>xx<i>xxx</i><span>xx|x</span>xxx</b>

 </script>

#### collapse([Boolean](#Boolean) toStart)

方法

1.2.6.1

闭合当前选区，根据给定的toStart参数项决定是向当前选区开始处闭合还是向结束处闭合， 如果toStart的值为true，则向开始位置闭合， 反之，向结束位置闭合。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:collapse()](#UE.dom.Range:collapse())

参数列表

参数名

类型

描述

toStart

[Boolean](#Boolean)

是否向选区开始处闭合

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象，此时range对象处于闭合状态

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13

 <!-- 选区示例 -->
 <b>xx<i>xxx</i><span>\[xx\]x</span>xxx</b>

 <script>

     //执行操作
     range.collapse( true );

     //结果选区
     //“|”表示选区已闭合
     //<b>xx<i>xxx</i><span>|xxx</span>xxx</b>

 </script>

#### shrinkBoundary()

方法

1.2.6.1

调整range的开始位置和结束位置，使其"收缩"到最小的位置

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

示例

html代码：

1

 <span>xx<b>xx\[</b>xxxxx\]</span> => <span>xx<b>xx</b>\[xxxxx\]</span>

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 <!-- 选区示例 -->
 <b>x\[xx</b><i>\]xxx</i>

 <script>

     //执行收缩
     range.shrinkBoundary();

     //结果选区
     //<b>x\[xx\]</b><i>xxx</i>
 </script>

html代码：

1

 \[<b><i>xxxx</i>xxxxxxx</b>\] => <b><i>\[xxxx</i>xxxxxxx\]</b>

#### shrinkBoundary([Boolean](#Boolean) ignoreEnd)

方法

1.2.6.1

调整range的开始位置和结束位置，使其"收缩"到最小的位置， 如果ignoreEnd的值为true，则忽略对结束位置的调整

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.domUtils.Range:shrinkBoundary()](#UE.dom.domUtils.Range:shrinkBoundary())

参数列表

参数名

类型

描述

ignoreEnd

[Boolean](#Boolean)

是否忽略对结束位置的调整

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### getCommonAncestor()

方法

1.2.6.1

获取离当前选区内包含的所有节点最近的公共祖先节点，

*   提示： 返回的公共祖先节点一定不是range自身的容器节点， 但有可能是一个文本节点

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[Node](#Node)

当前range对象内所有节点的公共祖先节点

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 //选区示例
 <span>xxx<b>x\[x<em>xx\]x</em>xxx</b>xx</span>
 <script>

     var node \= range.getCommonAncestor();

     //公共祖先节点是： b节点
     //输出： B
     console.log(node.tagName);

 </script>

#### getCommonAncestor([Boolean](#Boolean) includeSelf)

方法

1.2.6.1

获取当前选区所包含的所有节点的公共祖先节点， 可以根据给定的参数 includeSelf 决定获取到 的公共祖先节点是否可以是当前选区的startContainer或endContainer节点， 如果 includeSelf 的取值为true， 则返回的节点可以是自身的容器节点， 否则， 则不能是容器节点

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:getCommonAncestor()](#UE.dom.Range:getCommonAncestor())

参数列表

参数名

类型

描述

includeSelf

[Boolean](#Boolean)

是否允许获取到的公共祖先节点是当前range对象的容器节点

返回值

类型

描述

[Node](#Node)

当前range对象内所有节点的公共祖先节点

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16

 <body>

     <!-- 选区示例 -->
     <b>xxx<i>xxxx<span>xx\[x</span>xx\]x</i>xxxxxxx</b>

     <script>

         var node \= range.getCommonAncestor( false );

         //这里的公共祖先节点是B而不是I， 是因为参数限制了获取到的节点不能是容器节点
         //output: B
         console.log( node.tagName );

     </script>

 </body>

#### getCommonAncestor([Boolean](#Boolean) includeSelf, [Boolean](#Boolean) ignoreTextNode)

方法

1.2.6.1

获取当前选区所包含的所有节点的公共祖先节点， 可以根据给定的参数 includeSelf 决定获取到 的公共祖先节点是否可以是当前选区的startContainer或endContainer节点， 如果 includeSelf 的取值为true， 则返回的节点可以是自身的容器节点， 否则， 则不能是容器节点； 同时可以根据 ignoreTextNode 参数的取值决定是否忽略类型为文本节点的祖先节点。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:getCommonAncestor()](#UE.dom.Range:getCommonAncestor())

[UE.dom.Range:getCommonAncestor(Boolean)](#UE.dom.Range:getCommonAncestor(Boolean))

参数列表

参数名

类型

描述

includeSelf

[Boolean](#Boolean)

是否允许获取到的公共祖先节点是当前range对象的容器节点

ignoreTextNode

[Boolean](#Boolean)

获取祖先节点的过程中是否忽略类型为文本节点的祖先节点

返回值

类型

描述

[Node](#Node)

当前range对象内所有节点的公共祖先节点

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15

 <body>

     <!-- 选区示例 -->
     <b>xxx<i>xxxx<span>x\[x\]x</span>xxx</i>xxxxxxx</b>

     <script>

         var node \= range.getCommonAncestor( true, false );

         //output: SPAN
         console.log( node.tagName );

     </script>

 </body>

#### trimBoundary()

方法

1.2.6.1

调整当前Range的开始和结束边界容器，如果是容器节点是文本节点,就调整到包含该文本节点的父节点上

*   提示： 该操作有可能会引起文本节点被切开

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 //选区示例
 <b>xxx<i>\[xxxxx\]</i>xxx</b>

 <script>
     //未调整前， 选区的开始容器和结束都是文本节点
     //执行调整
     range.trimBoundary();

     //调整之后， 容器节点变成了i节点
     //<b>xxx\[<i>xxxxx</i>\]xxx</b>
 </script>

#### trimBoundary([Boolean](#Boolean) ignoreEnd)

方法

1.2.6.1

调整当前Range的开始和结束边界容器，如果是容器节点是文本节点,就调整到包含该文本节点的父节点上， 可以根据 ignoreEnd 参数的值决定是否调整对结束边界的调整

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

ignoreEnd

[Boolean](#Boolean)

是否忽略对结束边界的调整

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 //选区示例
 <b>xxx<i>\[xxxxx\]</i>xxx</b>

 <script>
     //未调整前， 选区的开始容器和结束都是文本节点
     //执行调整
     range.trimBoundary( true );

     //调整之后， 开始容器节点变成了i节点
     //但是， 结束容器没有发生变化
     //<b>xxx\[<i>xxxxx\]</i>xxx</b>
 </script>

#### txtToElmBoundary()

方法

1.2.6.1

如果选区在文本的边界上，就扩展选区到文本的父节点上, 如果当前选区是闭合的， 则什么也不做

*   提示： 该操作不会修改dom节点

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### txtToElmBoundary([Boolean](#Boolean) ignoreCollapsed)

方法

1.2.6.1

如果选区在文本的边界上，就扩展选区到文本的父节点上, 如果当前选区是闭合的， 则根据参数项 ignoreCollapsed 的值决定是否执行该调整

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

ignoreCollapsed

[Boolean](#Boolean)

是否忽略选区的闭合状态， 如果该参数取值为true， 则 不论选区是否闭合， 都会执行该操作， 反之， 则不会对闭合的选区执行该操作

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### insertNode([Node](#Node) node)

方法

1.2.6.1

在当前选区的开始位置前插入节点，新插入的节点会被该range包含

*   提示： 插入的节点可以是一个DocumentFragment依次插入多个节点

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要插入的节点

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### setCursor()

方法

1.2.6.1

闭合选区到当前选区的开始位置， 并且定位光标到闭合后的位置

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:collapse()](#UE.dom.Range:collapse())

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### setCursor([Boolean](#Boolean) toEnd)

方法

1.2.6.1

闭合选区，可以根据参数toEnd的值控制选区是向前闭合还是向后闭合， 并且定位光标到闭合后的位置。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:collapse(Boolean)](#UE.dom.Range:collapse(Boolean))

参数列表

参数名

类型

描述

toEnd

[Boolean](#Boolean)

是否向后闭合， 如果为true， 则闭合选区时， 将向结束容器方向闭合， 反之，则向开始容器方向闭合

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### createBookmark([Boolean](#Boolean) serialize)

方法

1.2.6.1

创建当前range的一个书签，记录下当前range的位置，方便当dom树改变时，还能找回原来的选区位置

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

serialize

[Boolean](#Boolean)

控制返回的标记位置是对当前位置的引用还是ID，如果该值为true，则 返回标记位置的ID， 反之则返回标记位置节点的引用

返回值

类型

描述

[Object](#Object)

返回一个书签记录键值对， 其包含的key有： start => 开始标记的ID或者引用， end => 结束标记的ID或引用， id => 当前标记的类型， 如果为true，则表示 返回的记录的类型为ID， 反之则为引用

#### moveToBookmark([BookMark](#BookMark) bookmark)

方法

1.2.6.1

调整当前range的边界到书签位置，并删除该书签对象所标记的位置内的节点

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:createBookmark(Boolean)](#UE.dom.Range:createBookmark(Boolean))

参数列表

参数名

类型

描述

bookmark

[BookMark](#BookMark)

createBookmark所创建的标签对象

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### enlarge()

方法

1.2.6.1

调整range的边界，使其"放大"到最近的父节点

*   提示： 会引起选区的变化

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### enlarge([Boolean](#Boolean) toBlock)

方法

1.2.6.1

调整range的边界，使其"放大"到最近的父节点，根据参数 toBlock 的取值， 可以 要求扩大之后的父节点是block节点

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

toBlock

[Boolean](#Boolean)

是否要求扩大之后的父节点必须是block节点

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### adjustmentBoundary()

方法

1.2.6.1

调整Range的边界，使其"缩小"到最合适的位置

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:shrinkBoundary()](#UE.dom.Range:shrinkBoundary())

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

#### applyInlineStyle([String](#String) tagName)

方法

1.2.6.1

给range选区中的内容添加给定的inline标签

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

tagName

[String](#String)

需要添加的标签名

示例

html代码：

1

 <p>xxxx\[xxxx\]x</p>  ==>  range.applyInlineStyle("strong")  ==>  <p>xxxx\[<strong>xxxx</strong>\]x</p>

#### applyInlineStyle([String](#String) tagName, [Object](#Object) attrs)

方法

1.2.6.1

给range选区中的内容添加给定的inline标签， 并且为标签附加上一些初始化属性。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

tagName

[String](#String)

需要添加的标签名

attrs

[Object](#Object)

跟随新添加的标签的属性

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前选区

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10

 <p>xxxx\[xxxx\]x</p>

 ==>

 <!-- 执行操作 -->
 range.applyInlineStyle("strong",{"style":"font-size:12px"})

 ==>

 <p>xxxx\[<strong style="font-size:12px"\>xxxx</strong>\]x</p>

#### removeInlineStyle([String](#String) tagName)

方法

1.2.6.1

移除当前选区内指定的inline标签，但保留其中的内容

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

tagName

[String](#String)

需要移除的标签名

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前的range对象

示例

html代码：

1

 xx\[x<span>xxx<em>yyy</em>zz\]z</span>  => range.removeInlineStyle(\["em"\])  => xx\[x<span>xxxyyyzz\]z</span>

#### removeInlineStyle([Array](#Array) tagNameArr)

方法

1.2.6.1

移除当前选区内指定的一组inline标签，但保留其中的内容

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:removeInlineStyle(String)](#UE.dom.Range:removeInlineStyle(String))

参数列表

参数名

类型

描述

tagNameArr

[Array](#Array)

需要移除的标签名的数组

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前的range对象

#### getClosedNode()

方法

1.2.6.1

获取当前选中的自闭合的节点

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[Node | NULL](#Node | NULL)

如果当前选中的是自闭合节点， 则返回该节点， 否则返回NULL

#### select()

方法

1.2.6.1

在页面上高亮range所表示的选区

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

返回当前Range对象

#### scrollToView([Window](#Window) win)

方法

1.2.6.1

滚动到当前range开始的位置

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

win

[Window](#Window)

当前range对象所属的window对象

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前Range对象

#### scrollToView([Window](#Window) win, [Number](#Number) offset)

方法

1.2.6.1

滚动到距离当前range开始位置 offset 的位置处

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

win

[Window](#Window)

当前range对象所属的window对象

offset

[Number](#Number)

距离range开始位置处的偏移量， 如果为正数， 则向下偏移， 反之， 则向上偏移

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前Range对象

#### equals()

方法

1.2.6.1

判断给定的Range对象是否和当前Range对象表示的是同一个选区

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

返回值

类型

描述

[Boolean](#Boolean)

如果给定的Range对象与当前Range对象表示的是同一个选区， 则返回true， 否则返回false

#### traversal([Function](#Function) doFn)

方法

1.2.6.1

遍历range内的节点。每当遍历一个节点时， 都会执行参数项 doFn 指定的函数， 该函数的接受当前遍历的节点 作为其参数。

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参数列表

参数名

类型

描述

doFn

[Function](#Function)

对每个遍历的节点要执行的方法， 该方法接受当前遍历的节点作为其参数

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25

 <body>

     <!-- 选区开始 -->
     <span></span>
     <a></a>
     <!-- 选区结束 -->
 </body>

 <script>

     //output: <span></span><a></a>
     console.log( range.cloneContents() );

     range.traversal( function ( node ) {

         if ( node.nodeType \=== 1 ) {
             node.className \= "test";
         }

     } );

     //output: <span class="test"></span><a class="test"></a>
     console.log( range.cloneContents() );

 </script>

#### traversal([Function](#Function) doFn, [Function](#Function) filterFn)

方法

1.2.6.1

遍历range内的节点。 每当遍历一个节点时， 都会执行参数项 doFn 指定的函数， 该函数的接受当前遍历的节点 作为其参数。 可以通过参数项 filterFn 来指定一个过滤器， 只有符合该过滤器过滤规则的节点才会触 发doFn函数的执行

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Range](#UE.dom.Range)

参考

[UE.dom.Range:traversal(Function)](#UE.dom.Range:traversal(Function))

参数列表

参数名

类型

描述

doFn

[Function](#Function)

对每个遍历的节点要执行的方法， 该方法接受当前遍历的节点作为其参数

filterFn

[Function](#Function)

过滤器， 该函数接受当前遍历的节点作为参数， 如果该节点满足过滤 规则， 请返回true， 该节点会触发doFn， 否则， 请返回false， 则该节点不 会触发doFn。

返回值

类型

描述

[UE.dom.Range](#UE.dom.Range)

当前range对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25

 <body>

     <!-- 选区开始 -->
     <span></span>
     <a></a>
     <!-- 选区结束 -->
 </body>

 <script>

     //output: <span></span><a></a>
     console.log( range.cloneContents() );

     range.traversal( function ( node ) {

         node.className \= "test";

     }, function ( node ) {
          return node.nodeType \=== 1;
     } );

     //output: <span class="test"></span><a class="test"></a>
     console.log( range.cloneContents() );

 </script>

### Selection

类

选区集合

所属模块： [UE.dom](#UE.dom)

方法列表

方法签名

静态

描述

[getNative()](#UE.dom.Selection:getNative())

否

获取原生seleciton对象

[getIERange()](#UE.dom.Selection:getIERange())

否

获得ieRange

[cache()](#UE.dom.Selection:cache())

否

缓存当前选区的range和选区的开始节点

[getStartElementPath()](#UE.dom.Selection:getStartElementPath())

否

获取选区开始位置的父节点到body

[clear()](#UE.dom.Selection:clear())

否

清空缓存

[isFocus()](#UE.dom.Selection:isFocus())

否

编辑器是否得到了选区

[getRange()](#UE.dom.Selection:getRange())

否

获取选区对应的Range

[getStart()](#UE.dom.Selection:getStart())

否

获取开始元素，用于状态反射

[getText()](#UE.dom.Selection:getText())

否

得到选区中的文本

[clearRange()](#UE.dom.Selection:clearRange())

否

清除选区

类成员详细描述([Selection](#UE.dom.Selection))

#### getNative()

方法

1.2.6.1

获取原生seleciton对象

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Selection](#UE.dom.Selection)

返回值

类型

描述

[Object](#Object)

获得selection对象

示例

javascript代码：

1

 editor.selection.getNative();

#### getIERange()

方法

1.2.6.1

获得ieRange

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Selection](#UE.dom.Selection)

返回值

类型

描述

[Object](#Object)

返回ie原生的Range

示例

javascript代码：

1

 editor.selection.getIERange();

#### cache()

方法

1.2.6.1

缓存当前选区的range和选区的开始节点

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Selection](#UE.dom.Selection)

#### getStartElementPath()

方法

1.2.6.1

获取选区开始位置的父节点到body

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Selection](#UE.dom.Selection)

返回值

类型

描述

[Array](#Array)

返回父节点集合

示例

javascript代码：

1

 editor.selection.getStartElementPath();

#### clear()

方法

1.2.6.1

清空缓存

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Selection](#UE.dom.Selection)

#### isFocus()

方法

1.2.6.1

编辑器是否得到了选区

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Selection](#UE.dom.Selection)

#### getRange()

方法

1.2.6.1

获取选区对应的Range

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Selection](#UE.dom.Selection)

返回值

类型

描述

[Object](#Object)

得到Range对象

示例

javascript代码：

1

 editor.selection.getRange();

#### getStart()

方法

1.2.6.1

获取开始元素，用于状态反射

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Selection](#UE.dom.Selection)

返回值

类型

描述

[Element](#Element)

获得开始元素

示例

javascript代码：

1

 editor.selection.getStart();

#### getText()

方法

1.2.6.1

得到选区中的文本

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Selection](#UE.dom.Selection)

返回值

类型

描述

[String](#String)

选区中包含的文本

示例

javascript代码：

1

 editor.selection.getText();

#### clearRange()

方法

1.2.6.1

清除选区

所属模块： [UE.dom](#UE.dom)

所属类： [UE.dom.Selection](#UE.dom.Selection)

示例

javascript代码：

1

 editor.selection.clearRange();

UE.ajax
-------

模块

提供对ajax请求的支持

方法列表

方法签名

静态

描述

[request(URLString url, Object ajaxOptions)](#UE.ajax.request(URLString,Object))

是

根据给定的参数项，向指定的url发起一个ajax请求。 ajax请求完成后，会根据请求结果调用相应回调： 如果请求 成功， 则调用onsuccess回调， 失败则调用 onerror 回调

[request(Object ajaxOptions)](#UE.ajax.request(Object))

是

根据给定的参数项发起一个ajax请求， 参数项里必须包含一个url地址。 ajax请求完成后，会根据请求结果调用相应回调： 如果请求 成功， 则调用onsuccess回调， 失败则调用 onerror 回调。

模块成员详细描述([UE.ajax](#UE.ajax))

#### request([URLString](#URLString) url, [Object](#Object) ajaxOptions)

方法 静态

1.2.6.1

根据给定的参数项，向指定的url发起一个ajax请求。 ajax请求完成后，会根据请求结果调用相应回调： 如果请求 成功， 则调用onsuccess回调， 失败则调用 onerror 回调

所属模块： [UE.ajax](#UE.ajax)

参数列表

参数名

类型

描述

url

[URLString](#URLString)

ajax请求的url地址

ajaxOptions

[Object](#Object)

ajax请求选项的键值对，支持的选项如下：

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28

 //向sayhello.php发起一个异步的Ajax GET请求, 请求超时时间为10s， 请求完成后执行相应的回调。
 UE.ajax.requeset( 'sayhello.php', {

     //请求方法。可选值： 'GET', 'POST'，默认值是'POST'
     method: 'GET',

     //超时时间。 默认为5000， 单位是ms
     timeout: 10000,

     //是否是异步请求。 true为异步请求， false为同步请求
     async: true,

     //请求携带的数据。如果请求为GET请求， data会经过stringify后附加到请求url之后。
     data: {
         name: 'ueditor'
     },

     //请求成功后的回调， 该回调接受当前的XMLHttpRequest对象作为参数。
     onsuccess: function ( xhr ) {
         console.log( xhr.responseText );
     },

     //请求失败或者超时后的回调。
     onerror: function ( xhr ) {
          alert( 'Ajax请求失败' );
     }

 } );

#### request([Object](#Object) ajaxOptions)

方法 静态

1.2.6.1

根据给定的参数项发起一个ajax请求， 参数项里必须包含一个url地址。 ajax请求完成后，会根据请求结果调用相应回调： 如果请求 成功， 则调用onsuccess回调， 失败则调用 onerror 回调。

*   警告： 如果在参数项里未提供一个key为“url”的地址值，则该请求将直接退出。

所属模块： [UE.ajax](#UE.ajax)

参数列表

参数名

类型

描述

ajaxOptions

[Object](#Object)

ajax请求选项的键值对，支持的选项如下：

示例

javascript代码：

1
2
3
4
5
6
7

 //向sayhello.php发起一个异步的Ajax POST请求, 请求超时时间为5s， 请求完成后不执行任何回调。
 UE.ajax.requeset( 'sayhello.php', {

     //请求的地址， 该项是必须的。
     url: 'sayhello.php'

 } );

UE.browser
----------

模块

提供浏览器检测的模块

属性列表

属性名

类型

静态

描述

[ie](#UE.browser.ie)

boolean

是

检测当前浏览器是否为IE

[opera](#UE.browser.opera)

boolean

是

检测当前浏览器是否为Opera

[webkit](#UE.browser.webkit)

boolean

是

检测当前浏览器是否是webkit内核的浏览器

[mac](#UE.browser.mac)

boolean

是

检测当前浏览器是否是运行在mac平台下

[quirks](#UE.browser.quirks)

boolean

是

检测当前浏览器是否处于“怪异模式”下

[gecko](#UE.browser.gecko)

boolean

是

检测当前浏览器内核是否是gecko内核

[ie9Compat](#UE.browser.ie9Compat)

boolean

是

检测浏览器模式是否为 IE9 兼容模式

[ie8](#UE.browser.ie8)

boolean

是

检测浏览器是否是IE8浏览器

[ie8Compat](#UE.browser.ie8Compat)

boolean

是

检测浏览器模式是否为 IE8 兼容模式

[ie7Compat](#UE.browser.ie7Compat)

boolean

是

检测浏览器模式是否为 IE7 兼容模式

[ie6Compat](#UE.browser.ie6Compat)

boolean

是

检测浏览器模式是否为 IE6 模式 或者怪异模式

[chrome](#UE.browser.chrome)

Number

是

检测当前浏览器是否为Chrome, 如果是，则返回Chrome的大版本号

[safari](#UE.browser.safari)

Number

是

检测当前浏览器是否为Safari, 如果是，则返回Safari的大版本号

[version](#UE.browser.version)

Number

是

检测当前浏览器版本号

[isCompatible](#UE.browser.isCompatible)

boolean

是

检测当前浏览器是否能够与UEditor良好兼容

模块成员详细描述([UE.browser](#UE.browser))

#### ie

属性 静态

1.2.6.1

检测当前浏览器是否为IE

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测当前浏览器是否为IE

示例

javascript代码：

1
2
3

 if ( UE.browser.ie ) {
     console.log( '当前浏览器是IE' );
 }

#### opera

属性 静态

1.2.6.1

检测当前浏览器是否为Opera

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测当前浏览器是否为Opera

示例

javascript代码：

1
2
3

 if ( UE.browser.opera ) {
     console.log( '当前浏览器是Opera' );
 }

#### webkit

属性 静态

1.2.6.1

检测当前浏览器是否是webkit内核的浏览器

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测当前浏览器是否是webkit内核的浏览器

示例

javascript代码：

1
2
3

 if ( UE.browser.webkit ) {
     console.log( '当前浏览器是webkit内核浏览器' );
 }

#### mac

属性 静态

1.2.6.1

检测当前浏览器是否是运行在mac平台下

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测当前浏览器是否是运行在mac平台下

示例

javascript代码：

1
2
3

 if ( UE.browser.mac ) {
     console.log( '当前浏览器运行在mac平台下' );
 }

#### quirks

属性 静态

1.2.6.1

检测当前浏览器是否处于“怪异模式”下

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测当前浏览器是否处于“怪异模式”下

示例

javascript代码：

1
2
3

 if ( UE.browser.quirks ) {
     console.log( '当前浏览器运行处于“怪异模式”' );
 }

#### gecko

属性 静态

1.2.6.1

检测当前浏览器内核是否是gecko内核

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测当前浏览器内核是否是gecko内核

示例

javascript代码：

1
2
3

 if ( UE.browser.gecko ) {
     console.log( '当前浏览器内核是gecko内核' );
 }

#### ie9Compat

属性 静态

1.2.6.1

检测浏览器模式是否为 IE9 兼容模式

*   警告： 如果浏览器不是IE， 则该值为undefined

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测浏览器模式是否为 IE9 兼容模式

示例

javascript代码：

1
2
3

 if ( UE.browser.ie9Compat ) {
     console.log( '当前浏览器运行在IE9兼容模式下' );
 }

#### ie8

属性 静态

1.2.6.1

检测浏览器是否是IE8浏览器

*   警告： 如果浏览器不是IE， 则该值为undefined

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测浏览器是否是IE8浏览器

示例

javascript代码：

1
2
3

 if ( UE.browser.ie8 ) {
     console.log( '当前浏览器是IE8浏览器' );
 }

#### ie8Compat

属性 静态

1.2.6.1

检测浏览器模式是否为 IE8 兼容模式

*   警告： 如果浏览器不是IE， 则该值为undefined

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测浏览器模式是否为 IE8 兼容模式

示例

javascript代码：

1
2
3

 if ( UE.browser.ie8Compat ) {
     console.log( '当前浏览器运行在IE8兼容模式下' );
 }

#### ie7Compat

属性 静态

1.2.6.1

检测浏览器模式是否为 IE7 兼容模式

*   警告： 如果浏览器不是IE， 则该值为undefined

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测浏览器模式是否为 IE7 兼容模式

示例

javascript代码：

1
2
3

 if ( UE.browser.ie7Compat ) {
     console.log( '当前浏览器运行在IE7兼容模式下' );
 }

#### ie6Compat

属性 静态

1.2.6.1

检测浏览器模式是否为 IE6 模式 或者怪异模式

*   警告： 如果浏览器不是IE， 则该值为undefined

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测浏览器模式是否为 IE6 模式 或者怪异模式

示例

javascript代码：

1
2
3

 if ( UE.browser.ie6Compat ) {
     console.log( '当前浏览器运行在IE6模式或者怪异模式下' );
 }

#### chrome

属性 静态

1.2.6.1

检测当前浏览器是否为Chrome, 如果是，则返回Chrome的大版本号

*   警告： 如果浏览器不是chrome， 则该值为undefined

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

Number

无

检测当前浏览器是否为Chrome, 如果是，则返回Chrome的大版本号

示例

javascript代码：

1
2
3

 if ( UE.browser.chrome ) {
     console.log( '当前浏览器是Chrome' );
 }

#### safari

属性 静态

1.2.6.1

检测当前浏览器是否为Safari, 如果是，则返回Safari的大版本号

*   警告： 如果浏览器不是safari， 则该值为undefined

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

Number

无

检测当前浏览器是否为Safari, 如果是，则返回Safari的大版本号

示例

javascript代码：

1
2
3

 if ( UE.browser.safari ) {
     console.log( '当前浏览器是Safari' );
 }

#### version

属性 静态

1.2.6.1

检测当前浏览器版本号

*   提示：
    *   IE系列返回值为5,6,7,8,9,10等
    *   gecko系列会返回10900，158900等
    *   webkit系列会返回其build号 (如 522等)

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

Number

无

检测当前浏览器版本号

示例

javascript代码：

1

 console.log( '当前浏览器版本号是： ' + UE.browser.version );

#### isCompatible

属性 静态

1.2.6.1

检测当前浏览器是否能够与UEditor良好兼容

所属模块： [UE.browser](#UE.browser)

类型

默认值

描述

boolean

无

检测当前浏览器是否能够与UEditor良好兼容

示例

javascript代码：

1
2
3

 if ( UE.browser.isCompatible ) {
     console.log( '浏览器与UEditor能够良好兼容' );
 }

UE.dom.domUtils
---------------

模块

Dom操作工具包

方法列表

方法签名

静态

描述

[getPosition(Node nodeA, Node nodeB)](#UE.dom.domUtils.getPosition(Node,Node))

是

获取节点A相对于节点B的位置关系

[getNodeIndex(Node node)](#UE.dom.domUtils.getNodeIndex(Node))

是

检测节点node在父节点中的索引位置

[getNodeIndex(Node node, Boolean mergeTextNode)](#UE.dom.domUtils.getNodeIndex(Node,Boolean))

是

检测节点node在父节点中的索引位置， 根据给定的mergeTextNode参数决定是否要合并多个连续的文本节点为一个节点

[inDoc(Node node, DomDocument doc)](#UE.dom.domUtils.inDoc(Node,DomDocument))

是

检测节点node是否在给定的document对象上

[findParent(Node node, Function filterFn)](#UE.dom.domUtils.findParent(Node,Function))

是

根据给定的过滤规则filterFn， 查找符合该过滤规则的node节点的第一个祖先节点， 查找的起点是给定node节点的父节点。

[findParent(Node node, Function filterFn, Boolean includeSelf)](#UE.dom.domUtils.findParent(Node,Function,Boolean))

是

根据给定的过滤规则filterFn， 查找符合该过滤规则的node节点的第一个祖先节点， 如果includeSelf的值为true，则查找的起点是给定的节点node， 否则， 起点是node的父节点

[findParentByTagName(Node node, Array tagNames)](#UE.dom.domUtils.findParentByTagName(Node,Array))

是

查找node的节点名为tagName的第一个祖先节点， 查找的起点是node节点的父节点。

[findParentByTagName(Node node, Array tagNames, Boolean includeSelf)](#UE.dom.domUtils.findParentByTagName(Node,Array,Boolean))

是

查找node的节点名为tagName的祖先节点， 如果includeSelf的值为true，则查找的起点是给定的节点node， 否则， 起点是node的父节点。

[findParents(Node node)](#UE.dom.domUtils.findParents(Node))

是

查找节点node的祖先节点集合， 查找的起点是给定节点的父节点，结果集中不包含给定的节点。

[findParents(Node node, Boolean includeSelf)](#UE.dom.domUtils.findParents(Node,Boolean))

是

查找节点node的祖先节点集合， 如果includeSelf的值为true， 则返回的结果集中允许出现当前给定的节点， 否则， 该节点不会出现在其结果集中。

[insertAfter(Node node, Node newNode)](#UE.dom.domUtils.insertAfter(Node,Node))

是

在节点node后面插入新节点newNode

[remove(Node node)](#UE.dom.domUtils.remove(Node))

是

删除节点node及其下属的所有节点

[remove(Node node, Boolean keepChildren)](#UE.dom.domUtils.remove(Node,Boolean))

是

删除节点node，并根据keepChildren的值决定是否保留子节点

[getNextDomNode(Node node)](#UE.dom.domUtils.getNextDomNode(Node))

是

取得node节点的下一个兄弟节点， 如果该节点其后没有兄弟节点， 则递归查找其父节点之后的第一个兄弟节点， 直到找到满足条件的节点或者递归到BODY节点之后才会结束。

[getNextDomNode(Node node, Boolean startFromChild)](#UE.dom.domUtils.getNextDomNode(Node,Boolean))

是

取得node节点的下一个兄弟节点， 如果startFromChild的值为ture，则先获取其子节点， 如果有子节点则直接返回第一个子节点；如果没有子节点或者startFromChild的值为false， 则执行[getNextDomNode(Node node)](#UE.dom.domUtils.getNextDomNode(Node))的查找过程。

[getWindow(Node node)](#UE.dom.domUtils.getWindow(Node))

是

获取节点node所属的window对象

[getCommonAncestor(Node nodeA, Node nodeB)](#UE.dom.domUtils.getCommonAncestor(Node,Node))

是

获取离nodeA与nodeB最近的公共的祖先节点

[clearEmptySibling(Node node)](#UE.dom.domUtils.clearEmptySibling(Node))

是

清除node节点左右连续为空的兄弟inline节点

[clearEmptySibling(Node node, Boolean ignoreNext)](#UE.dom.domUtils.clearEmptySibling(Node,Boolean))

是

清除node节点左右连续为空的兄弟inline节点， 如果ignoreNext的值为true， 则忽略对右边兄弟节点的操作。

[clearEmptySibling(Node node, Boolean ignoreNext, Boolean ignorePre)](#UE.dom.domUtils.clearEmptySibling(Node,Boolean,Boolean))

是

清除node节点左右连续为空的兄弟inline节点， 如果ignoreNext的值为true， 则忽略对右边兄弟节点的操作， 如果ignorePre的值为true，则忽略对左边兄弟节点的操作。

[split(Node textNode, int offset)](#UE.dom.domUtils.split(Node,int))

是

将一个文本节点textNode拆分成两个文本节点，offset指定拆分位置

[isWhitespace(Node node)](#UE.dom.domUtils.isWhitespace(Node))

是

检测文本节点textNode是否为空节点（包括空格、换行、占位符等字符）

[getXY(Node element)](#UE.dom.domUtils.getXY(Node))

是

获取元素element相对于viewport的位置坐标

[on(Node element, String type, Function handler)](#UE.dom.domUtils.on(Node,String,Function))

是

为元素element绑定原生DOM事件，type为事件类型，handler为处理函数

[on(Node element, Array type, Function handler)](#UE.dom.domUtils.on(Node,Array,Function))

是

为元素element绑定原生DOM事件，type为事件类型，handler为处理函数

[un(Node element, String type, Function handler)](#UE.dom.domUtils.un(Node,String,Function))

是

解除DOM事件绑定

[un(Node element, Array type, Function handler)](#UE.dom.domUtils.un(Node,Array,Function))

是

解除DOM事件绑定

[isSameElement(Node nodeA, Node nodeB)](#UE.dom.domUtils.isSameElement(Node,Node))

是

比较节点nodeA与节点nodeB是否具有相同的标签名、属性名以及属性值

[isSameStyle(Node nodeA, Node nodeB)](#UE.dom.domUtils.isSameStyle(Node,Node))

是

判断节点nodeA与节点nodeB的元素的style属性是否一致

[isBlockElm(Node node)](#UE.dom.domUtils.isBlockElm(Node))

是

检查节点node是否为block元素

[isBody(Element node)](#UE.dom.domUtils.isBody(Element))

是

检测node节点是否为body节点

[breakParent(Node node, Node parent)](#UE.dom.domUtils.breakParent(Node,Node))

是

以node节点为分界，将该节点的指定祖先节点parent拆分成两个独立的节点， 拆分形成的两个节点之间是node节点

[isEmptyInlineElement(Node node)](#UE.dom.domUtils.isEmptyInlineElement(Node))

是

检查节点node是否是空inline节点

[trimWhiteTextNode(Element node)](#UE.dom.domUtils.trimWhiteTextNode(Element))

是

删除node节点下首尾两端的空白文本子节点

[getElementsByTagName(Node node, String tagName)](#UE.dom.domUtils.getElementsByTagName(Node,String))

是

原生方法getElementsByTagName的封装

[mergeToParent(Element node)](#UE.dom.domUtils.mergeToParent(Element))

是

将节点node提取到父节点上

[mergeSibling(Element node)](#UE.dom.domUtils.mergeSibling(Element))

是

合并节点node的左右兄弟节点

[mergeSibling(Element node, Boolean ignorePre)](#UE.dom.domUtils.mergeSibling(Element,Boolean))

是

合并节点node的左右兄弟节点， 可以根据给定的条件选择是否忽略合并左节点。

[mergeSibling(Element node, Boolean ignorePre, Boolean ignoreNext)](#UE.dom.domUtils.mergeSibling(Element,Boolean,Boolean))

是

合并节点node的左右兄弟节点，可以根据给定的条件选择是否忽略合并左右节点。

[unSelectable(Element node)](#UE.dom.domUtils.unSelectable(Element))

是

设置节点node及其子节点不会被选中

[removeAttributes(Node node, String attrNames)](#UE.dom.domUtils.removeAttributes(Node,String))

是

删除节点node上的指定属性名称的属性

[removeAttributes(Node node, Array attrNames)](#UE.dom.domUtils.removeAttributes(Node,Array))

是

删除节点node上的指定属性名称的属性

[createElement(DomDocument doc, String tagName, Object attrs)](#UE.dom.domUtils.createElement(DomDocument,String,Object))

是

在doc下创建一个标签名为tag，属性为attrs的元素

[setAttributes(Element node, Object attrs)](#UE.dom.domUtils.setAttributes(Element,Object))

是

为节点node添加属性attrs，attrs为属性键值对

[getComputedStyle(Element element, String styleName)](#UE.dom.domUtils.getComputedStyle(Element,String))

是

获取元素element经过计算后的样式值

[removeClasses(Element ele, String classNames)](#UE.dom.domUtils.removeClasses(Element,String))

是

删除元素element指定的className

[removeClasses(Element ele, Array classNames)](#UE.dom.domUtils.removeClasses(Element,Array))

是

删除元素element指定的className

[addClass(Node ele, String classNames)](#UE.dom.domUtils.addClass(Node,String))

是

给元素element添加className

[addClass(Node ele, Array classNames)](#UE.dom.domUtils.addClass(Node,Array))

是

给元素element添加className

[hasClass(Node ele, String classNames)](#UE.dom.domUtils.hasClass(Node,String))

是

判断元素element是否包含给定的样式类名className

[hasClass(Node ele, Array classNames)](#UE.dom.domUtils.hasClass(Node,Array))

是

判断元素element是否包含给定的样式类名className

[preventDefault(Event evt)](#UE.dom.domUtils.preventDefault(Event))

是

阻止事件默认行为

[removeStyle(Element element, String styleName)](#UE.dom.domUtils.removeStyle(Element,String))

是

删除元素element指定的样式

[getStyle(Element element, String styleName)](#UE.dom.domUtils.getStyle(Element,String))

是

获取元素element的style属性的指定值

[setStyle(Element element, String styleName, String styleValue)](#UE.dom.domUtils.setStyle(Element,String,String))

是

为元素element设置样式属性值

[setStyles(Element element, Object styles)](#UE.dom.domUtils.setStyles(Element,Object))

是

为元素element设置多个样式属性值

[getChildCount(Element node)](#UE.dom.domUtils.getChildCount(Element))

是

获取子节点的数量

[getChildCount(Element node, Function fn)](#UE.dom.domUtils.getChildCount(Element,Function))

是

根据给定的过滤规则， 获取符合条件的子节点的数量

[isEmptyNode(Node node)](#UE.dom.domUtils.isEmptyNode(Node))

是

判断给定节点是否为空节点

[scrollToView(Node node, window win, Number offsetTop)](#UE.dom.domUtils.scrollToView(Node,window,Number))

是

将显示区域滚动到指定节点的位置

[isBr(Node node)](#UE.dom.domUtils.isBr(Node))

是

判断给定节点是否为br

[isEmptyBlock(Element node)](#UE.dom.domUtils.isEmptyBlock(Element))

是

判断给定的元素是否是一个空元素

[isEmptyBlock(Element node, RegExp reg)](#UE.dom.domUtils.isEmptyBlock(Element,RegExp))

是

根据指定的判断规则判断给定的元素是否是一个空元素

[setViewportOffset(Element element, Object offset)](#UE.dom.domUtils.setViewportOffset(Element,Object))

是

移动元素使得该元素的位置移动指定的偏移量的距离

[moveChild(Node src, Node tag)](#UE.dom.domUtils.moveChild(Node,Node))

是

把节点src的所有子节点追加到另一个节点tag上去

[moveChild(Node src, Node tag, Boolean dir)](#UE.dom.domUtils.moveChild(Node,Node,Boolean))

是

把节点src的所有子节点移动到另一个节点tag上去, 可以通过dir参数控制附加的行为是“追加”还是“插入顶部”

[isTagNode(Node node, String tagName)](#UE.dom.domUtils.isTagNode(Node,String))

是

检测节点的标签是否是给定的标签

[filterNodeList(Array nodeList, Function fn)](#UE.dom.domUtils.filterNodeList(Array,Function))

是

给定一个节点数组，在通过指定的过滤器过滤后， 获取其中满足过滤条件的第一个节点

[filterNodeList(Array nodeList, String tagNames)](#UE.dom.domUtils.filterNodeList(Array,String))

是

给定一个节点数组nodeList和一组标签名tagNames， 获取其中能够匹配标签名的节点集合中的第一个节点

[filterNodeList(Array nodeList, Function fn, Boolean forAll)](#UE.dom.domUtils.filterNodeList(Array,Function,Boolean))

是

给定一个节点数组，在通过指定的过滤器过滤后， 如果参数forAll为true， 则会返回所有满足过滤 条件的节点集合， 否则， 返回满足条件的节点集合中的第一个节点

[isInNodeEndBoundary(UE.dom.Range rng)](#UE.dom.domUtils.isInNodeEndBoundary(UE.dom.Range))

是

查询给定的range选区是否在给定的node节点内，且在该节点的最末尾

模块成员详细描述([UE.dom.domUtils](#UE.dom.domUtils))

#### getPosition([Node](#Node) nodeA, [Node](#Node) nodeB)

方法 静态

1.2.6.1

获取节点A相对于节点B的位置关系

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

nodeA

[Node](#Node)

需要查询位置关系的节点A

nodeB

[Node](#Node)

需要查询位置关系的节点B

返回值

类型

描述

[Number](#Number)

节点A与节点B的关系

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37

 //output: 20
 var position \= UE.dom.domUtils.getPosition( document.documentElement, document.body );

 switch ( position ) {

      //0
      case POSITION\_IDENTICAL:
          console.log('元素相同');
          break;
      //1
      case POSITION\_DISCONNECTED:
          console.log('两个节点在不同的文档中');
          break;
      //2
      case POSITION\_FOLLOWING:
          console.log('节点A在节点B之后');
          break;
      //4
      case POSITION\_PRECEDING;
          console.log('节点A在节点B之前');
          break;
      //8
      case POSITION\_IS\_CONTAINED:
          console.log('节点A被节点B包含');
          break;
      case 10:
          console.log('节点A被节点B包含且节点A在节点B之后');
          break;
      //16
      case POSITION\_CONTAINS:
          console.log('节点A包含节点B');
          break;
      case 20:
          console.log('节点A包含节点B且节点A在节点B之前');
          break;

 }

#### getNodeIndex([Node](#Node) node)

方法 静态

1.2.6.1

检测节点node在父节点中的索引位置

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参考

[UE.dom.domUtils.getNodeIndex(Node,Boolean)](#UE.dom.domUtils.getNodeIndex(Node,Boolean))

参数列表

参数名

类型

描述

node

[Node](#Node)

需要检测的节点对象

返回值

类型

描述

[Number](#Number)

该节点在父节点中的位置

#### getNodeIndex([Node](#Node) node, [Boolean](#Boolean) mergeTextNode)

方法 静态

1.2.6.1

检测节点node在父节点中的索引位置， 根据给定的mergeTextNode参数决定是否要合并多个连续的文本节点为一个节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要检测的节点对象

mergeTextNode

[Boolean](#Boolean)

是否合并多个连续的文本节点为一个节点

返回值

类型

描述

[Number](#Number)

该节点在父节点中的位置

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

      var node \= document.createElement("div");

      node.appendChild( document.createTextNode( "hello" ) );
      node.appendChild( document.createTextNode( "world" ) );
      node.appendChild( node \= document.createElement( "div" ) );

      //output: 2
      console.log( UE.dom.domUtils.getNodeIndex( node ) );

      //output: 1
      console.log( UE.dom.domUtils.getNodeIndex( node, true ) );

#### inDoc([Node](#Node) node, [DomDocument](#DomDocument) doc)

方法 静态

1.2.6.1

检测节点node是否在给定的document对象上

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要检测的节点对象

doc

[DomDocument](#DomDocument)

需要检测的document对象

返回值

类型

描述

[Boolean](#Boolean)

该节点node是否在给定的document的dom树上

示例

javascript代码：

1
2
3
4
5
6
7
8
9

 var node \= document.createElement("div");

 //output: false
 console.log( UE.do.domUtils.inDoc( node, document ) );

 document.body.appendChild( node );

 //output: true
 console.log( UE.do.domUtils.inDoc( node, document ) );

#### findParent([Node](#Node) node, [Function](#Function) filterFn)

方法 静态

1.2.6.1

根据给定的过滤规则filterFn， 查找符合该过滤规则的node节点的第一个祖先节点， 查找的起点是给定node节点的父节点。

*   提示： 自定义的过滤方法filterFn接受一个Node对象作为参数， 该对象代表当前执行检测的祖先节点。 如果该 节点满足过滤条件， 则要求返回true， 这时将直接返回该节点作为findParent()的结果， 否则， 请返回false。

*   警告： 查找的终点是到body节点为止

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要查找的节点

filterFn

[Function](#Function)

自定义的过滤方法。

返回值

类型

描述

[Node | Null](#Node | Null)

如果找到符合过滤条件的节点， 就返回该节点， 否则返回NULL

示例

javascript代码：

1
2
3
4
5
6
7
8
9

 var filterNode \= UE.dom.domUtils.findParent( document.body.firstChild, function ( node ) {

     //由于查找的终点是body节点， 所以永远也不会匹配当前过滤器的条件， 即这里永远会返回false
     return node.tagName \=== "HTML";

 } );

 //output: true
 console.log( filterNode \=== null );

#### findParent([Node](#Node) node, [Function](#Function) filterFn, [Boolean](#Boolean) includeSelf)

方法 静态

1.2.6.1

根据给定的过滤规则filterFn， 查找符合该过滤规则的node节点的第一个祖先节点， 如果includeSelf的值为true，则查找的起点是给定的节点node， 否则， 起点是node的父节点

*   提示： 自定义的过滤方法filterFn接受一个Node对象作为参数， 该对象代表当前执行检测的祖先节点。 如果该 节点满足过滤条件， 则要求返回true， 这时将直接返回该节点作为findParent()的结果， 否则， 请返回false。

*   提示： 如果includeSelf为true， 则过滤器第一次执行时的参数会是节点本身。 反之， 过滤器第一次执行时的参数将是该节点的父节点。

*   警告： 查找的终点是到body节点为止

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要查找的节点

filterFn

[Function](#Function)

自定义的过滤方法。

includeSelf

[Boolean](#Boolean)

查找过程是否包含自身

返回值

类型

描述

[Node | Null](#Node | Null)

如果找到符合过滤条件的节点， 就返回该节点， 否则返回NULL

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17

 <body>

      <div id="test"\>
      </div>

      <script type="text/javascript"\>

          //output: DIV, BODY
          var filterNode \= UE.dom.domUtils.findParent( document.getElementById( "test" ), function ( node ) {

              console.log( node.tagName );
              return false;

          }, true );

      </script>
 </body>

#### findParentByTagName([Node](#Node) node, [Array](#Array) tagNames)

方法 静态

1.2.6.1

查找node的节点名为tagName的第一个祖先节点， 查找的起点是node节点的父节点。

*   警告： 查找的终点是到body节点为止

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要查找的节点对象

tagNames

[Array](#Array)

需要查找的父节点的名称数组

返回值

类型

描述

[Node | NULL](#Node | NULL)

如果找到符合条件的节点， 则返回该节点， 否则返回NULL

示例

javascript代码：

1
2
3

 var node \= UE.dom.domUtils.findParentByTagName( document.getElementsByTagName("div")\[0\], \[ "BODY" \] );
 //output: BODY
 console.log( node.tagName );

#### findParentByTagName([Node](#Node) node, [Array](#Array) tagNames, [Boolean](#Boolean) includeSelf)

方法 静态

1.2.6.1

查找node的节点名为tagName的祖先节点， 如果includeSelf的值为true，则查找的起点是给定的节点node， 否则， 起点是node的父节点。

*   警告： 查找的终点是到body节点为止

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要查找的节点对象

tagNames

[Array](#Array)

需要查找的父节点的名称数组

includeSelf

[Boolean](#Boolean)

查找过程是否包含node节点自身

返回值

类型

描述

[Node | NULL](#Node | NULL)

如果找到符合条件的节点， 则返回该节点， 否则返回NULL

示例

javascript代码：

1
2
3
4

 var queryTarget \= document.getElementsByTagName("div")\[0\];
 var node \= UE.dom.domUtils.findParentByTagName( queryTarget, \[ "DIV" \], true );
 //output: true
 console.log( queryTarget \=== node );

#### findParents([Node](#Node) node)

方法 静态

1.2.6.1

查找节点node的祖先节点集合， 查找的起点是给定节点的父节点，结果集中不包含给定的节点。

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要查找的节点对象

返回值

类型

描述

[Array](#Array)

给定节点的祖先节点数组

#### findParents([Node](#Node) node, [Boolean](#Boolean) includeSelf)

方法 静态

1.2.6.1

查找节点node的祖先节点集合， 如果includeSelf的值为true， 则返回的结果集中允许出现当前给定的节点， 否则， 该节点不会出现在其结果集中。

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要查找的节点对象

includeSelf

[Boolean](#Boolean)

查找的结果中是否允许包含当前查找的节点对象

返回值

类型

描述

[Array](#Array)

给定节点的祖先节点数组

#### insertAfter([Node](#Node) node, [Node](#Node) newNode)

方法 静态

1.2.6.1

在节点node后面插入新节点newNode

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

目标节点

newNode

[Node](#Node)

新插入的节点， 该节点将置于目标节点之后

返回值

类型

描述

[Node](#Node)

新插入的节点

#### remove([Node](#Node) node)

方法 静态

1.2.6.1

删除节点node及其下属的所有节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要删除的节点对象

返回值

类型

描述

[Node](#Node)

返回刚删除的节点对象

示例

html代码：

1
2
3
4
5
6
7
8

 <div id="test"\>
     <div id="child"\>你好</div>
 </div>
 <script>
     UE.dom.domUtils.remove( document.body, false );
     //output: false
     console.log( document.getElementById( "child" ) !== null );
 </script>

#### remove([Node](#Node) node, [Boolean](#Boolean) keepChildren)

方法 静态

1.2.6.1

删除节点node，并根据keepChildren的值决定是否保留子节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要删除的节点对象

keepChildren

[Boolean](#Boolean)

是否需要保留子节点

返回值

类型

描述

[Node](#Node)

返回刚删除的节点对象

示例

html代码：

1
2
3
4
5
6
7
8

 <div id="test"\>
     <div id="child"\>你好</div>
 </div>
 <script>
     UE.dom.domUtils.remove( document.body, true );
     //output: true
     console.log( document.getElementById( "child" ) !== null );
 </script>

#### getNextDomNode([Node](#Node) node)

方法 静态

1.2.6.1

取得node节点的下一个兄弟节点， 如果该节点其后没有兄弟节点， 则递归查找其父节点之后的第一个兄弟节点， 直到找到满足条件的节点或者递归到BODY节点之后才会结束。

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要获取其后的兄弟节点的节点对象

返回值

类型

描述

[Node | NULL](#Node | NULL)

如果找满足条件的节点， 则返回该节点， 否则返回NULL

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

     <body>
      <div id="test"\>
          <span></span>
      </div>
      <i>xxx</i>
 </body>
 <script>

     //output: i节点
     console.log( UE.dom.domUtils.getNextDomNode( document.getElementById( "test" ) ) );

 </script>

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14

 <body>
      <div>
          <span></span>
          <i id="test"\>xxx</i>
      </div>
      <b>xxx</b>
 </body>
 <script>

     //由于id为test的i节点之后没有兄弟节点， 则查找其父节点（div）后面的兄弟节点
     //output: b节点
     console.log( UE.dom.domUtils.getNextDomNode( document.getElementById( "test" ) ) );

 </script>

#### getNextDomNode([Node](#Node) node, [Boolean](#Boolean) startFromChild)

方法 静态

1.2.6.1

取得node节点的下一个兄弟节点， 如果startFromChild的值为ture，则先获取其子节点， 如果有子节点则直接返回第一个子节点；如果没有子节点或者startFromChild的值为false， 则执行[getNextDomNode(Node node)](#UE.dom.domUtils.getNextDomNode(Node))的查找过程。

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参考

[UE.dom.domUtils.getNextDomNode(Node)](#UE.dom.domUtils.getNextDomNode(Node))

参数列表

参数名

类型

描述

node

[Node](#Node)

需要获取其后的兄弟节点的节点对象

startFromChild

[Boolean](#Boolean)

查找过程是否从其子节点开始

返回值

类型

描述

[Node | NULL](#Node | NULL)

如果找满足条件的节点， 则返回该节点， 否则返回NULL

#### getWindow([Node](#Node) node)

方法 静态

1.2.6.1

获取节点node所属的window对象

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

节点对象

返回值

类型

描述

[Window](#Window)

当前节点所属的window对象

示例

javascript代码：

1
2

 //output: true
 console.log( UE.dom.domUtils.getWindow( document.body ) \=== window );

#### getCommonAncestor([Node](#Node) nodeA, [Node](#Node) nodeB)

方法 静态

1.2.6.1

获取离nodeA与nodeB最近的公共的祖先节点

*   提示： 如果给定的两个节点是同一个节点， 将直接返回该节点。

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

nodeA

[Node](#Node)

第一个节点

nodeB

[Node](#Node)

第二个节点

返回值

类型

描述

[Node | NULL](#Node | NULL)

如果未找到公共节点， 返回NULL， 否则返回最近的公共祖先节点。

示例

javascript代码：

1
2
3

 var commonAncestor \= UE.dom.domUtils.getCommonAncestor( document.body, document.body.firstChild );
 //output: true
 console.log( commonAncestor.tagName.toLowerCase() \=== 'body' );

#### clearEmptySibling([Node](#Node) node)

方法 静态

1.2.6.1

清除node节点左右连续为空的兄弟inline节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

执行的节点对象， 如果该节点的左右连续的兄弟节点是空的inline节点， 则这些兄弟节点将被删除

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16

 <body>
     <div></div>
     <span id="test"\></span>
     <i></i>
     <b></b>
     <em>xxx</em>
     <span></span>
 </body>
 <script>

      UE.dom.domUtils.clearEmptySibling( document.getElementById( "test" ) );

      //output: <div></div><span id="test"></span><em>xxx</em><span></span>
      console.log( document.body.innerHTML );

 </script>

#### clearEmptySibling([Node](#Node) node, [Boolean](#Boolean) ignoreNext)

方法 静态

1.2.6.1

清除node节点左右连续为空的兄弟inline节点， 如果ignoreNext的值为true， 则忽略对右边兄弟节点的操作。

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参考

[UE.dom.domUtils.clearEmptySibling(Node)](#UE.dom.domUtils.clearEmptySibling(Node))

参数列表

参数名

类型

描述

node

[Node](#Node)

执行的节点对象， 如果该节点的左右连续的兄弟节点是空的inline节点，

ignoreNext

[Boolean](#Boolean)

是否忽略忽略对右边的兄弟节点的操作 则这些兄弟节点将被删除

#### clearEmptySibling([Node](#Node) node, [Boolean](#Boolean) ignoreNext, [Boolean](#Boolean) ignorePre)

方法 静态

1.2.6.1

清除node节点左右连续为空的兄弟inline节点， 如果ignoreNext的值为true， 则忽略对右边兄弟节点的操作， 如果ignorePre的值为true，则忽略对左边兄弟节点的操作。

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参考

[UE.dom.domUtils.clearEmptySibling(Node)](#UE.dom.domUtils.clearEmptySibling(Node))

参数列表

参数名

类型

描述

node

[Node](#Node)

执行的节点对象， 如果该节点的左右连续的兄弟节点是空的inline节点，

ignoreNext

[Boolean](#Boolean)

是否忽略忽略对右边的兄弟节点的操作

ignorePre

[Boolean](#Boolean)

是否忽略忽略对左边的兄弟节点的操作 则这些兄弟节点将被删除

#### split([Node](#Node) textNode, [int](#int) offset)

方法 静态

1.2.6.1

将一个文本节点textNode拆分成两个文本节点，offset指定拆分位置

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

textNode

[Node](#Node)

需要拆分的文本节点对象

offset

[int](#int)

需要拆分的位置， 位置计算从0开始

返回值

类型

描述

[Node](#Node)

拆分后形成的新节点

示例

html代码：

1
2
3
4
5
6

 <div id="test"\>abcdef</div>
 <script>
      var newNode \= UE.dom.domUtils.split( document.getElementById( "test" ).firstChild, 3 );
      //output: def
      console.log( newNode.nodeValue );
 </script>

#### isWhitespace([Node](#Node) node)

方法 静态

1.2.6.1

检测文本节点textNode是否为空节点（包括空格、换行、占位符等字符）

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要检测的节点对象

返回值

类型

描述

[Boolean](#Boolean)

检测的节点是否为空

示例

html代码：

1
2
3
4
5
6
7

 <div id="test"\>

 </div>
 <script>
      //output: true
      console.log( UE.dom.domUtils.isWhitespace( document.getElementById("test").firstChild ) );
 </script>

#### getXY([Node](#Node) element)

方法 静态

1.2.6.1

获取元素element相对于viewport的位置坐标

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Node](#Node)

需要计算位置的节点对象

返回值

类型

描述

[Object](#Object)

返回形如{x:left,y:top}的一个key-value映射对象， 其中键x代表水平偏移距离， y代表垂直偏移距离。

示例

javascript代码：

1
2
3

 var location \= UE.dom.domUtils.getXY( document.getElementById("test") );
 //output: test的坐标为: 12, 24
 console.log( 'test的坐标为： ', location.x, ',', location.y );

#### on([Node](#Node) element, [String](#String) type, [Function](#Function) handler)

方法 静态

1.2.6.1

为元素element绑定原生DOM事件，type为事件类型，handler为处理函数

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Node](#Node)

需要绑定事件的节点对象

type

[String](#String)

绑定的事件类型

handler

[Function](#Function)

事件处理器

示例

javascript代码：

1
2
3

 UE.dom.domUtils.on(document.body,"click",function(e){
     //e为事件对象，this为被点击元素对戏那个
 });

#### on([Node](#Node) element, [Array](#Array) type, [Function](#Function) handler)

方法 静态

1.2.6.1

为元素element绑定原生DOM事件，type为事件类型，handler为处理函数

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Node](#Node)

需要绑定事件的节点对象

type

[Array](#Array)

绑定的事件类型数组

handler

[Function](#Function)

事件处理器

示例

javascript代码：

1
2
3

 UE.dom.domUtils.on(document.body,\["click","mousedown"\],function(evt){
     //evt为事件对象，this为被点击元素对象
 });

#### un([Node](#Node) element, [String](#String) type, [Function](#Function) handler)

方法 静态

1.2.6.1

解除DOM事件绑定

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Node](#Node)

需要解除事件绑定的节点对象

type

[String](#String)

需要接触绑定的事件类型

handler

[Function](#Function)

对应的事件处理器

示例

javascript代码：

1
2
3

 UE.dom.domUtils.un(document.body,"click",function(evt){
     //evt为事件对象，this为被点击元素对象
 });

#### un([Node](#Node) element, [Array](#Array) type, [Function](#Function) handler)

方法 静态

1.2.6.1

解除DOM事件绑定

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Node](#Node)

需要解除事件绑定的节点对象

type

[Array](#Array)

需要接触绑定的事件类型数组

handler

[Function](#Function)

对应的事件处理器

示例

javascript代码：

1
2
3

 UE.dom.domUtils.un(document.body, \["click","mousedown"\],function(evt){
     //evt为事件对象，this为被点击元素对象
 });

#### isSameElement([Node](#Node) nodeA, [Node](#Node) nodeB)

方法 静态

1.2.6.1

比较节点nodeA与节点nodeB是否具有相同的标签名、属性名以及属性值

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

nodeA

[Node](#Node)

需要比较的节点

nodeB

[Node](#Node)

需要比较的节点

返回值

类型

描述

[Boolean](#Boolean)

两个节点是否具有相同的标签名、属性名以及属性值

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16

 <span style="font-size:12px"\>ssss</span>
 <span style="font-size:12px"\>bbbbb</span>
 <span style="font-size:13px"\>ssss</span>
 <span style="font-size:14px"\>bbbbb</span>

 <script>

     var nodes \= document.getElementsByTagName( "span" );

     //output: true
     console.log( UE.dom.domUtils.isSameElement( nodes\[0\], nodes\[1\] ) );

     //output: false
     console.log( UE.dom.domUtils.isSameElement( nodes\[2\], nodes\[3\] ) );

 </script>

#### isSameStyle([Node](#Node) nodeA, [Node](#Node) nodeB)

方法 静态

1.2.6.1

判断节点nodeA与节点nodeB的元素的style属性是否一致

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

nodeA

[Node](#Node)

需要比较的节点

nodeB

[Node](#Node)

需要比较的节点

返回值

类型

描述

[Boolean](#Boolean)

两个节点是否具有相同的style属性值

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16

 <span style="font-size:12px"\>ssss</span>
 <span style="font-size:12px"\>bbbbb</span>
 <span style="font-size:13px"\>ssss</span>
 <span style="font-size:14px"\>bbbbb</span>

 <script>

     var nodes \= document.getElementsByTagName( "span" );

     //output: true
     console.log( UE.dom.domUtils.isSameStyle( nodes\[0\], nodes\[1\] ) );

     //output: false
     console.log( UE.dom.domUtils.isSameStyle( nodes\[2\], nodes\[3\] ) );

 </script>

#### isBlockElm([Node](#Node) node)

方法 静态

1.2.6.1

检查节点node是否为block元素

*   警告： 该方法的判断规则如下： 如果该元素原本是block元素， 则不论该元素当前的css样式是什么都会返回true； 否则，检测该元素的css样式， 如果该元素当前是block元素， 则返回true。 其余情况下都返回false。

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要检测的节点对象

返回值

类型

描述

[Boolean](#Boolean)

是否是block元素节点

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16

 <span id="test1" style="display: block"\></span>
 <span id="test2"\></span>
 <div id="test3" style="display: inline"\></div>

 <script>

     //output: true
     console.log( UE.dom.domUtils.isBlockElm( document.getElementById("test1") ) );

     //output: false
     console.log( UE.dom.domUtils.isBlockElm( document.getElementById("test2") ) );

     //output: true
     console.log( UE.dom.domUtils.isBlockElm( document.getElementById("test3") ) );

 </script>

#### isBody([Element](#Element) node)

方法 静态

1.2.6.1

检测node节点是否为body节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要检测的dom元素

返回值

类型

描述

[Boolean](#Boolean)

给定的元素是否是body元素

示例

javascript代码：

1
2

 //output: true
 console.log( UE.dom.domUtils.isBody( document.body ) );

#### breakParent([Node](#Node) node, [Node](#Node) parent)

方法 静态

1.2.6.1

以node节点为分界，将该节点的指定祖先节点parent拆分成两个独立的节点， 拆分形成的两个节点之间是node节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

作为分界的节点对象

parent

[Node](#Node)

该节点必须是node节点的祖先节点， 且是block节点。

返回值

类型

描述

[Node](#Node)

给定的node分界节点

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16

      var node \= document.createElement("span"),
          wrapNode \= document.createElement( "div" ),
          parent \= document.createElement("p");

      parent.appendChild( node );
      wrapNode.appendChild( parent );

      //拆分前
      //output: <p><span></span></p>
      console.log( wrapNode.innerHTML );

      UE.dom.domUtils.breakParent( node, parent );
      //拆分后
      //output: <p></p><span></span><p></p>
      console.log( wrapNode.innerHTML );

#### isEmptyInlineElement([Node](#Node) node)

方法 静态

1.2.6.1

检查节点node是否是空inline节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要检测的节点对象

返回值

类型

描述

[Number](#Number)

如果给定的节点是空的inline节点， 则返回1, 否则返回0。

示例

html代码：

1
2
3
4

 <b><i></i></b> => 1
 <b><i></i><u></u></b> => 1
 <b></b> => 1
 <b>xx<i></i></b> => 0

#### trimWhiteTextNode([Element](#Element) node)

方法 静态

1.2.6.1

删除node节点下首尾两端的空白文本子节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要执行删除操作的元素对象

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15

      var node \= document.createElement("div");

      node.appendChild( document.createTextNode( "" ) );

      node.appendChild( document.createElement("div") );

      node.appendChild( document.createTextNode( "" ) );

      //3
      console.log( node.childNodes.length );

      UE.dom.domUtils.trimWhiteTextNode( node );

      //1
      console.log( node.childNodes.length );

#### getElementsByTagName([Node](#Node) node, [String](#String) tagName)

方法 静态

1.2.6.1

原生方法getElementsByTagName的封装

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

目标节点对象

tagName

[String](#String)

需要查找的节点的tagName， 多个tagName以空格分割

返回值

类型

描述

[Array](#Array)

符合条件的节点集合

#### mergeToParent([Element](#Element) node)

方法 静态

1.2.6.1

将节点node提取到父节点上

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要提取的元素对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19

 <div id="parent"\>
     <div id="sub"\>
         <span id="child"\></span>
     </div>
 </div>

 <script>

     var child \= document.getElementById( "child" );

     //output: sub
     console.log( child.parentNode.id );

     UE.dom.domUtils.mergeToParent( child );

     //output: parent
     console.log( child.parentNode.id );

 </script>

#### mergeSibling([Element](#Element) node)

方法 静态

1.2.6.1

合并节点node的左右兄弟节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要合并的目标节点

示例

html代码：

1
2
3
4
5
6
7
8

 <b>xxxx</b><b id="test"\>ooo</b><b>xxxx</b>

 <script>
     var demoNode \= document.getElementById("test");
     UE.dom.domUtils.mergeSibling( demoNode );
     //output: xxxxoooxxxx
     console.log( demoNode.innerHTML );
 </script>

#### mergeSibling([Element](#Element) node, [Boolean](#Boolean) ignorePre)

方法 静态

1.2.6.1

合并节点node的左右兄弟节点， 可以根据给定的条件选择是否忽略合并左节点。

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要合并的目标节点

ignorePre

[Boolean](#Boolean)

是否忽略合并左节点

示例

html代码：

1
2
3
4
5
6
7
8

 <b>xxxx</b><b id="test"\>ooo</b><b>xxxx</b>

 <script>
     var demoNode \= document.getElementById("test");
     UE.dom.domUtils.mergeSibling( demoNode, true );
     //output: oooxxxx
     console.log( demoNode.innerHTML );
 </script>

#### mergeSibling([Element](#Element) node, [Boolean](#Boolean) ignorePre, [Boolean](#Boolean) ignoreNext)

方法 静态

1.2.6.1

合并节点node的左右兄弟节点，可以根据给定的条件选择是否忽略合并左右节点。

*   提示： 如果同时忽略左右节点， 则该操作什么也不会做

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要合并的目标节点

ignorePre

[Boolean](#Boolean)

是否忽略合并左节点

ignoreNext

[Boolean](#Boolean)

是否忽略合并右节点

示例

html代码：

1
2
3
4
5
6
7
8

 <b>xxxx</b><b id="test"\>ooo</b><b>xxxx</b>

 <script>
     var demoNode \= document.getElementById("test");
     UE.dom.domUtils.mergeSibling( demoNode, false, true );
     //output: xxxxooo
     console.log( demoNode.innerHTML );
 </script>

#### unSelectable([Element](#Element) node)

方法 静态

1.2.6.1

设置节点node及其子节点不会被选中

*   提示： 执行该操作后的节点， 将不能被鼠标选中

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要执行操作的dom元素

示例

javascript代码：

1

 UE.dom.domUtils.unSelectable( document.body );

#### removeAttributes([Node](#Node) node, [String](#String) attrNames)

方法 静态

1.2.6.1

删除节点node上的指定属性名称的属性

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要删除属性的节点对象

attrNames

[String](#String)

可以是空格隔开的多个属性名称，该操作将会依次删除相应的属性

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <div id="wrap"\>
      <span style="font-size:14px;" id="test" name="followMe"\>xxxxx</span>
 </div>

 <script>

     UE.dom.domUtils.removeAttributes( document.getElementById( "test" ), "id name" );

     //output: <span style="font-size:14px;">xxxxx</span>
     console.log( document.getElementById("wrap").innerHTML );

 </script>

#### removeAttributes([Node](#Node) node, [Array](#Array) attrNames)

方法 静态

1.2.6.1

删除节点node上的指定属性名称的属性

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要删除属性的节点对象

attrNames

[Array](#Array)

需要删除的属性名数组

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <div id="wrap"\>
      <span style="font-size:14px;" id="test" name="followMe"\>xxxxx</span>
 </div>

 <script>

     UE.dom.domUtils.removeAttributes( document.getElementById( "test" ), \["id", "name"\] );

     //output: <span style="font-size:14px;">xxxxx</span>
     console.log( document.getElementById("wrap").innerHTML );

 </script>

#### createElement([DomDocument](#DomDocument) doc, [String](#String) tagName, [Object](#Object) attrs)

方法 静态

1.2.6.1

在doc下创建一个标签名为tag，属性为attrs的元素

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

doc

[DomDocument](#DomDocument)

新创建的元素属于该document节点创建

tagName

[String](#String)

需要创建的元素的标签名

attrs

[Object](#Object)

新创建的元素的属性key-value集合

返回值

类型

描述

[Element](#Element)

新创建的元素对象

示例

javascript代码：

1
2
3
4
5
6
7
8
9

 var ele \= UE.dom.domUtils.createElement( document, 'div', {
     id: 'test'
 } );

 //output: DIV
 console.log( ele.tagName );

 //output: test
 console.log( ele.id );

#### setAttributes([Element](#Element) node, [Object](#Object) attrs)

方法 静态

1.2.6.1

为节点node添加属性attrs，attrs为属性键值对

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要设置属性的元素对象

attrs

[Object](#Object)

需要设置的属性名-值对

返回值

类型

描述

[Element](#Element)

设置属性的元素对象

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <span id="test"\></span>

 <script>

     var testNode \= UE.dom.domUtils.setAttributes( document.getElementById( "test" ), {
         id: 'demo'
     } );

     //output: demo
     console.log( testNode.id );

 </script>

#### getComputedStyle([Element](#Element) element, [String](#String) styleName)

方法 静态

1.2.6.1

获取元素element经过计算后的样式值

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Element](#Element)

需要获取样式的元素对象

styleName

[String](#String)

需要获取的样式名

返回值

类型

描述

[String](#String)

获取到的样式值

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <style type="text/css"\>
      #test {
          font-size: 15px;
      }
 </style>

 <span id="test"\></span>

 <script>
     //output: 15px
     console.log( UE.dom.domUtils.getComputedStyle( document.getElementById( "test" ), 'font-size' ) );
 </script>

#### removeClasses([Element](#Element) ele, [String](#String) classNames)

方法 静态

1.2.6.1

删除元素element指定的className

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

ele

[Element](#Element)

需要删除class的元素节点

classNames

[String](#String)

需要删除的className， 多个className之间以空格分开

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 <span id="test" class="test1 test2 test3"\>xxx</span>

 <script>

     var testNode \= document.getElementById( "test" );
     UE.dom.domUtils.removeClasses( testNode, "test1 test2" );

     //output: test3
     console.log( testNode.className );

 </script>

#### removeClasses([Element](#Element) ele, [Array](#Array) classNames)

方法 静态

1.2.6.1

删除元素element指定的className

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

ele

[Element](#Element)

需要删除class的元素节点

classNames

[Array](#Array)

需要删除的className数组

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 <span id="test" class="test1 test2 test3"\>xxx</span>

 <script>

     var testNode \= document.getElementById( "test" );
     UE.dom.domUtils.removeClasses( testNode, \["test1", "test2"\] );

     //output: test3
     console.log( testNode.className );

 </script>

#### addClass([Node](#Node) ele, [String](#String) classNames)

方法 静态

1.2.6.1

给元素element添加className

*   提示： 相同的类名不会被重复添加

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

ele

[Node](#Node)

需要增加className的元素

classNames

[String](#String)

需要添加的className， 多个className之间以空格分割

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 <span id="test" class="cls1 cls2"\></span>

 <script>
     var testNode = document.getElementById("test");

     UE.dom.domUtils.addClass( testNode, "cls2 cls3 cls4" );

     //output: cl1 cls2 cls3 cls4
     console.log( testNode.className );

 <script>

#### addClass([Node](#Node) ele, [Array](#Array) classNames)

方法 静态

1.2.6.1

给元素element添加className

*   提示： 相同的类名不会被重复添加

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

ele

[Node](#Node)

需要增加className的元素

classNames

[Array](#Array)

需要添加的className的数组

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 <span id="test" class="cls1 cls2"\></span>

 <script>
     var testNode = document.getElementById("test");

     UE.dom.domUtils.addClass( testNode, \["cls2", "cls3", "cls4"\] );

     //output: cl1 cls2 cls3 cls4
     console.log( testNode.className );

 <script>

#### hasClass([Node](#Node) ele, [String](#String) classNames)

方法 静态

1.2.6.1

判断元素element是否包含给定的样式类名className

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

ele

[Node](#Node)

需要检测的元素

classNames

[String](#String)

需要检测的className， 多个className之间用空格分割

返回值

类型

描述

[Boolean](#Boolean)

元素是否包含所有给定的className

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 <span id="test1" class="cls1 cls2"\></span>

 <script>
     var test1 \= document.getElementById("test1");

     //output: false
     console.log( UE.dom.domUtils.hasClass( test1, "cls2 cls1 cls3" ) );

     //output: true
     console.log( UE.dom.domUtils.hasClass( test1, "cls2 cls1" ) );
 </script>

#### hasClass([Node](#Node) ele, [Array](#Array) classNames)

方法 静态

1.2.6.1

判断元素element是否包含给定的样式类名className

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

ele

[Node](#Node)

需要检测的元素

classNames

[Array](#Array)

需要检测的className数组

返回值

类型

描述

[Boolean](#Boolean)

元素是否包含所有给定的className

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 <span id="test1" class="cls1 cls2"\></span>

 <script>
     var test1 \= document.getElementById("test1");

     //output: false
     console.log( UE.dom.domUtils.hasClass( test1, \[ "cls2", "cls1", "cls3" \] ) );

     //output: true
     console.log( UE.dom.domUtils.hasClass( test1, \[ "cls2", "cls1" \]) );
 </script>

#### preventDefault([Event](#Event) evt)

方法 静态

1.2.6.1

阻止事件默认行为

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

evt

[Event](#Event)

需要阻止默认行为的事件对象

示例

javascript代码：

1

 UE.dom.domUtils.preventDefault( evt );

#### removeStyle([Element](#Element) element, [String](#String) styleName)

方法 静态

1.2.6.1

删除元素element指定的样式

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Element](#Element)

需要删除样式的元素

styleName

[String](#String)

需要删除的样式名

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12

 <span id="test" style="color: red; background: blue;"\></span>

 <script>

     var testNode \= document.getElementById("test");

     UE.dom.domUtils.removeStyle( testNode, 'color' );

     //output: background: blue;
     console.log( testNode.style.cssText );

 </script>

#### getStyle([Element](#Element) element, [String](#String) styleName)

方法 静态

1.2.6.1

获取元素element的style属性的指定值

*   警告： 该方法仅获取元素style属性中所标明的值

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Element](#Element)

需要获取属性值的元素

styleName

[String](#String)

需要获取的style的名称

返回值

类型

描述

[String](#String)

该元素包含指定的style属性值

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13

 <div id="test" style="color: red;"\></div>

 <script>

      var testNode \= document.getElementById( "test" );

      //output: red
      console.log( UE.dom.domUtils.getStyle( testNode, "color" ) );

      //output: ""
      console.log( UE.dom.domUtils.getStyle( testNode, "background" ) );

 </script>

#### setStyle([Element](#Element) element, [String](#String) styleName, [String](#String) styleValue)

方法 静态

1.2.6.1

为元素element设置样式属性值

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Element](#Element)

需要设置样式的元素

styleName

[String](#String)

样式名

styleValue

[String](#String)

样式值

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14

 <div id="test"\></div>

 <script>

      var testNode \= document.getElementById( "test" );

      //output: ""
      console.log( testNode.style.color );

      UE.dom.domUtils.setStyle( testNode, 'color', 'red' );
      //output: "red"
      console.log( testNode.style.color );

 </script>

#### setStyles([Element](#Element) element, [Object](#Object) styles)

方法 静态

1.2.6.1

为元素element设置多个样式属性值

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Element](#Element)

需要设置样式的元素

styles

[Object](#Object)

样式名值对

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16

 <div id="test"\></div>

 <script>

      var testNode \= document.getElementById( "test" );

      //output: ""
      console.log( testNode.style.color );

      UE.dom.domUtils.setStyles( testNode, {
          'color': 'red'
      } );
      //output: "red"
      console.log( testNode.style.color );

 </script>

#### getChildCount([Element](#Element) node)

方法 静态

1.2.6.1

获取子节点的数量

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要检测的元素

返回值

类型

描述

[Number](#Number)

给定的node元素的子节点数量

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10

 <div id="test"\>
      <span></span>
 </div>

 <script>

     //output: 3
     console.log( UE.dom.domUtils.getChildCount( document.getElementById("test") ) );

 </script>

#### getChildCount([Element](#Element) node, [Function](#Function) fn)

方法 静态

1.2.6.1

根据给定的过滤规则， 获取符合条件的子节点的数量

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要检测的元素

fn

[Function](#Function)

过滤器， 要求对符合条件的子节点返回true， 反之则要求返回false

返回值

类型

描述

[Number](#Number)

符合过滤条件的node元素的子节点数量

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14

 <div id="test"\>
      <span></span>
 </div>

 <script>

     //output: 1
     console.log( UE.dom.domUtils.getChildCount( document.getElementById("test"), function ( node ) {

         return node.nodeType \=== 1;

     } ) );

 </script>

#### isEmptyNode([Node](#Node) node)

方法 静态

1.2.6.1

判断给定节点是否为空节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要检测的节点对象

返回值

类型

描述

[Boolean](#Boolean)

节点是否为空

示例

javascript代码：

1

 UE.dom.domUtils.isEmptyNode( document.body );

#### scrollToView([Node](#Node) node, [window](#window) win, [Number](#Number) offsetTop)

方法 静态

1.2.6.1

将显示区域滚动到指定节点的位置

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

节点

win

[window](#window)

window对象

offsetTop

[Number](#Number)

距离上方的偏移量

#### isBr([Node](#Node) node)

方法 静态

1.2.6.1

判断给定节点是否为br

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要判断的节点对象

返回值

类型

描述

[Boolean](#Boolean)

给定的节点是否是br节点

#### isEmptyBlock([Element](#Element) node)

方法 静态

1.2.6.1

判断给定的元素是否是一个空元素

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要判断的元素

返回值

类型

描述

[Boolean](#Boolean)

是否是空元素

示例

html代码：

1
2
3
4
5
6

 <div id="test"\></div>

 <script>
     //output: true
     console.log( UE.dom.domUtils.isEmptyBlock( document.getElementById("test") ) );
 </script>

#### isEmptyBlock([Element](#Element) node, [RegExp](#RegExp) reg)

方法 静态

1.2.6.1

根据指定的判断规则判断给定的元素是否是一个空元素

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Element](#Element)

需要判断的元素

reg

[RegExp](#RegExp)

对内容执行判断的正则表达式对象

返回值

类型

描述

[Boolean](#Boolean)

是否是空元素

#### setViewportOffset([Element](#Element) element, [Object](#Object) offset)

方法 静态

1.2.6.1

移动元素使得该元素的位置移动指定的偏移量的距离

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

element

[Element](#Element)

需要设置偏移量的元素

offset

[Object](#Object)

偏移量， 形如{ left: 100, top: 50 }的一个键值对， 表示该元素将在 现有的位置上向水平方向偏移offset.left的距离， 在竖直方向上偏移 offset.top的距离

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15

 <div id="test" style="top: 100px; left: 50px; position: absolute;"\></div>

 <script>

     var testNode \= document.getElementById("test");

     UE.dom.domUtils.setViewportOffset( testNode, {
         left: 200,
         top: 50
     } );

     //output: top: 300px; left: 100px; position: absolute;
     console.log( testNode.style.cssText );

 </script>

#### moveChild([Node](#Node) src, [Node](#Node) tag)

方法 静态

1.2.6.1

把节点src的所有子节点追加到另一个节点tag上去

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

src

[Node](#Node)

源节点， 该节点下的所有子节点将被移除

tag

[Node](#Node)

目标节点， 从源节点移除的子节点将被追加到该节点下

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21

 <div id="test1"\>
      <span></span>
 </div>
 <div id="test2"\>
     <div></div>
 </div>

 <script>

     var test1 \= document.getElementById("test1"),
         test2 \= document.getElementById("test2");

     UE.dom.domUtils.moveChild( test1, test2 );

     //output: ""（空字符串）
     console.log( test1.innerHTML );

     //output: "<div></div><span></span>"
     console.log( test2.innerHTML );

 </script>

#### moveChild([Node](#Node) src, [Node](#Node) tag, [Boolean](#Boolean) dir)

方法 静态

1.2.6.1

把节点src的所有子节点移动到另一个节点tag上去, 可以通过dir参数控制附加的行为是“追加”还是“插入顶部”

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

src

[Node](#Node)

源节点， 该节点下的所有子节点将被移除

tag

[Node](#Node)

目标节点， 从源节点移除的子节点将被附加到该节点下

dir

[Boolean](#Boolean)

附加方式， 如果为true， 则附加进去的节点将被放到目标节点的顶部， 反之，则放到末尾

示例

html代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19
20
21

 <div id="test1"\>
      <span></span>
 </div>
 <div id="test2"\>
     <div></div>
 </div>

 <script>

     var test1 \= document.getElementById("test1"),
         test2 \= document.getElementById("test2");

     UE.dom.domUtils.moveChild( test1, test2, true );

     //output: ""（空字符串）
     console.log( test1.innerHTML );

     //output: "<span></span><div></div>"
     console.log( test2.innerHTML );

 </script>

#### isTagNode([Node](#Node) node, [String](#String) tagName)

方法 静态

1.2.6.1

检测节点的标签是否是给定的标签

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

node

[Node](#Node)

需要检测的节点对象

tagName

[String](#String)

标签

返回值

类型

描述

[Boolean](#Boolean)

节点的标签是否是给定的标签

示例

html代码：

1
2
3
4
5
6
7
8

 <div id="test"\></div>

 <script>

     //output: true
     console.log( UE.dom.domUtils.isTagNode( document.getElementById("test"), "div" ) );

 </script>

#### filterNodeList([Array](#Array) nodeList, [Function](#Function) fn)

方法 静态

1.2.6.1

给定一个节点数组，在通过指定的过滤器过滤后， 获取其中满足过滤条件的第一个节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

nodeList

[Array](#Array)

需要过滤的节点数组

fn

[Function](#Function)

过滤器， 对符合条件的节点， 执行结果返回true， 反之则返回false

返回值

类型

描述

[Node | NULL](#Node | NULL)

如果找到符合过滤条件的节点， 则返回该节点， 否则返回NULL

示例

javascript代码：

1
2
3
4
5
6
7

 var divNodes \= document.getElementsByTagName("div");
 divNodes \= \[\].slice.call( divNodes, 0 );

 //output: null
 console.log( UE.dom.domUtils.filterNodeList( divNodes, function ( node ) {
     return node.tagName.toLowerCase() !== 'div';
 } ) );

#### filterNodeList([Array](#Array) nodeList, [String](#String) tagNames)

方法 静态

1.2.6.1

给定一个节点数组nodeList和一组标签名tagNames， 获取其中能够匹配标签名的节点集合中的第一个节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

nodeList

[Array](#Array)

需要过滤的节点数组

tagNames

[String](#String)

需要匹配的标签名， 多个标签名之间用空格分割

返回值

类型

描述

[Node | NULL](#Node | NULL)

如果找到标签名匹配的节点， 则返回该节点， 否则返回NULL

示例

javascript代码：

1
2
3
4
5

 var divNodes \= document.getElementsByTagName("div");
 divNodes \= \[\].slice.call( divNodes, 0 );

 //output: null
 console.log( UE.dom.domUtils.filterNodeList( divNodes, 'a span' ) );

#### filterNodeList([Array](#Array) nodeList, [Function](#Function) fn, [Boolean](#Boolean) forAll)

方法 静态

1.2.6.1

给定一个节点数组，在通过指定的过滤器过滤后， 如果参数forAll为true， 则会返回所有满足过滤 条件的节点集合， 否则， 返回满足条件的节点集合中的第一个节点

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

nodeList

[Array](#Array)

需要过滤的节点数组

fn

[Function](#Function)

过滤器， 对符合条件的节点， 执行结果返回true， 反之则返回false

forAll

[Boolean](#Boolean)

是否返回整个节点数组, 如果该参数为false， 则返回节点集合中的第一个节点

返回值

类型

描述

[Array | Node | NULL](#Array | Node | NULL)

如果找到符合过滤条件的节点， 则根据参数forAll的值决定返回满足 过滤条件的节点数组或第一个节点， 否则返回NULL

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19

 var divNodes \= document.getElementsByTagName("div");
 divNodes \= \[\].slice.call( divNodes, 0 );

 //output: 3（假定有3个div）
 console.log( divNodes.length );

 var nodes \= UE.dom.domUtils.filterNodeList( divNodes, function ( node ) {
     return node.tagName.toLowerCase() \=== 'div';
 }, true );

 //output: 3
 console.log( nodes.length );

 var node \= UE.dom.domUtils.filterNodeList( divNodes, function ( node ) {
     return node.tagName.toLowerCase() \=== 'div';
 }, false );

 //output: div
 console.log( node.nodeName );

#### isInNodeEndBoundary([UE.dom.Range](#UE.dom.Range) rng)

方法 静态

1.2.6.1

查询给定的range选区是否在给定的node节点内，且在该节点的最末尾

所属模块： [UE.dom.domUtils](#UE.dom.domUtils)

参数列表

参数名

类型

描述

rng

[UE.dom.Range](#UE.dom.Range)

需要判断的range对象， 该对象的startContainer不能为NULL

返回值

类型

描述

[Number](#Number)

如果给定的选取range对象是在node内部的最末端， 则返回1, 否则返回0

UE.utils
--------

模块

UEditor封装使用的静态工具函数

方法列表

方法签名

静态

描述

[each(Object obj, Function iterator)](#UE.utils.each(Object,Function))

是

用给定的迭代器遍历对象

[each(Array array, Function iterator)](#UE.utils.each(Array,Function))

是

用给定的迭代器遍历数组或类数组对象

[makeInstance(Object protoObject)](#UE.utils.makeInstance(Object))

是

以给定对象作为原型创建一个新对象

[extend(Object target, Object source)](#UE.utils.extend(Object,Object))

是

将source对象中的属性扩展到target对象上

[extend(Object target, Object source, Boolean isKeepTarget)](#UE.utils.extend(Object,Object,Boolean))

是

将source对象中的属性扩展到target对象上， 根据指定的isKeepTarget值决定是否保留目标对象中与 源对象属性名相同的属性值。

[extend2(Object target, Object... source)](#UE.utils.extend2(Object,Object...))

是

将给定的多个对象的属性复制到目标对象target上

[inherits(Object subClass, Object superClass)](#UE.utils.inherits(Object,Object))

是

模拟继承机制， 使得subClass继承自superClass

[bind(Function fn, Object content)](#UE.utils.bind(Function,Object))

是

用指定的context对象作为函数fn的上下文

[defer(Function fn, int delay)](#UE.utils.defer(Function,int))

是

创建延迟指定时间后执行的函数fn

[defer(Function fn, int delay, Boolean exclusion)](#UE.utils.defer(Function,int,Boolean))

是

创建延迟指定时间后执行的函数fn, 如果在延迟时间内再次执行该方法， 将会根据指定的exclusion的值， 决定是否取消前一次函数的执行， 如果exclusion的值为true， 则取消执行，反之，将继续执行前一个方法。

[indexOf(Array array, \* item)](#UE.utils.indexOf(Array,*))

是

获取元素item在数组array中首次出现的位置, 如果未找到item， 则返回-1

[indexOf(Array array, \* item, int start)](#UE.utils.indexOf(Array,*,int))

是

获取元素item数组array中首次出现的位置, 如果未找到item， 则返回-1。通过start的值可以指定搜索的起始位置。

[removeItem(Array array, \* item)](#UE.utils.removeItem(Array,*))

是

移除数组array中所有的元素item

[trim(String str)](#UE.utils.trim(String))

是

删除字符串str的首尾空格

[listToMap(String str)](#UE.utils.listToMap(String))

是

将字符串str以','分隔成数组后，将该数组转换成哈希对象， 其生成的hash对象的key为数组中的元素， value为1

[listToMap(Array arr)](#UE.utils.listToMap(Array))

是

将字符串数组转换成哈希对象， 其生成的hash对象的key为数组中的元素， value为1

[unhtml(String str)](#UE.utils.unhtml(String))

是

将str中的html符号转义,将转义“'，&，<，"，>”五个字符

[html(String str)](#UE.utils.html(String))

是

将str中的转义字符还原成html字符

[cssStyleToDomStyle(String cssName)](#UE.utils.cssStyleToDomStyle(String))

是

将css样式转换为驼峰的形式

[loadFile(DomDocument document, Object options)](#UE.utils.loadFile(DomDocument,Object))

是

动态加载文件到doc中

[loadFile(DomDocument document, Object options, Function fn)](#UE.utils.loadFile(DomDocument,Object,Function))

是

动态加载文件到doc中，加载成功后执行的回调函数fn

[isEmptyObject(\* obj)](#UE.utils.isEmptyObject(*))

是

判断obj对象是否为空

[clone(Object source)](#UE.utils.clone(Object))

是

克隆对象

[clone(Object source, Object target)](#UE.utils.clone(Object,Object))

是

深度克隆对象，将source的属性克隆到target对象， 会覆盖target重名的属性。

[transUnitToPx()](#UE.utils.transUnitToPx())

是

把cm／pt为单位的值转换为px为单位的值

[domReady(Function fn)](#UE.utils.domReady(Function))

是

在dom树ready之后执行给定的回调函数

[isString(\* object)](#UE.utils.isString(*))

是

判断给定的对象是否是字符串

[isArray(\* object)](#UE.utils.isArray(*))

是

判断给定的对象是否是数组

[isFunction(\* object)](#UE.utils.isFunction(*))

是

判断给定的对象是否是一个Function

[isNumber(\* object)](#UE.utils.isNumber(*))

是

判断给定的对象是否是Number

[isRegExp(\* object)](#UE.utils.isRegExp(*))

是

判断给定的对象是否是一个正则表达式

[isObject(\* object)](#UE.utils.isObject(*))

是

判断给定的对象是否是一个普通对象

模块成员详细描述([UE.utils](#UE.utils))

#### each([Object](#Object) obj, [Function](#Function) iterator)

方法 静态

1.2.6.1

用给定的迭代器遍历对象

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

obj

[Object](#Object)

需要遍历的对象

iterator

[Function](#Function)

迭代器， 该方法接受两个参数， 第一个参数是当前所处理的value， 第二个参数是当前遍历对象的key

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 var demoObj \= {
     key1: 1,
     key2: 2
 };

 //output: key1: 1, key2: 2
 UE.utils.each( demoObj, funciton ( value, key ) {

     console.log( key + ":" + value );

 } );

#### each([Array](#Array) array, [Function](#Function) iterator)

方法 静态

1.2.6.1

用给定的迭代器遍历数组或类数组对象

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

array

[Array](#Array)

需要遍历的数组或者类数组

iterator

[Function](#Function)

迭代器， 该方法接受两个参数， 第一个参数是当前所处理的value， 第二个参数是当前遍历对象的key

示例

javascript代码：

1
2
3
4
5
6
7
8

 var divs \= document.getElmentByTagNames( "div" );

 //output: 0: DIV, 1: DIV ...
 UE.utils.each( divs, funciton ( value, key ) {

     console.log( key + ":" + value.tagName );

 } );

#### makeInstance([Object](#Object) protoObject)

方法 静态

1.2.6.1

以给定对象作为原型创建一个新对象

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

protoObject

[Object](#Object)

该对象将作为新创建对象的原型

返回值

类型

描述

[Object](#Object)

新的对象， 该对象的原型是给定的protoObject对象

示例

javascript代码：

1
2
3
4
5

 var protoObject \= { sayHello: function () { console.log('Hello UEditor!'); } };

 var newObject \= UE.utils.makeInstance( protoObject );
 //output: Hello UEditor!
 newObject.sayHello();

#### extend([Object](#Object) target, [Object](#Object) source)

方法 静态

1.2.6.1

将source对象中的属性扩展到target对象上

*   提示： 该方法将强制把source对象上的属性复制到target对象上

所属模块： [UE.utils](#UE.utils)

参考

[UE.utils.extend(Object,Object,Boolean)](#UE.utils.extend(Object,Object,Boolean))

参数列表

参数名

类型

描述

target

[Object](#Object)

目标对象， 新的属性将附加到该对象上

source

[Object](#Object)

源对象， 该对象的属性会被附加到target对象上

返回值

类型

描述

[Object](#Object)

返回target对象

示例

javascript代码：

1
2
3
4
5
6
7

 var target \= { name: 'target', sex: 1 },
      source \= { name: 'source', age: 17 };

 UE.utils.extend( target, source );

 //output: { name: 'source', sex: 1, age: 17 }
 console.log( target );

#### extend([Object](#Object) target, [Object](#Object) source, [Boolean](#Boolean) isKeepTarget)

方法 静态

1.2.6.1

将source对象中的属性扩展到target对象上， 根据指定的isKeepTarget值决定是否保留目标对象中与 源对象属性名相同的属性值。

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

target

[Object](#Object)

目标对象， 新的属性将附加到该对象上

source

[Object](#Object)

源对象， 该对象的属性会被附加到target对象上

isKeepTarget

[Boolean](#Boolean)

是否保留目标对象中与源对象中属性名相同的属性

返回值

类型

描述

[Object](#Object)

返回target对象

示例

javascript代码：

1
2
3
4
5
6
7

 var target \= { name: 'target', sex: 1 },
      source \= { name: 'source', age: 17 };

 UE.utils.extend( target, source, true );

 //output: { name: 'target', sex: 1, age: 17 }
 console.log( target );

#### extend2([Object](#Object) target, [Object...](#Object...) source)

方法 静态

1.2.6.1

将给定的多个对象的属性复制到目标对象target上

*   提示： 该方法将强制把源对象上的属性复制到target对象上

*   提示： 该方法支持两个及以上的参数， 从第二个参数开始， 其属性都会被复制到第一个参数上。 如果遇到同名的属性， 将会覆盖掉之前的值。

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

target

[Object](#Object)

目标对象， 新的属性将附加到该对象上

source

[Object...](#Object...)

源对象， 支持多个对象， 该对象的属性会被附加到target对象上

返回值

类型

描述

[Object](#Object)

返回target对象

示例

javascript代码：

1
2
3
4
5
6
7
8

 var target \= {},
     source1 \= { name: 'source', age: 17 },
     source2 \= { title: 'dev' };

 UE.utils.extend2( target, source1, source2 );

 //output: { name: 'source', age: 17, title: 'dev' }
 console.log( target );

#### inherits([Object](#Object) subClass, [Object](#Object) superClass)

方法 静态

1.2.6.1

模拟继承机制， 使得subClass继承自superClass

*   警告： 该方法只能让subClass继承超类的原型， subClass对象自身的属性和方法不会被继承

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

subClass

[Object](#Object)

子类对象

superClass

[Object](#Object)

超类对象

返回值

类型

描述

[Object](#Object)

继承superClass后的子类对象

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17
18
19

 function SuperClass(){
     this.name \= "小李";
 }

 SuperClass.prototype \= {
     hello:function(str){
         console.log(this.name + str);
     }
 }

 function SubClass(){
     this.name \= "小张";
 }

 UE.utils.inherits(SubClass,SuperClass);

 var sub \= new SubClass();
 //output: '小张早上好!
 sub.hello("早上好!");

#### bind([Function](#Function) fn, [Object](#Object) content)

方法 静态

1.2.6.1

用指定的context对象作为函数fn的上下文

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

fn

[Function](#Function)

需要绑定上下文的函数对象

content

[Object](#Object)

函数fn新的上下文对象

返回值

类型

描述

[Function](#Function)

一个新的函数， 该函数作为原始函数fn的代理， 将完成fn的上下文调换工作。

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14

 var name \= 'window',
     newTest \= null;

 function test () {
     console.log( this.name );
 }

 newTest \= UE.utils.bind( test, { name: 'object' } );

 //output: object
 newTest();

 //output: window
 test();

#### defer([Function](#Function) fn, [int](#int) delay)

方法 静态

1.2.6.1

创建延迟指定时间后执行的函数fn

*   警告： 该方法的时间控制是不精确的，仅仅只能保证函数的执行是在给定的时间之后， 而不能保证刚好到达延迟时间时执行。

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

fn

[Function](#Function)

需要延迟执行的函数对象

delay

[int](#int)

延迟的时间， 单位是毫秒

返回值

类型

描述

[Function](#Function)

目标函数fn的代理函数， 只有执行该函数才能起到延时效果

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11

 var start \= 0;

 function test(){
     console.log( new Date() \- start );
 }

 var testDefer \= UE.utils.defer( test, 1000 );
 //
 start \= new Date();
 //output: (大约在1000毫秒之后输出) 1000
 testDefer();

#### defer([Function](#Function) fn, [int](#int) delay, [Boolean](#Boolean) exclusion)

方法 静态

1.2.6.1

创建延迟指定时间后执行的函数fn, 如果在延迟时间内再次执行该方法， 将会根据指定的exclusion的值， 决定是否取消前一次函数的执行， 如果exclusion的值为true， 则取消执行，反之，将继续执行前一个方法。

*   警告： 该方法的时间控制是不精确的，仅仅只能保证函数的执行是在给定的时间之后， 而不能保证刚好到达延迟时间时执行。

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

fn

[Function](#Function)

需要延迟执行的函数对象

delay

[int](#int)

延迟的时间， 单位是毫秒

exclusion

[Boolean](#Boolean)

如果在延迟时间内再次执行该函数，该值将决定是否取消执行前一次函数的执行， 值为true表示取消执行， 反之则将在执行前一次函数之后才执行本次函数调用。

返回值

类型

描述

[Function](#Function)

目标函数fn的代理函数， 只有执行该函数才能起到延时效果

示例

javascript代码：

1
2
3
4
5
6
7
8
9

 function test(){
     console.log(1);
 }

 var testDefer \= UE.utils.defer( test, 1000, true );

 //output: (两次调用仅有一次输出) 1
 testDefer();
 testDefer();

#### indexOf([Array](#Array) array, [\*](#*) item)

方法 静态

1.2.6.1

获取元素item在数组array中首次出现的位置, 如果未找到item， 则返回-1

*   提示： 该方法的匹配过程使用的是恒等“===”

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

array

[Array](#Array)

需要查找的数组对象

item

[\*](#*)

需要在目标数组中查找的值

返回值

类型

描述

[int](#int)

返回item在目标数组array中首次出现的位置， 如果在数组中未找到item， 则返回-1

示例

javascript代码：

1
2
3
4
5

 var item \= 1,
     arr \= \[ 3, 4, 6, 8, 1, 1, 2 \];

 //output: 4
 console.log( UE.utils.indexOf( arr, item ) );

#### indexOf([Array](#Array) array, [\*](#*) item, [int](#int) start)

方法 静态

1.2.6.1

获取元素item数组array中首次出现的位置, 如果未找到item， 则返回-1。通过start的值可以指定搜索的起始位置。

*   提示： 该方法的匹配过程使用的是恒等“===”

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

array

[Array](#Array)

需要查找的数组对象

item

[\*](#*)

需要在目标数组中查找的值

start

[int](#int)

搜索的起始位置

返回值

类型

描述

[int](#int)

返回item在目标数组array中的start位置之后首次出现的位置， 如果在数组中未找到item， 则返回-1

示例

javascript代码：

1
2
3
4
5

 var item \= 1,
     arr \= \[ 3, 4, 6, 8, 1, 2, 8, 3, 2, 1, 1, 4 \];

 //output: 9
 console.log( UE.utils.indexOf( arr, item, 5 ) );

#### removeItem([Array](#Array) array, [\*](#*) item)

方法 静态

1.2.6.1

移除数组array中所有的元素item

*   提示： 该方法的匹配过程使用的是恒等“===”

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

array

[Array](#Array)

要移除元素的目标数组

item

[\*](#*)

将要被移除的元素

示例

javascript代码：

1
2
3
4
5

 var arr \= \[ 4, 5, 7, 1, 3, 4, 6 \];

 UE.utils.removeItem( arr, 4 );
 //output: \[ 5, 7, 1, 3, 6 \]
 console.log( arr );

#### trim([String](#String) str)

方法 静态

1.2.6.1

删除字符串str的首尾空格

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

str

[String](#String)

需要删除首尾空格的字符串

返回值

类型

描述

[String](#String)

删除了首尾的空格后的字符串

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10

 var str \= " UEdtior ";

 //output: 9
 console.log( str.length );

 //output: 7
 console.log( UE.utils.trim( " UEdtior " ).length );

 //output: 9
 console.log( str.length );

#### listToMap([String](#String) str)

方法 静态

1.2.6.1

将字符串str以','分隔成数组后，将该数组转换成哈希对象， 其生成的hash对象的key为数组中的元素， value为1

*   警告： 该方法在生成的hash对象中，会为每一个key同时生成一个另一个全大写的key。

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

str

[String](#String)

该字符串将被以','分割为数组， 然后进行转化

返回值

类型

描述

[Object](#Object)

转化之后的hash对象

示例

javascript代码：

1
2

 //output: Object {UEdtior: 1, UEDTIOR: 1, Hello: 1, HELLO: 1}
 console.log( UE.utils.listToMap( 'UEdtior,Hello' ) );

#### listToMap([Array](#Array) arr)

方法 静态

1.2.6.1

将字符串数组转换成哈希对象， 其生成的hash对象的key为数组中的元素， value为1

*   警告： 该方法在生成的hash对象中，会为每一个key同时生成一个另一个全大写的key。

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

arr

[Array](#Array)

字符串数组

返回值

类型

描述

[Object](#Object)

转化之后的hash对象

示例

javascript代码：

1
2

 //output: Object {UEdtior: 1, UEDTIOR: 1, Hello: 1, HELLO: 1}
 console.log( UE.utils.listToMap( \[ 'UEdtior', 'Hello' \] ) );

#### unhtml([String](#String) str)

方法 静态

1.2.6.1

将str中的html符号转义,将转义“'，&，<，"，>”五个字符

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

str

[String](#String)

需要转义的字符串

返回值

类型

描述

[String](#String)

转义后的字符串

示例

javascript代码：

1
2
3
4

 var html \= '<body>&</body>';

 //output: &lt;body&gt;&amp;&lt;/body&gt;
 console.log( UE.utils.unhtml( html ) );

#### html([String](#String) str)

方法 静态

1.2.6.1

将str中的转义字符还原成html字符

所属模块： [UE.utils](#UE.utils)

参考

[UE.utils.unhtml(String);](#UE.utils.unhtml(String);)

参数列表

参数名

类型

描述

str

[String](#String)

需要逆转义的字符串

返回值

类型

描述

[String](#String)

逆转义后的字符串

示例

javascript代码：

1
2
3
4

 var str \= '&lt;body&gt;&amp;&lt;/body&gt;';

 //output: <body>&</body>
 console.log( UE.utils.html( str ) );

#### cssStyleToDomStyle([String](#String) cssName)

方法 静态

1.2.6.1

将css样式转换为驼峰的形式

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

cssName

[String](#String)

需要转换的css样式名

返回值

类型

描述

[String](#String)

转换成驼峰形式后的css样式名

示例

javascript代码：

1
2
3
4

 var str \= 'border-top';

 //output: borderTop
 console.log( UE.utils.cssStyleToDomStyle( str ) );

#### loadFile([DomDocument](#DomDocument) document, [Object](#Object) options)

方法 静态

1.2.6.1

动态加载文件到doc中

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

document

[DomDocument](#DomDocument)

需要加载资源文件的文档对象

options

[Object](#Object)

加载资源文件的属性集合， 取值请参考代码示例

示例

javascript代码：

1
2
3
4
5
6

 UE.utils.loadFile( document, {
     src:"test.js",
     tag:"script",
     type:"text/javascript",
     defer:"defer"
 } );

#### loadFile([DomDocument](#DomDocument) document, [Object](#Object) options, [Function](#Function) fn)

方法 静态

1.2.6.1

动态加载文件到doc中，加载成功后执行的回调函数fn

*   警告： 对于在同一个文档中多次加载同一URL的文件， 该方法会在第一次加载之后缓存该请求， 在此之后的所有同一URL的请求， 将会直接触发回调。

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

document

[DomDocument](#DomDocument)

需要加载资源文件的文档对象

options

[Object](#Object)

加载资源文件的属性集合， 该集合支持的值是script标签和style标签支持的所有属性。

fn

[Function](#Function)

资源文件加载成功之后执行的回调

示例

javascript代码：

1
2
3
4
5
6
7
8

 UE.utils.loadFile( document, {
     src:"test.js",
     tag:"script",
     type:"text/javascript",
     defer:"defer"
 }, function () {
     console.log('加载成功');
 } );

#### isEmptyObject([\*](#*) obj)

方法 静态

1.2.6.1

判断obj对象是否为空

*   提示： 如果判断的对象是NULL， 将直接返回true， 如果是数组且为空， 返回true， 如果是字符串， 且字符串为空， 返回true， 如果是普通对象， 且该对象没有任何实例属性， 返回true

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

obj

[\*](#*)

需要判断的对象

返回值

类型

描述

[Boolean](#Boolean)

对象是否为空

示例

javascript代码：

 1
 2
 3
 4
 5
 6
 7
 8
 9
10
11
12
13
14
15
16
17

 //output: true
 console.log( UE.utils.isEmptyObject( {} ) );

 //output: true
 console.log( UE.utils.isEmptyObject( \[\] ) );

 //output: true
 console.log( UE.utils.isEmptyObject( "" ) );

 //output: false
 console.log( UE.utils.isEmptyObject( { key: 1 } ) );

 //output: false
 console.log( UE.utils.isEmptyObject( \[1\] ) );

 //output: false
 console.log( UE.utils.isEmptyObject( "1" ) );

#### clone([Object](#Object) source)

方法 静态

1.2.6.1

克隆对象

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

source

[Object](#Object)

源对象

返回值

类型

描述

[Object](#Object)

source的一个副本

#### clone([Object](#Object) source, [Object](#Object) target)

方法 静态

1.2.6.1

深度克隆对象，将source的属性克隆到target对象， 会覆盖target重名的属性。

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

source

[Object](#Object)

源对象

target

[Object](#Object)

目标对象

返回值

类型

描述

[Object](#Object)

附加了source对象所有属性的target对象

#### transUnitToPx()

方法 静态

1.2.6.1

把cm／pt为单位的值转换为px为单位的值

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

返回值

类型

描述

[String](#String)

转换为px为计量单位的值的字符串

示例

javascript代码：

1
2
3
4
5

 //output: 500px
 console.log( UE.utils.transUnitToPx( '20cm' ) );

 //output: 27px
 console.log( UE.utils.transUnitToPx( '20pt' ) );

#### domReady([Function](#Function) fn)

方法 静态

1.2.6.1

在dom树ready之后执行给定的回调函数

*   提示： 如果在执行该方法的时候， dom树已经ready， 那么回调函数将立刻执行

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

fn

[Function](#Function)

dom树ready之后的回调函数

示例

javascript代码：

1
2
3
4
5

 UE.utils.domReady( function () {

     console.log('123');

 } );

#### isString([\*](#*) object)

方法 静态

1.2.6.1

判断给定的对象是否是字符串

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

object

[\*](#*)

需要判断的对象

返回值

类型

描述

[Boolean](#Boolean)

给定的对象是否是字符串

#### isArray([\*](#*) object)

方法 静态

1.2.6.1

判断给定的对象是否是数组

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

object

[\*](#*)

需要判断的对象

返回值

类型

描述

[Boolean](#Boolean)

给定的对象是否是数组

#### isFunction([\*](#*) object)

方法 静态

1.2.6.1

判断给定的对象是否是一个Function

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

object

[\*](#*)

需要判断的对象

返回值

类型

描述

[Boolean](#Boolean)

给定的对象是否是Function

#### isNumber([\*](#*) object)

方法 静态

1.2.6.1

判断给定的对象是否是Number

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

object

[\*](#*)

需要判断的对象

返回值

类型

描述

[Boolean](#Boolean)

给定的对象是否是Number

#### isRegExp([\*](#*) object)

方法 静态

1.2.6.1

判断给定的对象是否是一个正则表达式

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

object

[\*](#*)

需要判断的对象

返回值

类型

描述

[Boolean](#Boolean)

给定的对象是否是正则表达式

#### isObject([\*](#*) object)

方法 静态

1.2.6.1

判断给定的对象是否是一个普通对象

所属模块： [UE.utils](#UE.utils)

参数列表

参数名

类型

描述

object

[\*](#*)

需要判断的对象

返回值

类型

描述

[Boolean](#Boolean)

给定的对象是否是普通对象

### 辅助接口

该接口包提供的接口，大多数都是本地原生接口，这里只是把这些接口归纳起来以方便大家查看。

#### String

辅助接口

原生String对象， 字符串

#### Function

辅助接口

原生Function对象， 函数

#### Object

辅助接口

原生Object对象， 普通对象

#### Boolean

辅助接口

原生Boolean对象， 布尔值

#### Number

辅助接口

原生Number对象， 数值

#### NULL

辅助接口

原生NULL对象， 空

#### Array

辅助接口

原生Array对象， 数组

#### Node

辅助接口

浏览器Node， dom节点

#### Element

辅助接口

浏览器Element， dom元素

#### uNode

辅助接口

UEditor模拟dom节点对象

快速导航

*   [命令列表](#COMMAND.LIST)
[](#COMMAND.LIST)*   [](#COMMAND.LIST)[UE](#UE)
*   [UE.Editor](#UE.Editor)
*   [UE.EventBase](#UE.EventBase)
*   [UE.uNode](#UE.uNode)
*   [UE.dom](#UE.dom)
*   [UE.dom.Range](#UE.dom.Range)
*   [UE.dom.Selection](#UE.dom.Selection)
*   [UE.ajax](#UE.ajax)
*   [UE.browser](#UE.browser)
*   [UE.dom.domUtils](#UE.dom.domUtils)
*   [UE.utils](#UE.utils)

*   UE
    
    *   [getListener(Object obj, String type, Boolean force)](#UE.getListener(Object,String,Boolean))
    *   [filterNode(Object root, Object rules)](#UE.filterNode(Object,Object))
    *   [filterWord(String html)](#UE.filterWord(String))
    *   [htmlparser(String htmlstr, Boolean ignoreBlank)](#UE.htmlparser(String,Boolean))
    
*   UE.Editor
    
    *   [ready](#UE.Editor:ready)
    *   [destroy](#UE.Editor:destroy)
    *   [reset](#UE.Editor:reset)
    *   [focus](#UE.Editor:focus)
    *   [langReady](#UE.Editor:langReady)
    *   [beforeExecCommand](#UE.Editor:beforeExecCommand)
    *   [afterExecCommand](#UE.Editor:afterExecCommand)
    *   [firstBeforeExecCommand](#UE.Editor:firstBeforeExecCommand)
    *   [beforeGetContent](#UE.Editor:beforeGetContent)
    *   [afterGetContent](#UE.Editor:afterGetContent)
    *   [getAllHtml](#UE.Editor:getAllHtml)
    *   [beforeSetContent](#UE.Editor:beforeSetContent)
    *   [afterSetContent](#UE.Editor:afterSetContent)
    *   [selectionchange](#UE.Editor:selectionchange)
    *   [beforeSelectionChange](#UE.Editor:beforeSelectionChange)
    *   [afterSelectionChange](#UE.Editor:afterSelectionChange)
    *   [contentChange](#UE.Editor:contentChange)
    *   [Editor()](#UE.Editor:Editor())
    *   [Editor(Object setting)](#UE.Editor:Editor(Object))
    *   [ready(Function fn)](#UE.Editor:ready(Function))
    *   [setOpt(String key, \* val)](#UE.Editor:setOpt(String,*))
    *   [setOpt(Object options)](#UE.Editor:setOpt(Object))
    *   [destroy()](#UE.Editor:destroy())
    *   [render(String containerId)](#UE.Editor:render(String))
    *   [render(Element containerDom)](#UE.Editor:render(Element))
    *   [sync()](#UE.Editor:sync())
    *   [sync(String formID)](#UE.Editor:sync(String))
    *   [setHeight(Number number)](#UE.Editor:setHeight(Number))
    *   [addshortcutkey(Object keyset)](#UE.Editor:addshortcutkey(Object))
    *   [addshortcutkey(String cmd, String keys)](#UE.Editor:addshortcutkey(String,String))
    *   [getContent()](#UE.Editor:getContent())
    *   [getContent(Function fn)](#UE.Editor:getContent(Function))
    *   [getAllHtml()](#UE.Editor:getAllHtml())
    *   [getPlainTxt()](#UE.Editor:getPlainTxt())
    *   [getContentTxt()](#UE.Editor:getContentTxt())
    *   [setContent(String html)](#UE.Editor:setContent(String))
    *   [setContent(String html, Boolean isAppendTo)](#UE.Editor:setContent(String,Boolean))
    *   [focus()](#UE.Editor:focus())
    *   [focus(Boolean toEnd)](#UE.Editor:focus(Boolean))
    *   [execCommand(String cmdName)](#UE.Editor:execCommand(String))
    *   [queryCommandState(String cmdName)](#UE.Editor:queryCommandState(String))
    *   [queryCommandValue(String cmdName)](#UE.Editor:queryCommandValue(String))
    *   [hasContents()](#UE.Editor:hasContents())
    *   [hasContents(Array tags)](#UE.Editor:hasContents(Array))
    *   [reset()](#UE.Editor:reset())
    *   [setEnabled()](#UE.Editor:setEnabled())
    *   [setDisabled()](#UE.Editor:setDisabled())
    *   [setDisabled(String except)](#UE.Editor:setDisabled(String))
    *   [setDisabled(Array except)](#UE.Editor:setDisabled(Array))
    *   [setShow()](#UE.Editor:setShow())
    *   [setHide()](#UE.Editor:setHide())
    *   [getLang(String path)](#UE.Editor:getLang(String))
    *   [getContentLength()](#UE.Editor:getContentLength())
    *   [getContentLength(Boolean ingoneHtml)](#UE.Editor:getContentLength(Boolean))
    *   [addInputRule(Function rule)](#UE.Editor:addInputRule(Function))
    *   [filterInputRule(UE.uNode root)](#UE.Editor:filterInputRule(UE.uNode))
    *   [addOutputRule(Function rule)](#UE.Editor:addOutputRule(Function))
    *   [filterOutputRule(UE.uNode root)](#UE.Editor:filterOutputRule(UE.uNode))
    
*   UE.EventBase
    
    *   [EventBase()](#UE.EventBase:EventBase())
    *   [addListener(String types, Function fn)](#UE.EventBase:addListener(String,Function))
    *   [removeListener(String types, Function fn)](#UE.EventBase:removeListener(String,Function))
    *   [fireEvent(String types)](#UE.EventBase:fireEvent(String))
    *   [fireEvent(String types, \*... options)](#UE.EventBase:fireEvent(String,*...))
    
*   UE.uNode
    
    *   [uNode(Object attr)](#UE.uNode:uNode(Object))
    *   [toHtml()](#UE.uNode:toHtml())
    *   [toHtml(Boolean formatter)](#UE.uNode:toHtml(Boolean))
    *   [innerHTML()](#UE.uNode:innerHTML())
    *   [innerHTML(String htmlstr)](#UE.uNode:innerHTML(String))
    *   [innerText()](#UE.uNode:innerText())
    *   [innerText(String textStr)](#UE.uNode:innerText(String))
    *   [getData()](#UE.uNode:getData())
    *   [firstChild()](#UE.uNode:firstChild())
    *   [lastChild()](#UE.uNode:lastChild())
    *   [previousSibling()](#UE.uNode:previousSibling())
    *   [nextSibling()](#UE.uNode:nextSibling())
    *   [replaceChild(UE.uNode target, UE.uNode source)](#UE.uNode:replaceChild(UE.uNode,UE.uNode))
    *   [appendChild(UE.uNode node)](#UE.uNode:appendChild(UE.uNode))
    *   [insertBefore(UE.uNode target, UE.uNode source)](#UE.uNode:insertBefore(UE.uNode,UE.uNode))
    *   [insertAfter(UE.uNode target, UE.uNode source)](#UE.uNode:insertAfter(UE.uNode,UE.uNode))
    *   [removeChild(UE.uNode node, Boolean keepChildren)](#UE.uNode:removeChild(UE.uNode,Boolean))
    *   [getAttr(String attrName)](#UE.uNode:getAttr(String))
    *   [setAttr(String attrName, \* attrVal)](#UE.uNode:setAttr(String,*))
    *   [getIndex()](#UE.uNode:getIndex())
    *   [getNodeById(String id)](#UE.uNode:getNodeById(String))
    *   [getNodesByTagName(String tagNames)](#UE.uNode:getNodesByTagName(String))
    *   [getStyle(String name)](#UE.uNode:getStyle(String))
    *   [setStyle(String name, String val)](#UE.uNode:setStyle(String,String))
    *   [traversal(Function fn)](#UE.uNode:traversal(Function))
    
*   UE.dom.Range
    
    *   [Range(Document document)](#UE.dom.Range:Range(Document))
    *   [startContainer](#UE.dom.Range:startContainer)
    *   [startOffset](#UE.dom.Range:startOffset)
    *   [endContainer](#UE.dom.Range:endContainer)
    *   [endOffset](#UE.dom.Range:endOffset)
    *   [collapsed](#UE.dom.Range:collapsed)
    *   [document](#UE.dom.Range:document)
    *   [cloneContents()](#UE.dom.Range:cloneContents())
    *   [deleteContents()](#UE.dom.Range:deleteContents())
    *   [extractContents()](#UE.dom.Range:extractContents())
    *   [setStart(Node node, int offset)](#UE.dom.Range:setStart(Node,int))
    *   [setEnd(Node node, int offset)](#UE.dom.Range:setEnd(Node,int))
    *   [setStartAfter(Node node)](#UE.dom.Range:setStartAfter(Node))
    *   [setStartBefore(Node node)](#UE.dom.Range:setStartBefore(Node))
    *   [setEndAfter(Node node)](#UE.dom.Range:setEndAfter(Node))
    *   [setEndBefore(Node node)](#UE.dom.Range:setEndBefore(Node))
    *   [setStartAtFirst(Node node)](#UE.dom.Range:setStartAtFirst(Node))
    *   [setStartAtLast(Node node)](#UE.dom.Range:setStartAtLast(Node))
    *   [setEndAtFirst(Node node)](#UE.dom.Range:setEndAtFirst(Node))
    *   [setEndAtLast(Node node)](#UE.dom.Range:setEndAtLast(Node))
    *   [selectNode(Node node)](#UE.dom.Range:selectNode(Node))
    *   [selectNodeContents(Node node)](#UE.dom.Range:selectNodeContents(Node))
    *   [cloneRange()](#UE.dom.Range:cloneRange())
    *   [collapse()](#UE.dom.Range:collapse())
    *   [collapse(Boolean toStart)](#UE.dom.Range:collapse(Boolean))
    *   [shrinkBoundary()](#UE.dom.Range:shrinkBoundary())
    *   [shrinkBoundary(Boolean ignoreEnd)](#UE.dom.Range:shrinkBoundary(Boolean))
    *   [getCommonAncestor()](#UE.dom.Range:getCommonAncestor())
    *   [getCommonAncestor(Boolean includeSelf)](#UE.dom.Range:getCommonAncestor(Boolean))
    *   [getCommonAncestor(Boolean includeSelf, Boolean ignoreTextNode)](#UE.dom.Range:getCommonAncestor(Boolean,Boolean))
    *   [trimBoundary()](#UE.dom.Range:trimBoundary())
    *   [trimBoundary(Boolean ignoreEnd)](#UE.dom.Range:trimBoundary(Boolean))
    *   [txtToElmBoundary()](#UE.dom.Range:txtToElmBoundary())
    *   [txtToElmBoundary(Boolean ignoreCollapsed)](#UE.dom.Range:txtToElmBoundary(Boolean))
    *   [insertNode(Node node)](#UE.dom.Range:insertNode(Node))
    *   [setCursor()](#UE.dom.Range:setCursor())
    *   [setCursor(Boolean toEnd)](#UE.dom.Range:setCursor(Boolean))
    *   [createBookmark(Boolean serialize)](#UE.dom.Range:createBookmark(Boolean))
    *   [moveToBookmark(BookMark bookmark)](#UE.dom.Range:moveToBookmark(BookMark))
    *   [enlarge()](#UE.dom.Range:enlarge())
    *   [enlarge(Boolean toBlock)](#UE.dom.Range:enlarge(Boolean))
    *   [adjustmentBoundary()](#UE.dom.Range:adjustmentBoundary())
    *   [applyInlineStyle(String tagName)](#UE.dom.Range:applyInlineStyle(String))
    *   [applyInlineStyle(String tagName, Object attrs)](#UE.dom.Range:applyInlineStyle(String,Object))
    *   [removeInlineStyle(String tagName)](#UE.dom.Range:removeInlineStyle(String))
    *   [removeInlineStyle(Array tagNameArr)](#UE.dom.Range:removeInlineStyle(Array))
    *   [getClosedNode()](#UE.dom.Range:getClosedNode())
    *   [select()](#UE.dom.Range:select())
    *   [scrollToView(Window win)](#UE.dom.Range:scrollToView(Window))
    *   [scrollToView(Window win, Number offset)](#UE.dom.Range:scrollToView(Window,Number))
    *   [equals()](#UE.dom.Range:equals())
    *   [traversal(Function doFn)](#UE.dom.Range:traversal(Function))
    *   [traversal(Function doFn, Function filterFn)](#UE.dom.Range:traversal(Function,Function))
    
*   UE.dom.Selection
    
    *   [getNative()](#UE.dom.Selection:getNative())
    *   [getIERange()](#UE.dom.Selection:getIERange())
    *   [cache()](#UE.dom.Selection:cache())
    *   [getStartElementPath()](#UE.dom.Selection:getStartElementPath())
    *   [clear()](#UE.dom.Selection:clear())
    *   [isFocus()](#UE.dom.Selection:isFocus())
    *   [getRange()](#UE.dom.Selection:getRange())
    *   [getStart()](#UE.dom.Selection:getStart())
    *   [getText()](#UE.dom.Selection:getText())
    *   [clearRange()](#UE.dom.Selection:clearRange())
    
*   UE.ajax
    
    *   [request(URLString url, Object ajaxOptions)](#UE.ajax.request(URLString,Object))
    *   [request(Object ajaxOptions)](#UE.ajax.request(Object))
    
*   UE.browser
    
    *   [ie](#UE.browser.ie)
    *   [opera](#UE.browser.opera)
    *   [webkit](#UE.browser.webkit)
    *   [mac](#UE.browser.mac)
    *   [quirks](#UE.browser.quirks)
    *   [gecko](#UE.browser.gecko)
    *   [ie9Compat](#UE.browser.ie9Compat)
    *   [ie8](#UE.browser.ie8)
    *   [ie8Compat](#UE.browser.ie8Compat)
    *   [ie7Compat](#UE.browser.ie7Compat)
    *   [ie6Compat](#UE.browser.ie6Compat)
    *   [chrome](#UE.browser.chrome)
    *   [safari](#UE.browser.safari)
    *   [version](#UE.browser.version)
    *   [isCompatible](#UE.browser.isCompatible)
    
*   UE.dom.domUtils
    
    *   [getPosition(Node nodeA, Node nodeB)](#UE.dom.domUtils.getPosition(Node,Node))
    *   [getNodeIndex(Node node)](#UE.dom.domUtils.getNodeIndex(Node))
    *   [getNodeIndex(Node node, Boolean mergeTextNode)](#UE.dom.domUtils.getNodeIndex(Node,Boolean))
    *   [inDoc(Node node, DomDocument doc)](#UE.dom.domUtils.inDoc(Node,DomDocument))
    *   [findParent(Node node, Function filterFn)](#UE.dom.domUtils.findParent(Node,Function))
    *   [findParent(Node node, Function filterFn, Boolean includeSelf)](#UE.dom.domUtils.findParent(Node,Function,Boolean))
    *   [findParentByTagName(Node node, Array tagNames)](#UE.dom.domUtils.findParentByTagName(Node,Array))
    *   [findParentByTagName(Node node, Array tagNames, Boolean includeSelf)](#UE.dom.domUtils.findParentByTagName(Node,Array,Boolean))
    *   [findParents(Node node)](#UE.dom.domUtils.findParents(Node))
    *   [findParents(Node node, Boolean includeSelf)](#UE.dom.domUtils.findParents(Node,Boolean))
    *   [insertAfter(Node node, Node newNode)](#UE.dom.domUtils.insertAfter(Node,Node))
    *   [remove(Node node)](#UE.dom.domUtils.remove(Node))
    *   [remove(Node node, Boolean keepChildren)](#UE.dom.domUtils.remove(Node,Boolean))
    *   [getNextDomNode(Node node)](#UE.dom.domUtils.getNextDomNode(Node))
    *   [getNextDomNode(Node node, Boolean startFromChild)](#UE.dom.domUtils.getNextDomNode(Node,Boolean))
    *   [getWindow(Node node)](#UE.dom.domUtils.getWindow(Node))
    *   [getCommonAncestor(Node nodeA, Node nodeB)](#UE.dom.domUtils.getCommonAncestor(Node,Node))
    *   [clearEmptySibling(Node node)](#UE.dom.domUtils.clearEmptySibling(Node))
    *   [clearEmptySibling(Node node, Boolean ignoreNext)](#UE.dom.domUtils.clearEmptySibling(Node,Boolean))
    *   [clearEmptySibling(Node node, Boolean ignoreNext, Boolean ignorePre)](#UE.dom.domUtils.clearEmptySibling(Node,Boolean,Boolean))
    *   [split(Node textNode, int offset)](#UE.dom.domUtils.split(Node,int))
    *   [isWhitespace(Node node)](#UE.dom.domUtils.isWhitespace(Node))
    *   [getXY(Node element)](#UE.dom.domUtils.getXY(Node))
    *   [on(Node element, String type, Function handler)](#UE.dom.domUtils.on(Node,String,Function))
    *   [on(Node element, Array type, Function handler)](#UE.dom.domUtils.on(Node,Array,Function))
    *   [un(Node element, String type, Function handler)](#UE.dom.domUtils.un(Node,String,Function))
    *   [un(Node element, Array type, Function handler)](#UE.dom.domUtils.un(Node,Array,Function))
    *   [isSameElement(Node nodeA, Node nodeB)](#UE.dom.domUtils.isSameElement(Node,Node))
    *   [isSameStyle(Node nodeA, Node nodeB)](#UE.dom.domUtils.isSameStyle(Node,Node))
    *   [isBlockElm(Node node)](#UE.dom.domUtils.isBlockElm(Node))
    *   [isBody(Element node)](#UE.dom.domUtils.isBody(Element))
    *   [breakParent(Node node, Node parent)](#UE.dom.domUtils.breakParent(Node,Node))
    *   [isEmptyInlineElement(Node node)](#UE.dom.domUtils.isEmptyInlineElement(Node))
    *   [trimWhiteTextNode(Element node)](#UE.dom.domUtils.trimWhiteTextNode(Element))
    *   [getElementsByTagName(Node node, String tagName)](#UE.dom.domUtils.getElementsByTagName(Node,String))
    *   [mergeToParent(Element node)](#UE.dom.domUtils.mergeToParent(Element))
    *   [mergeSibling(Element node)](#UE.dom.domUtils.mergeSibling(Element))
    *   [mergeSibling(Element node, Boolean ignorePre)](#UE.dom.domUtils.mergeSibling(Element,Boolean))
    *   [mergeSibling(Element node, Boolean ignorePre, Boolean ignoreNext)](#UE.dom.domUtils.mergeSibling(Element,Boolean,Boolean))
    *   [unSelectable(Element node)](#UE.dom.domUtils.unSelectable(Element))
    *   [removeAttributes(Node node, String attrNames)](#UE.dom.domUtils.removeAttributes(Node,String))
    *   [removeAttributes(Node node, Array attrNames)](#UE.dom.domUtils.removeAttributes(Node,Array))
    *   [createElement(DomDocument doc, String tagName, Object attrs)](#UE.dom.domUtils.createElement(DomDocument,String,Object))
    *   [setAttributes(Element node, Object attrs)](#UE.dom.domUtils.setAttributes(Element,Object))
    *   [getComputedStyle(Element element, String styleName)](#UE.dom.domUtils.getComputedStyle(Element,String))
    *   [removeClasses(Element ele, String classNames)](#UE.dom.domUtils.removeClasses(Element,String))
    *   [removeClasses(Element ele, Array classNames)](#UE.dom.domUtils.removeClasses(Element,Array))
    *   [addClass(Node ele, String classNames)](#UE.dom.domUtils.addClass(Node,String))
    *   [addClass(Node ele, Array classNames)](#UE.dom.domUtils.addClass(Node,Array))
    *   [hasClass(Node ele, String classNames)](#UE.dom.domUtils.hasClass(Node,String))
    *   [hasClass(Node ele, Array classNames)](#UE.dom.domUtils.hasClass(Node,Array))
    *   [preventDefault(Event evt)](#UE.dom.domUtils.preventDefault(Event))
    *   [removeStyle(Element element, String styleName)](#UE.dom.domUtils.removeStyle(Element,String))
    *   [getStyle(Element element, String styleName)](#UE.dom.domUtils.getStyle(Element,String))
    *   [setStyle(Element element, String styleName, String styleValue)](#UE.dom.domUtils.setStyle(Element,String,String))
    *   [setStyles(Element element, Object styles)](#UE.dom.domUtils.setStyles(Element,Object))
    *   [getChildCount(Element node)](#UE.dom.domUtils.getChildCount(Element))
    *   [getChildCount(Element node, Function fn)](#UE.dom.domUtils.getChildCount(Element,Function))
    *   [isEmptyNode(Node node)](#UE.dom.domUtils.isEmptyNode(Node))
    *   [scrollToView(Node node, window win, Number offsetTop)](#UE.dom.domUtils.scrollToView(Node,window,Number))
    *   [isBr(Node node)](#UE.dom.domUtils.isBr(Node))
    *   [isEmptyBlock(Element node)](#UE.dom.domUtils.isEmptyBlock(Element))
    *   [isEmptyBlock(Element node, RegExp reg)](#UE.dom.domUtils.isEmptyBlock(Element,RegExp))
    *   [setViewportOffset(Element element, Object offset)](#UE.dom.domUtils.setViewportOffset(Element,Object))
    *   [moveChild(Node src, Node tag)](#UE.dom.domUtils.moveChild(Node,Node))
    *   [moveChild(Node src, Node tag, Boolean dir)](#UE.dom.domUtils.moveChild(Node,Node,Boolean))
    *   [isTagNode(Node node, String tagName)](#UE.dom.domUtils.isTagNode(Node,String))
    *   [filterNodeList(Array nodeList, Function fn)](#UE.dom.domUtils.filterNodeList(Array,Function))
    *   [filterNodeList(Array nodeList, String tagNames)](#UE.dom.domUtils.filterNodeList(Array,String))
    *   [filterNodeList(Array nodeList, Function fn, Boolean forAll)](#UE.dom.domUtils.filterNodeList(Array,Function,Boolean))
    *   [isInNodeEndBoundary(UE.dom.Range rng)](#UE.dom.domUtils.isInNodeEndBoundary(UE.dom.Range))
    
*   UE.utils
    
    *   [each(Object obj, Function iterator)](#UE.utils.each(Object,Function))
    *   [each(Array array, Function iterator)](#UE.utils.each(Array,Function))
    *   [makeInstance(Object protoObject)](#UE.utils.makeInstance(Object))
    *   [extend(Object target, Object source)](#UE.utils.extend(Object,Object))
    *   [extend(Object target, Object source, Boolean isKeepTarget)](#UE.utils.extend(Object,Object,Boolean))
    *   [extend2(Object target, Object... source)](#UE.utils.extend2(Object,Object...))
    *   [inherits(Object subClass, Object superClass)](#UE.utils.inherits(Object,Object))
    *   [bind(Function fn, Object content)](#UE.utils.bind(Function,Object))
    *   [defer(Function fn, int delay)](#UE.utils.defer(Function,int))
    *   [defer(Function fn, int delay, Boolean exclusion)](#UE.utils.defer(Function,int,Boolean))
    *   [indexOf(Array array, \* item)](#UE.utils.indexOf(Array,*))
    *   [indexOf(Array array, \* item, int start)](#UE.utils.indexOf(Array,*,int))
    *   [removeItem(Array array, \* item)](#UE.utils.removeItem(Array,*))
    *   [trim(String str)](#UE.utils.trim(String))
    *   [listToMap(String str)](#UE.utils.listToMap(String))
    *   [listToMap(Array arr)](#UE.utils.listToMap(Array))
    *   [unhtml(String str)](#UE.utils.unhtml(String))
    *   [html(String str)](#UE.utils.html(String))
    *   [cssStyleToDomStyle(String cssName)](#UE.utils.cssStyleToDomStyle(String))
    *   [loadFile(DomDocument document, Object options)](#UE.utils.loadFile(DomDocument,Object))
    *   [loadFile(DomDocument document, Object options, Function fn)](#UE.utils.loadFile(DomDocument,Object,Function))
    *   [isEmptyObject(\* obj)](#UE.utils.isEmptyObject(*))
    *   [clone(Object source)](#UE.utils.clone(Object))
    *   [clone(Object source, Object target)](#UE.utils.clone(Object,Object))
    *   [transUnitToPx()](#UE.utils.transUnitToPx())
    *   [domReady(Function fn)](#UE.utils.domReady(Function))
    *   [isString(\* object)](#UE.utils.isString(*))
    *   [isArray(\* object)](#UE.utils.isArray(*))
    *   [isFunction(\* object)](#UE.utils.isFunction(*))
    *   [isNumber(\* object)](#UE.utils.isNumber(*))
    *   [isRegExp(\* object)](#UE.utils.isRegExp(*))
    *   [isObject(\* object)](#UE.utils.isObject(*))
    

按 ESC 可以关闭搜索框

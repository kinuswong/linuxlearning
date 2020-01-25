# ctags 使用
## 1. 查看支持的语言
`ctags --list-languages`
## 2. 查看语言和扩展名对应关系
`ctags --list-maps`
## 3. 查看ctags可以识别和记录的语法元素
`ctags --list-kinds`
`ctags --list-kinds=python`
## 4. 对当前目录下所有ctags支持的语言格式文件生成tags
`ctags -R *`
## 5. 对特定文件生成tags
`ctags "*.h"`
## 6. tags命令
### 6.1 跳转到指定的tag
tag tagname
### 6.2 快捷键 <kbd>Ctrl></kbd>+ <kbd>]</kbd>
取出当前光标下的word作为tag名字并进行跳转
### 6.3 tags 命令
列出曾经访问过的tag的列表
### 6.4 快捷键 <kbd>Ctrl</kbd>+<kbd>T</kbd>
跳转到前一次的tag处
###6.5 stag命令
分割当前窗口, 并且跳转到指定的tag
### 6.6 快捷键 <kbd>Ctrl</kbd>+<kbd>W</kbd>+<kbd>]</kbd> 
分割当前窗口, 并且跳转到光标下的tag
### 6.7 同名tag
如存在多个同名tag，tag命令会给出一个tag的列表，可以通过键入tag的序号来选择tag
也可以通过tselect来过滤tag，如：:tselect tagname
如果要在多个tags间移动, 可以使用如下命令:
```shell
:tfirst           go to first match
:[count]tprevious go to [count] previous match
:[count]tnext     go to [count] next match
:tlast            go to last match
[count]			  默认 1
```
### 7.其他
如果是多个tags文件，可以通过设置`tags`选项来引入更多的tags文件。例如: `:set tags=./tags, ./../tags, ./*/tags`
使用`tag`命令时，可以输入部分tag名，然后使用`Tab`键进行补全。

# 参考来源:
1. https://blog.csdn.net/foreverling/article/details/80329586

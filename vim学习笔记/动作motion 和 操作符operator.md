# 在普通模式NORMAL下
# 动作motion
>告诉vim要怎么做

## i(inner)和 a(around)区别

| 键位 | 描述 |
| - | - |
| i | 选中标签内部内容
| a | 选中标签及其内部内容
### js 相关

| 键位 | 描述 |
| - | - |
| ie |  整个文件entire
| iw / aw| 选中单词word
| i( / a( 或 ib / ab | 选中括号
| i{ / a{ 或 iB / aB | 选中大括号{
| i " / a" | 选中双引号"
| i' / a' | 选中单引号
| i` / a`  | 选中反引号` 
| i< / a< |  选中尖括号<
| i[  /  a[ |  选中中括号[

###  html 相关
| 键位 | 描述 |
| - | - |
| it / at | 选中标签tag
| is / as | 选中句子sentence
| ip / ap | 选中段落paragraph

# 操作符operator
> 告诉vim我们干什么，配合动作motion一起操作

| 键位 | 描述 |
| - | - |
| v | 选中内容
| d | delete删除
| c | change 修改（删除并且进入插入模式）
| y | yank 复制
| v | visual 选中并且进入VISUAL模式
| u | 撤销
| p | 粘贴

#example
die 删除整个文件内容
dd 删除一行
p 复制一行
u 撤销
cc 删除进入写入模式
yy 复制



# vim NORMAl模式下大小写转换
| 键位 | 描述 |
| - | - |
| ~ | 将光标下的字母改变大小写
| 3~ | 将光标位置开始的3个字母改变其大小写
| g~~ | 改变当前行字母的大小写
| gUU | 将当前行的字母改成大写
| guu | 将当前行的字母改成小写
| gUaw (gUiw) | 将光标下的单词改成大写
| guaw (guiw) | 将光标下的单词改成小写 

## Tips

###  vscode相关
| 键位 | 描述 |
| - | - |
| gd | 跳转到定义 go to define|
| gh | 悬浮函数签名 hover|
| gt/gT/3gt | 切换标签页 tabs |
| command + 0 | 跳转到侧边栏
| command + 1 | 跳转分屏
| space | 空格展开侧边栏目录或者打开文件
| l | 从侧边栏打开文件并进入
| gcc | 注释当前行
| gc2j | 注释当前行下两行
### vim-easymotion
> 文件内快速的高亮查询跳转

| 键位 | 描述 |
| - | - |
| space + sapce + s + {char} | 双击空格搜索search字符
| space + sapce + f + {char} | 双击空格向后查找find字符
....
### vim-surround
> 环绕相同字符的相关操作

| 键位 | 描述 |
| - | - |
| ds {existing char} | 删除环绕的相同字符 |
| cs {existing char} {desired char} | 改变环绕的相同字符
| ys {motion}{desired char} | 添加环绕的字符
| S {desired char} | 可视模式选中情况下
#example
-   `"test"` with cursor inside quotes type `cs"'` to end up with `'test'`
-   `"test"` with cursor inside quotes type `ds"` to end up with `test`
-   `"test"` with cursor inside quotes type `cs"t` and enter `123>` to end up with `<123>test</123`
- `ysi"`  `test` -> `“test”` 

### 多光标模式 Multi-cursor mode

| 键位 | 描述 |
| - | - |
| gb | 选中多个光标 |


Vim 备忘清单
===

[Vim](http://www.vim.org/) 8.2 快速参考备忘单的有用集合，可帮助您更快地学习 vim 编辑器。

入门
---------------

### 运动图
<!--rehype:wrap-class=row-span-2-->

```bash
▼/▶ 光标   ▽/▷ 目标
```

#### 左右动作

```bash
╭┈┈┈┈┈┈┈┈┈┈┈┈┈ |      
├┈┈┈┈┈┈┈┈┈┈┈┈┈ 0      $ ┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈┈╮
┆  ╭┈┈┈┈┈┈┈┈┈┈ ^      fe ┈┈┈┈┈┈┈┈╮       ┆
┆  ┆  ╭┈┈┈┈┈┈┈ Fo     te ┈┈┈┈┈┈┈╮┆       ┆
┆  ┆  ┆╭┈┈┈┈┈┈ To     30| ┈┈┈╮  ┆┆       ┆
┆  ┆  ┆┆ ╭┈┈┈┈ ge     w ┈┈┈╮ ┆  ┆┆       ┆
┆  ┆  ┆┆ ┆ ╭┈┈ b      e ┈╮ ┆ ┆  ┆┆       ┆
┆  ┆  ┆┆ ┆ ┆  ╭h      l╮ ┆ ┆ ┆  ┆┆       ┆
▽  ▽  ▽▽ ▽ ▽  ▽▼      ▼▽ ▽ ▽ ▽  ▽▽       ▽
   echo "A cheatsheet from quickReference"
```

#### 上下动作

```bash
                  - SCREEN 1 START
   ╭┈┬┈┈┈┈┈┈┈┈┈▷  #!/usr/bin/python
   ┆ ┆     ╭┈┈┈▷      
   ┆ ┆     ┆      print("Hello")
   ┆ ┆     { } ▶  print("Vim")
   ┆ ┆       ┆    print("!")
   ┆ ┆       └┈▷     
   ┆ ┆ ╭┈┈┈┬┈┈┈▷  print("Welcome")
G gg H M L k j ▶  print("to")
┆        ┆   └┈▷  print("Quick Reference")
┆        ┆        print("/vim")
┆        ┆     
┆        ╰┈┈┈┈┈▷ 
┆                 - SCREEN 1 END
╰┈┈┈┈┈┈┈┈┈┈┈┈┈┈▷  print("SCREEN 2")
```

### 动作

快捷方式 | 说明
:- | -
`<C-u>` _/_ `<C-d>`            | 上/下半页
`<C-b>` _/_ `<C-f>`            | 向上/向下翻页
<!--rehype:className=shortcuts-->

#### 文档

快捷方式 | 说明
:- | -
`:n` \| `nG`   | 转到第 `n` 行
`}` _/_ `{`    | 下一个/上一个空行
<!--rehype:className=shortcuts-->

#### 窗口

快捷方式 | 说明
:- | -
`H` _/_ `M` _/_ `L`     | 上/中/下屏幕
`zt` _/_ `zz` _/_  `zb` | 上/中/下这条线
<!--rehype:className=shortcuts-->

### 正常模式

快捷方式 | 说明
:- | -
`U`                   | 在一行上撤消更改
`J`                   | 加入下一行
`<C-r>` | 重做更改
<!--rehype:className=shortcuts-->

### 剪切和粘贴

快捷方式 | 说明
:- | -
`p` _/_ `P`      | 在之后/之前粘贴
`D`              | 删除到行尾 _(剪切)_
`"*p` \| `"+p`   | 从系统剪贴板粘贴
`"*y` \| `"+y`   | 粘贴到系统剪贴板
<!--rehype:className=shortcuts-->

### 重复

快捷方式 | 说明
:- | -
`.`      | 重复上一个命令
`;`      | 重复最新的 `f`、`t`、`F` 或 `T`
`,`      | 重复最新的`f`、`t`、`F`或`T`颠倒
`&`      | 重复最后一个`:s`
`@:`     | 重复命令行命令
<!--rehype:className=shortcuts-->

Vim 文本对象
------------

### 文本对象
<!--rehype:wrap-class=row-span-2-->

快捷方式 | 说明
:- | -
<yel>p</yel>                                         | 段落
<yel>w</yel>                                         | 单词
<yel>W</yel>                                         | WORD <br/> _(被空格包围)_
<yel>s</yel>                                         | 句子
<yel>[</yel> <yel>(</yel> <yel>{</yel> <yel>\<</yel> | []、() 或 {} 块
<yel>]</yel> <yel>)</yel> <yel>}</yel> <yel>\></yel> | []、() 或 {} 块
<yel>'</yel> <yel>"</yel> <yel>\`</yel>              | 带引号的字符串
<yel>b</yel>                                         | 一个块 [(
<yel>B</yel>                                         | [{中的一个块
<yel>t</yel>                                         | 一个 HTML 标签块

查看 `:help text-objects`

Vim 多个文件
-------------

### Buffers (缓冲器)

:- | -
:- | -
`:e file`  | 在新缓冲区中编辑文件
`:bn`      | 转到下一个缓冲区
`:bp`      | 转到上一个缓冲区
`:bd`      | 从缓冲区列表中删除文件
`:b 5`     | 打开缓冲区 #5
`:b file`  | 按文件转到缓冲区
`:ls`      | 列出所有打开的缓冲区
`:sp file` | 打开和拆分窗口
`:vs file` | 打开和垂直拆分窗口
`:hid`     | 隐藏此缓冲区
`:wn`      | 写入文件并移至下一个
`:tab ba`  | 将所有缓冲区编辑为选项卡

### 窗口

:- | -
:- | -
`<C-w>` `s`          | 拆分窗口
`<C-w>` `v`          | 垂直拆分窗口
`<C-w>` `w`          | 切换窗口
`<C-w>` `q`          | 退出一个窗口
`<C-w>` `T`          | 拆分成一个新标签
`<C-w>` `x`          | 用下一个交换当前
`<C-w>` `-`  _/_ `+` | 减少/增加高度
`<C-w>` `<`  _/_ `>` | 减少/增加宽度
`<C-w>` `\|`          | 最大宽度
`<C-w>` `=`          | 同样高和宽
`<C-w>` `h` _/_ `l`  | 转到左/右窗口
`<C-w>` `j` _/_ `k`  | 转到上/下窗口
<!--rehype:className=shortcuts-->

### 选项卡

快捷方式 | 说明
:- | -
`:tabe [file]` | <yel>E</yel>在新选项卡中编辑文件
`:tabf [file]` | 如果在新选项卡中存在则打开
`:tabc`        | <yel>C</yel>失去当前选项卡
`:tabo`        | 关闭<yel>o</yel>其他选项卡
`:tabs`        | 列出所有<yel>标签</yel>
`:tabr`        | 转到第一个<yel>r</yel>标签
`:tabl`        | 转到 <yel>l</yel>ast 选项卡
`:tabm 0`      | <yel>我</yel>转到位置 `0`
`:tabn`        | 转到 <yel>n</yel>ext 选项卡
`:tabp`        | 转到<yel>p</yel>上一个标签

#### 正常模式

快捷方式 | 说明
:- | -
`gt`     | 转到 <yel>n</yel>ext 选项卡
`gT`     | 转到<yel>p</yel>上一个标签
`2gt`    | 转到标签编号 `2`

Vim 搜索和替换
------------------

### 搜索

:- | -
:- | -
`/foo`   | 向前搜索
`/foo\c` | 向前搜索 _(不区分大小写)_
`?foo`   | 向后搜索
`/\v\d+` | 使用 [regex](./regex.md) 搜索
`n`      | 下一个匹配的搜索模式
`N`      | 上一个匹配的搜索
`*`      | 向前搜索当前单词
`#`      | 向后搜索当前单词

### 更换行

```vim
:[range]s/{pattern}/{str}/[flags]
```

---

:- | -
:- | -
`:s/old/new`      | 先更换
`:s/old/new/g`    | 全部替换
`:s/\vold/new/g`  | 全部替换为 [regex](./regex.md)
`:s/old/new/gc`   | 全部替换_(确认)_
`:s/old/new/i`    | 先忽略大小写替换
`:2,6s/old/new/g` | 在 `2`-`6` 行之间替换

### 替换文件

```vim
:%s/{pattern}/{str}/[flags]
```

---

:- | -
:- | -
`:%s/old/new`     | 先更换
`:%s/old/new/g`   | 全部替换
`:%s/old/new/gc`  | 全部替换 _(确认)_
`:%s/old/new/gi`  | 全部替换 _(忽略大小写)_
`:%s/\vold/new/g` | 全部替换为 [regex](./regex.md)

### 范围
<!--rehype:wrap-class=row-span-2-->

:- | -
:- | -
`%`     | 整个文件
`’<,’>` | 当前选择
`5`     | 第 `5` 行
`5,10`  | 第 `5` 行到第 `10` 行
`$`     | 最后一行
`2,$`   | 第 `2` 行到最后
`.`     | 当前行
`,3`    | 接下来的 `3` 行
`-3,`   | 转发 `3` 行

### 全局命令
<!--rehype:wrap-class=row-span-2-->

```vim
:[range]g/{pattern}/[command]
```

---

:- | -
:- | -
`:g/foo/d`   | 删除包含 `foo` 的行
`:g!/foo/d`  | 删除不包含 `foo` 的行
`:g/^\s*$/d` | 删除所有空行
`:g/foo/t$`  | 将包含 `foo` 的行复制到 EOF
`:g/foo/m$`  | 将包含 `foo` 的行移动到 EOF
`:g/^/m0`    | 反转文件
`:g/^/t.`    | 复制每一行

### Inverse(逆) :g

```vim
:[range]v/{pattern}/[command]
```

---

:- | -
:- | -
`:v/foo/d` | 删除不包含`foo`的行 <br/> _(还有`:g!/foo/d`)_

### Flags(标志)

:- | -
:- | -
`g` | 替换所有出现
`i` | 忽略大小写
`I` | 不要忽略大小写
`c` | 确认每个替换

### 替换表达式（魔术）

:- | -
:- | -
`&` _\|_ `\0` | 替换为整个匹配的
`\1`...`\9`   | 替换为 0-9 组
`\u`          | 大写下一个字母
`\U`          | 后面的大写字符
`\l`          | 小写下一个字母
`\L`          | 后面的字符小写
`\e`          | `\u`、`\U`、`\l` 和 `\L` 的结尾
`\E`          | `\u`、`\U`、`\l` 和 `\L` 的结尾

### 例子
<!--rehype:wrap-class=col-span-2-->

```shell
:s/a\|b/xxx\0xxx/g               # 将 "a b"      修改为 "xxxaxxx xxxbxxx"
:s/test/\U& file/                # 将 "test"     修改为 "TEST FILE"
:s/\(test\)/\U\1\e file/         # 将 "test"     修改为 "TEST file"
:s/\v([abc])([efg])/\2\1/g       # 将 "af fa bg" 修改为 "fa fa gb"
:s/\v\w+/\u\0/g                  # 将 "bla bla"  修改为 "Bla Bla"
:s/\v([ab])|([cd])/\1x/g         # 将 "a b c d"  修改为 "ax bx x x"
:%s/.*/\L&/                      # 将 "HTML"     修改为 "html"
:s/\v<(.)(\w*)/\u\1\L\2/g        # 将单词的每个首字母大写
:%s/^\(.*\)\n\1/\1/              # 删除重复行
:%s/<\/\=\(\w\+\)\>/\U&/g        # 将 HTML 标记转换为大写
:g/^pattern/s/$/mytext           # 查找文本并将其附加到末尾
:g/pattern/norm! @i              # 在匹配行上运行宏
/^\(.*\)\(\r\?\n\1\)\+$          # 查看重复行
/\v^(.*)(\r?\n\1)+$              # 查看重复行（非常神奇）
:v/./,/./-j                      # 将空行压缩成空行
:g/<p1>/,/<p2>/d                 # 从 <p1> 到 <p2> 包含删除
```

Vimdiff
-------

### 用法
<!--rehype:style=background:#d7a100;-->

```shell script
$ vimdiff file1 file2 [file3]
$ vim -d file1 file2 [file3]
```

### 编辑
<!--rehype:wrap-class=row-span-2-->

```
:[range]diffget [bufspec]
:[range]diffput [bufspec]
```

---

快捷方式 | 说明
:- | -
`do` _/_ `:diffget` | 获取（get）差异
`dp` _/_ `:diffput` | 放差价
`:dif`              | 重新扫描差异
`:diffo`            | 关闭差异模式
`:1,$+1diffget`     | 获取所有差异
`ZQ`                | 不做改动就退出
<!--rehype:className=shortcuts-->

请参阅：[范围](#范围)

### 折叠
<!--rehype:wrap-class=row-span-2-->

快捷方式 | 说明
:- | -
`zo` _/_ `zO` | 打开
`zc` _/_ `zC` | 关
`za` _/_ `zA` | 切换
`zv`          | 这条线的打开折叠
`zM`          | 关闭所有
`zR`          | 打开所有
`zm`          | 折叠更多 _(折叠级别 += 1)_
`zr`          | 少折叠 _(折叠级别 -= 1)_
`zx`          | 更新折叠
<!--rehype:className=shortcuts-->

### 跳跃

快捷方式 | 说明
:- | -
`]c`     | 下一个区别
`[c`     | 以前的区别
<!--rehype:className=shortcuts-->

各种各样的
-------------

### 跳跃

快捷方式 | 说明
:- | -
| `<C-o>`  | 返回上一个
| `<C-i>`  | 向前
<!--rehype:className=shortcuts-->

### 其他命令行
<!--rehype:wrap-class=row-span-2-->

:- | -
:- | -
`:h`           | 帮助打开帮助视图
`:edit!`       | 重新加载当前文件
`:2,8m0`       | 将行 `2`-`8` 移动到 `0`
`:noh`         | 清除搜索亮点
`:sort`        | 排序行

### 导航

快捷方式 | 说明
:- | -
`%`                      | 最近/匹配的`{[()]}`
`[(` _\|_ `[{`           | 上一个 `(` 或 `{`
`])` _\|_ `]{`           | 下一个`)`或`}`
`[m`                     | 上一个方法开始
`[M`                     | 上一个方法结束
<!--rehype:className=shortcuts-->

### 选项卡
<!--rehype:wrap-class=row-span-2 col-span-2-->

快捷方式 | 说明
:- | -
`:tag Classname`     | 跳转到 Classname 的第一个定义
`<C-]>`              | 跳转到定义
`g]`                 | 查看所有定义
`<C-t>`              | 回到最后一个标签
`<C-o> <C-i>`        | 后退前进
`:tselect Classname` | 查找类名的定义
`:tjump Classname`   | 查找类名的定义 _(自动选择第一个)_
<!--rehype:className=shortcuts-->

### 标记
<!--rehype:wrap-class=row-span-4 col-span-2-->

快捷方式 | 说明
:- | -
<code>\`^</code>   | 插入模式下光标的最后位置
<code>\`.</code>   | 当前缓冲区的最后更改
<code>\`"</code>   | 最后退出的当前缓冲区
<code>\`0</code>   | 在上次编辑的文件中
<code>''</code>    | 返回当前缓冲区中跳出的行
<code>\`\`</code>  | 返回当前缓冲区中跳转的位置
<code>\`[</code>   | 到先前更改或拉出的文本的开头
<code>\`]</code>   | 到之前更改或拉出的文本的结尾
<code>\`&lt;</code>| 到最后一个可视化选择的开始
<code>\`&gt;</code>| 到最后一个可视化选择的结尾
`ma`               | 将此光标位置标记为`a`
<code>\`a</code>   | 跳转到光标位置`a`
`'a`               | 跳转到位置为 `a` 的行首
<code>d'a</code>   | 从当前行删除到标记 `a` 的行
<code>d\`a</code>  | 从当前位置删除到标记 `a` 的位置
<code>c'a</code>   | 将文本从当前行更改为 `a` 行
<code>y\`a</code>  | 将文本从当前位置拉到 `a` 的位置
`:marks`           | 列出所有当前标记
`:delm a`          | 删除标记`a`
`:delm a-d`        | 删除标记`a`、`b`、`c`、`d`
`:delm abc`        | 删除标记`a`、`b`、`c`
<!--rehype:className=shortcuts-->

### 计算器

快捷方式 | 说明
:- | -
| `<C-r>` `=` 7*7  | 显示结果|
| `<C-r>` `=` 10/2 | 显示结果|
<!--rehype:className=shortcuts-->

在 INSERT 模式下执行此操作

### Shell

:- | -
:- | -
`:!<shell>`  | 解释 Shell 命令
`:r!<shell>` | 读入shell的输出
`:r!date`    | 插入日期
`:!!date`    | 用日期替换当前行

### 命令行

快捷方式 | 说明
:- | -
`<C-r><C-w>` | 将当前单词插入命令行
`<C-r>"`     | 从 `注册` 粘贴
`<C-x><C-f>` | 在插入模式下自动完成路径
<!--rehype:className=shortcuts-->

### 技巧

删除重复行

```shell
:sort | %!uniq -u
```

对文件中的行进行编号

```shell
:%!cat -n
```

将整个文档复制到剪贴板

```shell
:%w !pbcopy            # Mac OS X
:%w !xclip -i -sel c   # GNU/Linux
:%w !xsel -i -b        # GNU/Linux
```

理解 Vim
---

### 动词理解

```shell
d  # 表示删除delete
r  # 表示替换replace
c  # 表示修改change
y  # 表示复制yank
v  # 表示选取visual select
```

动词代表了我们打算对文本进行什么样的操作

### 名词理解

```shell
w  # 表示一个单词word
s  # 表示一个句子sentence
p  # 表示一个段落paragraph
t  # 表示一个 HTML 标签tag
```

名词代表了我们即将处理的文本。引号或者各种括号所包含的文本称作一个文本块。

### 介词理解

```shell
i  # 表示在...之内 inside
a  # 表示环绕... around
t  # 表示到...位置前 to
f  # 表示到...位置上 forward
```

介词界定了待编辑文本的范围或者位置。

### 数词理解
<!--rehype:wrap-class=col-span-2-->

数词指定了待编辑文本对象的数量，从这个角度而言，数词也可以看作是一种介词。引入数词之后，文本编辑命令的语法就升级成了下面这样：

```shell
动词 介词/数词 名词
```

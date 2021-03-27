## From GUI to CLI

## 软件环境

* Virtualbox
* Ubuntu 20.04.4 Live-Server 64bit
* 在 [asciinema](https://asciinema.org) 注册一个账号，并在本地安装配置好asciinema

## 安装asciinema

按照官网安装指南，在终端中输入
```
sudo apt-add-repository ppa:zanchey/asciinema
sudo apt-get update
sudo apt-get install asciinema
```
## vimtutor操作录像

### Lesson 1
[![asciicast](https://asciinema.org/a/Xh0JfxWT08G4aPs8b48MgoqG6.svg)](https://asciinema.org/a/Xh0JfxWT08G4aPs8b48MgoqG6)

### Lesson 2
[![asciicast](https://asciinema.org/a/N3ifnx1AzAOKp4BbMtd52Ho0U.svg)](https://asciinema.org/a/N3ifnx1AzAOKp4BbMtd52Ho0U)
### Lesson 3
[![asciicast](https://asciinema.org/a/QdvCZht5dk1oEEa9sBzZPNKuP.svg)](https://asciinema.org/a/QdvCZht5dk1oEEa9sBzZPNKuP)
### Lesson 4
[![asciicast](https://asciinema.org/a/1F6t6g8Z4TF44DVmrGkq7hpLb.svg)](https://asciinema.org/a/1F6t6g8Z4TF44DVmrGkq7hpLb)
### Lesson 5
[![asciicast](https://asciinema.org/a/1MoAgBY8VLOseWZaeqj9mNULA.svg)](https://asciinema.org/a/1MoAgBY8VLOseWZaeqj9mNULA)
### Lesson 6
[![asciicast](https://asciinema.org/a/DTsykhRVW3xXqurKuJLb7Ew9G.svg)](https://asciinema.org/a/DTsykhRVW3xXqurKuJLb7Ew9G)
### Lesson 7
[![asciicast](https://asciinema.org/a/cOq5HRQcrNHimHDnmzesj1zRy.svg)](https://asciinema.org/a/cOq5HRQcrNHimHDnmzesj1zRy)


## vimtutor完成后的自查清单

#### 你了解vim有哪几种工作模式
- Normal
- Insert
- Visual

#### Normal模式下，从当前行开始，一次向下移动光标10行的操作方法？如何快速移动到文件开始行和结束行？如何快速跳转到文件中的第N行？
- 一次向下移动光标10行：`10j`
- 快速移动到文件开始行和结束行：`gg`，结束行：`G`
- 快速跳转到文件中的第N行：`Ngg`、`NG`

#### Normal模式下，如何删除单个字符、单个单词、从当前光标位置一直删除到行尾、单行、当前行开始向下数N行？
- 删除单个字符：`x`
- 删除单个单词：`dw`
- 删除到行尾：`d$`
- 删除单行：`dd`
- 删除下N行：`Ndd`

#### 如何在vim中快速插入N个空行？如何在vim中快速输入80个-？
- 插入N个空行：`N o ESC` 
- 快速插入80个-：`80 i - ESC`

#### 如何撤销最近一次编辑操作？如何重做最近一次被撤销的操作？
- 撤销最近一次编辑操作：`u`
- 重做最近一次被撤销的操作：`ctrl+R`

#### vim中如何实现剪切粘贴单个字符？单个单词？单行？如何实现相似的复制粘贴操作呢？
- 剪切单个字符：`x`
- 剪切单个单词：`dw`
- 剪切单行：`dd`
- 复制单个字符：`y`
- 复制单个单词：`b yw`
- 复制单行：`yy`
- 粘贴操作都是：`P` `p`
- 也可以在Visual模式下选择好范围后 `d` 剪切，`y` 复制，`p` 粘贴

#### 为了编辑一段文本你能想到哪几种操作方式（按键序列）
- 光标移动：`h,j,k,l,w,b,Ctrl+b,Ctrl+f,gg,G`
- 编辑操作（插入或替换）：`i,a,o,`
- 删除操作：`x,dd,dw,`
- 查询操作：`/[xx]` xx是查找内容
- 退出：`:wq` or `:q` or `:q!`

#### 查看当前正在编辑的文件名的方法？查看当前光标所在行的行号的方法？
- `ctrl-g`

#### 在文件中进行关键词搜索你会哪些方法？如何设置忽略大小写的情况下进行匹配搜索？如何将匹配的搜索结果进行高亮显示？如何对匹配到的关键词进行批量替换？
- 关键词搜索：`/pattern`
- 设置忽略大小写：`:set ignorecase` `:set ic`
- 高亮显示搜索结果：`:set hlsearch` `:set hls`
- 关键词进行批量替换：`:%s/old/new/g ` 

#### 在文件中最近编辑过的位置来回快速跳转的方法？
- `ctrl-o`
- `ctrl-i`

#### 如何把光标定位到各种括号的匹配项？例如：找到\(, \[, or \{对应匹配的),], or }
- 光标移至需要匹配的括号上，`%`

#### 在不退出vim的情况下执行一个外部程序的方法？
- `:!command`，command为外部程序名称

#### 如何使用vim的内置帮助系统来查询一个内置默认快捷键的使用方法？如何在两个不同的分屏窗口中移动光标？
- 查询一个内置默认快捷键 `:help xx`，xx为名称
- 在两个不同的分屏窗口中移动光标`ctrl-w` 
---
sidebar_position: 2
---

# Vim 基本操作

## 概念

- **操作模式**

  分为命令模式和插入模式，默认在命令模式，按 `i` 进入插入模式；在插入模式时，按 `ESC` 退出插入模式，进入命令模式。

:::info

这样设计因此持按几下 `ESC` 可以发出“嘟”的一声，表示已在命令模式。

:::


- **文档末尾的**

  Vim 用波浪号 `~` 表示文档末尾，文档末尾有波浪号开头的行，代表空行。

## Vim 操作

:::tip joke

我在电脑上安装了 Linux，但我不知道怎么使用这个 6 号编辑器。

:::

### 1. 打开文件（加载文件到缓冲区）

```shell
vim [filename]
```
在现代系统中，vi 常常是 Vim 的链接。 
```shell
vi [filename]
```

### 2. 保存文件（缓冲区写入文件）

在命令模式中，输入 `:w` 并回车。

### 3. 关闭文件

在命令模式中，输入 `:q` 并回车。

如果没有保存，则输入 `:wq` 并回车。

另一个更现代的命令是 `ZZ` （Z为大写字母）

舍弃编辑的内容重新载入原始文件 `:e!`

舍弃编辑的内容并退出 `:q!`

### 4. 移动

- 前后移动光标：在命令模式下，前 `h`，后 `l`
- 上下移动光标：在命令模式下，下 `j`，上 `k`

掌握这四个键后，手指可以不离开键盘中心区域移动光标。

上下移动，还可使用 `BACKSPACE` 和 `ENTER`，或者与 Emacs 相似的 `CTRL-P` 和 `CTRL-N`。 

:::info

这样设计是因为 vi 的作者 Bill Joy 的键盘没有方向键，而使用这几个键能兼容更多键盘。

:::


### 5. 编辑

插入文本：进入插入模式，再输入文本。

删除文本：在插入模式，按 `Del` 或 `Backspace`；在命令模式有好几个命令，留后。

:::info

理论上，上述五个属于 Vim 新手逃生操作，理解并用熟后，就可以开始文本编辑了。

:::

# Bash 的基本语法

## echo

```shell
# 输出单行文本
echo hello world

# 输出多行文本
echo "<html>
	<HEAD>
		<TITLE>Page Title</TITLE>
	</HEAD>
	<body>
		page body
	</body>
</html>"

# -n 取消末尾的回车符
echo -n hello world
echo a;echo b
echo -n a;echo b

# -e 解释引号里面的特殊字符串
echo "Hello \nWorld"
echo -e "Hello \nWorld"
echo -e 'Hello \nWorld'
```

## 命令格式

```shell
command [arg1 ...[argN]]
ls -l

# 短形式，便于手动输入
ls -r
# 长形式，一般用于脚本中，可读性更好，利于解释自身含义
ls --revese

# 换行
echo bar foo
echo bar \
foo
```

## 空格

bash 使用空格（Tab 键）区分不同的参数

空格会默认为两个不同的参数

```shell
# bar 和 foo 是两个不同的参数
echo bar foo

# 如果参数间有多余的空格，会被忽略
echo this is    a     test
```

## 命令组合符

### 分号

> 使用 ; 时，第二个命令总是接着第一个命令执行，不管第一个命令执行**成功**或**失败**

分号(;)是命令的结束符，使得一行可以放置多个命令，上一个命令执行结束后，再执行第二个命令。

> 和 mysql 相同，sql 语句后面必须有 ;

```shell
clear; ls
```

### &&

> 第一个命令运行**成功**，则继续运行第二个命令

```shell
clear && ls
c && ls
```

### ||

> 第一个命令运行**失败**，则继续运行第二个命令

```shell
clear || ls
c || ls
```

## type 命令

判断命令来源。内部命令 或 外部程序。

```shell
type echo
# echo is a shell builtin

type ls
ls is hashed (/bin/ls)

type webstorm
# webstorm is /usr/local/bin/webstorm
```

| 选项 | 定义 | 示例 |
|:---|:---|:---|
| -a | 查看一个命令的所有定义 | type -a echo |
| -t | 返回命令的类型 | 别名（alias）， 关键词（keyword）， 函数（function），内置命令（builtin），文件（file）|

```shell
# 查看一个命令的所有定义
type -a echo
# echo is a shell builtin
# echo is /bin/echo

type -t webstorm # file
type -t echo # builtin
type -t if # keyword
```

## 快捷键


| 选项 | 定义 |
|:---|:---|
| Ctrl + L | 清除屏幕并将当前行移动到顶部 |
| Ctrl + C | 终止当前正在执行的命令 |
| Shift + PageUp | 向上滚动 |
| Shift + PageDown | 向下滚动 |
| Ctrl + U | 从光标位置移动到行首 |
| Ctrl + K | 从光标位置移动到行尾 |
| Ctrl + W | 删除光标位置前一个单词 |
| Ctrl + D | 关闭 shell 会话 |
| 👆， 👇 | 浏览执行的历史记录 |
| Tab | 命令自动补全 |
| Tab 双击 | 显示所有选项 |


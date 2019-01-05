# 1.Python提示工具包

​	

```
prompt_toolkit是一个用于在Python中构建功能强大的交互式命令行和终端应用程序的库
REPL(交互式解释器)
扮演了readline的角色
	纯Python。运行从2.6到3.4的所有Python版本

	在Linux，OS X，OpenBSD和Windows系统上运行

	轻量级
```

```
prompt:
cmd = prompt(prompt_str,history=FileHistory('history.txt'),auto_suggest = AutoSuggestFromHistory(),completer=ShellCompleter,)
prompt_str
prompt_str为输出在命令行中的界定符（提示符）
返回获取到的字符串

       
```

```
FileHistory
history=FileHistory('history.txt')
添加持久的历史记录
可以使用向上/向下箭头浏览历史记录
使用Ctrl + R搜索历史
```

```
AutoSuggestFromHistory
auto_suggest = AutoSuggestFromHistory()
自动联想
```

```
ShellCompleter = WordCompleter(['ls','cd','pwd','ps'],ignore_case=True)
completer=ShellCompleter,
通过tab键自动补全，在用户输入过程中弹出参考项。
```

```
自动补全字典
WordCompleter(['ls','cd','pwd','ps'],ignore_case=True)
忽略大小写
ps 列出进程快照
```

# 2.shlex

```
shlex.split(s, comments = False, posix = True)
使用类似shell的语法拆分字符串s,返回字符串列表
如果comments是False （默认值），则将禁用对给定字符串中的注释的解析（将实例的commenters属性 设置shlex为空字符串）。默认情况下，此函数在POSIX模式下运行，但如果posix参数为false ，则使用非POSIX模式。
由于split()函数实例化一个shlex 实例，因此传递None给s将读取要从标准输入中拆分的字符串。
```

# 3.OS

```
os.getenv('PATH')
#要获取某个环境变量的值，可以调用os.getenv()函数
os.getcwd()用户返回当前工作目录
os.path.basename(path)返回文件名
os.path.expanduser(path)把path中包含的"~"和"~user"转换成用户目录
os.chdir() 方法用于改变当前工作目录到指定的路径。
```

# 4.getpass

```
getpass.getuser()
Return the “login name” of the user.
```

# 5.socket

```
socket.gethostname()
获取当前主机的主机名
```

# 6.platform

```
platform.system()获取操作系统类型

```

# 7.signal

```
signal.SIGINT   # 终止进程（ctrl+c）;
signal.SIGTSTP  # 暂停进程（ctrl+z）;
signal.signal(signalnum, handler)：设置信号处理的函数。
signalnum为某个信号，handler为该信号的处理函数。进程可以无视信号，可以采取默认操作，还可以自定义操作。当handler为signal.SIG_IGN时，信号被无视(ignore)。当handler为singal.SIG_DFL，进程采取默认操作(default)。当handler为一个函数名时，进程采取函数中定义的操作。
```

# 8.subprocess

```
用subprocess 模块来运行系统命令.subprocess模块允许我们创建子进程,连接他们的输入/输出/错误管道，还有获得返回值。
subprocess.call()
执行由参数提供的命令.
subprocess 模块中基本的进程创建和管理由Popen 类来处理.
subprocess.popen是用来替代os.popen的.
```

# 9.SYS

```
sys.exc_info()
此函数返回三个值的元组，这些值提供有关当前正在处理的异常的信息。返回的信息特定于当前线程和当前堆栈帧。如果当前堆栈帧未处理异常，则从调用堆栈帧或其调用者获取信息，依此类推，直到找到正在处理异常的堆栈帧。这里，“处理异常”被定义为“执行except子句。”对于任何堆栈帧，只能访问有关当前处理的异常的信息。
如果堆栈中的任何位置都没有处理异常，None则返回包含三个值的元组。否则，返回的值是 。它们的含义是：type获取正在处理的异常的类型（子类）; value获取异常实例（异常类型的实例）; traceback获取一个回溯对象（参见参考手册），该对象在最初发生异常的位置封装调用堆栈。(type, value, traceback)BaseException
sys.stdin
sys.stdout
sys.stderr
解释器用于标准输入，输出和错误的文件对象：

stdin用于所有交互式输入（包括调用 input()）;
stdout用于输出print()和表达式 语句以及提示input();
解释器自己的提示及其错误消息转到stderr。
```


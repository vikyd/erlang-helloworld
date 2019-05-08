# Erlang Hello World
Erlang 最简单的输出字符串例子。

# 运行方式01：编译、执行
### 编译为 `.beam` 文件：
> [beam](https://blog.stenmans.org/theBeamBook/#CH-BEAM) 文件是 erlang 编译器生成的文件格式，可以直接加载到 erlang vm 中运行的文件格式，大致可当做 Java 的 jar

```sh
erlc hello.erl
```

上述命令会得到一个文件：`hello.beam`

### 执行 `hello.beam`
```sh
erl -noshell -s hello start -s init stop`
```

将输出：
```
hello world
```

### 解释
`erl -noshell -s hello start -s init stop` 的解释：
- `-noshell`：常用，不显示 erl shell。一般都是执行一系列的 -eval，-s，-ran，然后init:stop().
- `-s hello start`：hello 模块中的 start 函数
- `-s init stop`：init 模块中的 stop 函数
  > 不执行 stop，程序不会退出来


# 运行方式02：erlang shell 中调用函数
无需编译成 `.beam` 文件

> 英文句号 `.` 是 Erlang 的函数分隔符，下面在 erlang shell 中的操作都应以 `.` 结尾

### 步骤

- 进入 erlang shell
```sh
erl
```
- 导入 `hello` 模块
  > `c` 估计是 `compile` 的缩写，表示编译并导入模块
```
c(hello).
```
- 执行 `start` 函数
```
hello:start().
```
- 此时应已输出：
```
hello world
```



# 参考
- [erlang shell](http://erlang.org/doc/man/shell.html)

- [erl命令和参数](https://youthyblog.com/2015/07/22/erl%E5%91%BD%E4%BB%A4%E5%92%8C%E5%8F%82%E6%95%B0/)


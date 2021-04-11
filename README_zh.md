# 单词统计器

A description of this package.

## Run

```
➜  swift-word-counter git:(main) swift run
Fetching https://github.com/apple/swift-argument-parser
Cloning https://github.com/apple/swift-argument-parser
Resolving https://github.com/apple/swift-argument-parser at 0.4.1
[39/39] Linking count       ①
Error: Missing expected argument '--input <input>'

OVERVIEW: Word counter.

USAGE: count --input <input> --output <output> [--verbose]

OPTIONS:
  -i, --input <input>     A file to read. 
  -o, --output <output>   A file to save word counts to. 
  -v, --verbose           Print status updates while counting. 
  -h, --help              Show help information.
```

- ①

```
products: [
    .executable(name: "count", targets: ["swift-word-counter"])
],
```
## Using Custom Names

### 标识 放在第一位

```
➜  swift-word-counter git:(main) ✗ swift run count -v -i readme.md -o readme.counts
[3/3] Linking count
Counting words in 'readme.md' and writing the result into 'readme.counts'.
Found 66 words.
➜  swift-word-counter git:(main) ✗
```

### 标识放在最后一位

```
➜  swift-word-counter git:(main) ✗ swift run count --input readme.md --output readme.counts -v
Counting words in 'readme.md' and writing the result into 'readme.counts'.
Found 70 words.
➜  swift-word-counter git:(main) ✗
```

### 改变输入顺序
```
➜  swift-word-counter git:(main) ✗ swift run count -o readme.counts -i readme.md --verbose
Counting words in 'readme.md' and writing the result into 'readme.counts'.
Found 74 words.
➜  swift-word-counter git:(main) ✗ 
````
# 参数声明, 选项, 和 标识

Use the `@Argument`, `@Option` and `@Flag` property wrappers to declare the command-line interface for your command.

When creating commands, you can define three primary kinds of command-line inputs:

### 参数声明  `Arguments`
- *Arguments* are values given by a user and are read in order from first to last. For example, this command is called with three file names as arguments:

- *参数*是用户给定的值，并按从头到尾的顺序读取。例如，以三个文件名作为参数调用此命令：

  ```
  % example file1.swift file2.swift file3.swift
  ```

- *Options* are named key-value pairs. Keys start with one or two dashes (`-` or `--`), and a user can separate the key and value with an equal sign (`=`) or a space. This command is called with two options:

- *选项*称为键值对。键以一个或两个破折号（`-`或`--`）开头，并且用户可以用等号（`=`）或空格分隔键和值。可以通过两个选项调用此命令：

  ```
  % example --count=5 --index 2
  ```

- *Flags* are like options, but without a paired value. Instead, their presence indicates a particular value (usually `true`). This command is called with two flags:

- *标志*就像选项，但是没有成对的值。相反，它们的存在指示特定值（通常为`true`）。使用两个标志调用此命令：

  ```
  % example --verbose --strip-whitespace
  ```













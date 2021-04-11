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

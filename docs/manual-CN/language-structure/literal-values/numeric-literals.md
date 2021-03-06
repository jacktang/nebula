# 数值字面值

数值字面值包括整数字面值和浮点字面值。

整数为64位，并且可以用 `+` 和 `-` 来表明正负性。它们和 C 语言中的 `int64_t` 是一致的。

浮点数和 C 语言中的 `double` 是一致的。

以下为几个例子：

```
1, -5, +10000100000
-2.3, +1.00000000000
```

注意整数的最大值为 `9223372036854775807`。输入任何大于此最大值的整数为语法错误。整数的最小值`-9223372036854775808` 同理。
 
然而浮点数没有上限和下限。

科学计数法会在下个 release 版本中支持。
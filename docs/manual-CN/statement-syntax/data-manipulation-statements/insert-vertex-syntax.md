```
INSERT VERTEX tag_name[, tag_name] (prop_name_list[, prop_name_list])
     {VALUES | VALUE} vid: (prop_value_list[, prop_value_list])

prop_name_list:
  [prop_name [, prop_name] ...]

prop_value_list:
  [prop_value [, prop_value] ...]
```

INSERT VERTEX可向Nebula插入节点。
* `tag_name`表示标签（节点类型），在进行`INSERT VERTEX`操作前需创建好。
* `prop_name_list`为指定标签的属性列表。
* `prop_value_list`须根据<prop_name_list>列出属性性，如无匹配类型，则返回错误。

>目前版本尚不支持默认属性值。
### 示例

```
# CREATE TAG t1()                   -- 创建空属性标签t1
INSERT VERTEX t1 () VALUES 10:()    -- 插入空属性点100
```

```
# CREATE TAG t2 (name string, age int)                -- 创建有两种属性的标签t2
INSERT VERTEX t2 (name, age) VALUES 11:("n1", 12)     -- 插入有两种属性的点11
INSERT VERTEX t2 (name, age) VALUES 12:("n1", "a13")  -- 错误操作，"a13"不是int类型
```

```
# CREATE TAG t1(i1 int)
# CREATE TAG t2(s2 string)
INSERT VERTEX  t1 (i1), t2(s2) VALUES 21: (321, "hello")   -- 插入有两个标签的点21
```

同一节点可被多次插入或写入，读取时以最后一次插入为准。

```
-- 为点11多次插入新值
INSERT VERTEX t2 (name, age) VALUES 11:("n2", 13)
INSERT VERTEX t2 (name, age) VALUES 11:("n3", 14)
INSERT VERTEX t2 (name, age) VALUES 11:("n4", 15)  -- 读取最后插入的值
```

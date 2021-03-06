#### 数据库索引

- 数据库索引就是一个能加快海量数据查询的一项技术
> 比如字典里面的目录

- 联合索引(包含多个字段的索引)
> 比如字典里面的先查部首再根据笔画来查

- 最左前缀匹配
> 对于一个联合索引，如果有一个SQL查询语句需要执行，则只有从索引最左边的第一个字段开始到SQL语句查询条件中不包含的字段（不含）或范围条件字段（含）为止的部分才会使用索引进行加速。

- 聚集索引(数据会根据索引中的顺序进行排列和组织的),比如主键索引
> 比如像拼音目录这样的索引

- 数据库索引设计
  1.  **整理查询条件**
        - 在where子句、join连接条件中使用的字段
  2.  **分析字段的可选择性**
        - 会把可选择性高的字段放到前面，可选择性低的字段放在后面,可选择性是指字段的值的区分度
  3.  **合并查询条件**
        - 最左匹配原则来合并查询条件，尽可能让不同的查询条件使用同一个索引
  4.  **考虑是否需要使用全覆盖索引**
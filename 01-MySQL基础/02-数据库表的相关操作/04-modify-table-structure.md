# 修改表结构

使用`ALTER TABLE`语句修改表结构如下所示。

## 添加字段：

```sql
ALTER TABLE 表名称
ADD 列1 数据类型 [约束] [COMMENT '注释'],
ADD 列2 数据类型 [约束] [COMMENT '注释'],
...;
```

## 修改字段类型和约束：

```sql
ALTER TABLE 表名称
MODIFY 列1 数据类型 [约束],
MODIFY 列2 数据类型 [约束],
...;
```

## 修改字段名称：

```sql
ALTER TABLE 表名称
CHANGE 旧列名 新列名 数据类型 [约束] [COMMENT '注释'],
CHANGE 旧列名2 新列名2 数据类型 [约束] [COMMENT '注释'],
...;
```

## 删除字段：

```sql
ALTER TABLE 表名称
DROP 列1,
DROP 列2,
...;
```

## 修改表名：

```sql
ALTER TABLE 旧表名
RENAME TO 新表名;
```

请注意，这里使用的是方括号 `[ ]` 表示可选项，可以根据需要选择是否添加。另外，每个语句结束都有一个分号 `;`。

---

以下是一些具体的例子，以说明如何使用上述的 `SQL` 语句进行表结构的修改。

假设我们有一个表格 `students`，初始结构如下：

```sql
CREATE TABLE students (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT
);
```

### 添加字段：

```sql
-- 添加一个新的列 'grade'，数据类型为 INT
ALTER TABLE students
ADD grade INT COMMENT '学年';
```

### 修改字段类型和约束：

```sql
-- 将 'age' 列的数据类型改为 SMALLINT，并添加 NOT NULL 约束
ALTER TABLE students
MODIFY age SMALLINT NOT NULL;
```

### 修改字段名称：

```sql
-- 将 'name' 列改名为 'full_name'，同时将数据类型改为 VARCHAR(100)
ALTER TABLE students
CHANGE name full_name VARCHAR(100) COMMENT '学生姓名';
```

### 删除字段：

```sql
-- 删除 'grade' 列
ALTER TABLE students
DROP grade;
```

### 修改表名：

```sql
-- 将表名 'students' 改为 'class_members'
ALTER TABLE students
RENAME TO class_members;
```
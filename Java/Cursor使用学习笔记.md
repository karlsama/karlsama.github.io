# Cmd+K：选中代码让AI修改
## 基本用法
1. 选中代码
2. 按 `Cmd+K`（Windows用 `Ctrl+K`）
3. 输入指令，回车
4. Tab确认修改

## 常用指令示例

| 指令 | 作用 |
|------|------|
| `重构这个方法` | 优化代码结构 |
| `添加注释` | 自动生成文档注释 |
| `改名为xxx` | 批量修改变量名 |
| `用stream改写` | 改变实现方式 |
| `处理可能的空指针` | 增加判空逻辑 |

## 实战：优化学生管理系统的添加方法

**选中代码：**
​```java
System.out.print("学号：");
int id = scanner.nextInt();
​```

**输入指令：** `添加输入校验，学号不能重复`

**Cursor生成：**
​```java
System.out.print("学号：");
int id = scanner.nextInt();
// 检查学号是否已存在
boolean exists = false;
for (Student s : students) {
    if (s.getId() == id) {
        exists = true;
        break;
    }
}
if (exists) {
    System.out.println("学号已存在！");
    return;
}


## 总结：
在给ai足够精细的描述之后，ai对于项目的完成度，精确度就越高。
在ai完成代码编写后，要有人工阅读代码的习惯，才可以不断归纳总结。


# 用Cursor根据注释生成代码

## 方法
写一行注释描述你要做什么，Cursor会自动生成代码

## 实战：生成学生类的getter/setter

**输入注释：**
​```java
// 为Student类生成所有属性的getter和setter
​```

**Cursor生成：**
​```java
public int getId() { return id; }
public void setId(int id) { this.id = id; }
public String getName() { return name; }
public void setName(String name) { this.name = name; }
public double getScore() { return score; }
public void setScore(double score) { this.score = score; }
​```

## 适合自动生成的场景
- ✅ getter/setter
- ✅ 构造方法
- ✅ toString()
- ✅ 简单的CRUD方法
- ❌ 复杂业务逻辑
- ❌ 算法核心代码

## 我的原则
> 自动生成的代码要检查一遍，理解每行的作用才能提交。

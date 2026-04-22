
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
>
> # Cursor 快捷键速查表（Windows版）

> Cursor 是一款 AI 驱动的代码编辑器，熟练掌握快捷键可以大幅提升开发效率

## 一、AI 核心功能（最常用）

| 功能 | 快捷键 | 说明 |
|------|--------|------|
| **AI 对话** | `Ctrl+L` | 打开侧边栏对话，可以问代码问题 |
| **内联编辑** | `Ctrl+K` | 选中代码后让 AI 修改 |
| **终端错误解释** | `Ctrl+Shift+R` | 解释终端里的报错 |
| **代码补全** | `Tab` | 接受 AI 的代码建议 |
| **拒绝补全** | `Esc` | 拒绝 AI 的代码建议 |

## 二、通用编辑快捷键

| 功能 | 快捷键 |
|------|--------|
| 保存 | `Ctrl+S` |
| 查找 | `Ctrl+F` |
| 全局搜索 | `Ctrl+Shift+F` |
| 复制行（未选中时） | `Ctrl+C` |
| 剪切行（未选中时） | `Ctrl+X` |
| 删除行 | `Ctrl+Shift+K` |
| 移动行向上/下 | `Alt+↑/↓` |
| 注释/取消注释 | `Ctrl+/` |
| 格式化文档 | `Shift+Alt+F` |

## 三、光标与选择

| 功能 | 快捷键 |
|------|--------|
| 移动到行首 | `Home` |
| 移动到行尾 | `End` |
| 移动到文档开头 | `Ctrl+Home` |
| 移动到文档结尾 | `Ctrl+End` |
| 选中整行 | `Ctrl+L` |
| 多光标选择 | `Ctrl+点击` |

## 四、终端快捷键

| 功能 | 快捷键 |
|------|--------|
| 打开/关闭终端 | `` Ctrl+` `` |
| 新建终端 | `Ctrl+Shift+`` ` |
| 清空终端 | `Ctrl+K` |

## 五、AI 功能详解

### 1. Ctrl+L（AI 对话）
- 打开侧边栏，可以问任何代码问题
- 选中代码后再按 `Ctrl+L`，AI 会知道你在问什么

### 2. Ctrl+K（内联编辑）
- 选中代码后按 `Ctrl+K`
- 输入指令，如「添加注释」「重构这个方法」
- 按 `Tab` 确认修改，`Esc` 取消

### 3. Ctrl+Shift+R（解释错误）
- 在终端出现报错时使用
- AI 会分析错误原因并给出解决方案

### 4. Tab（智能补全）
- Cursor 最核心的功能
- 写代码时自动预测下一行
- 按 `Tab` 接受

## 六、我的常用组合

| 场景 | 操作 |
|------|------|
| 写新代码 | 写注释 → 等 AI 补全 → Tab 接受 |
| 修改旧代码 | 选中代码 → Ctrl+K → 输入指令 → Tab 确认 |
| 遇到报错 | 选中报错 → Ctrl+Shift+R → 看 AI 解释 |
| 不懂的地方 | 选中代码 → Ctrl+L → 问 AI |



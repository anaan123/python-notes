# 📅 Day 01｜Python 学习笔记（JavaScript 开发者视角）

> 学习背景：已有 JavaScript / 前端基础（HTML / CSS / Vue）
> 学习目标：**快速看懂 Python 代码，并能进行 JS → Python 转换**

---

## 🎯 今日学习目标（已完成）

* ✅ 搭建 Python 开发环境
* ✅ 掌握 Python 基础语法与变量
* ✅ 理解 Python 与 JavaScript 的核心差异
* ✅ 能将简单 JS 代码转换为 Python

---

## 一、开发环境搭建

### 1️⃣ 安装与验证 Python

```bash
python --version
pip --version
```

* Python 版本：3.10+
* pip：Python 的包管理工具

---

### 2️⃣ 开发工具

* **VS Code（主力）**

  * Python 扩展
  * Pylance（类型提示非常友好）

---

### 3️⃣ 第一个 Python 程序

```python
print("Hello Python!")
```

JS 对比：

```js
console.log("Hello JS")
```

---

### 4️⃣ 虚拟环境（项目隔离）

```bash
python -m venv venv

# Windows
venv\Scripts\activate

# macOS / Linux
source venv/bin/activate
```

---

## 二、变量与数据类型（JS 对比）

### 🔍 JS vs Python 对照

| 概念   | JavaScript        | Python              |
| ---- | ----------------- | ------------------- |
| 变量   | `let x = 5`       | `x = 5`             |
| 常量   | `const PI = 3.14` | `PI = 3.14`（约定）     |
| 字符串  | `""` / ` `        | `""` / `''` / `"""` |
| 类型查看 | `typeof x`        | `type(x)`           |

---

### 基本示例

```python
age = 25
price = 19.99
is_student = True

name = "张三"
multi_line = """这是一个
多行字符串"""

print(type(age))   # int
print(type(name))  # str
```

---

### 类型转换

```python
str_age = str(age)
int_price = int(price)
```

---

## 三、列表（≈ JS 数组）

```python
fruits = ["apple", "banana", "orange"]

print(fruits[0])
print(fruits[-1])   # Python 特有

fruits.append("mango")
fruits.insert(1, "pear")

fruits.pop()
fruits.remove("apple")

print(len(fruits))
```

### 切片（Python 特色）

```python
numbers = [0, 1, 2, 3, 4, 5]
print(numbers[1:4])
print(numbers[:3])
print(numbers[::2])
```

---

## 四、字典（≈ JS 对象）

```python
person = {
    "name": "李四",
    "age": 30,
    "is_developer": True
}

print(person["name"])
print(person.get("age"))

person["city"] = "北京"
person["age"] = 31

del person["is_developer"]
```

### 遍历字典

```python
for key in person:
    print(key, person[key])
```

---

## 五、条件语句

```python
score = 85

if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
else:
    grade = "C"

status = "通过" if score >= 60 else "未通过"
```

* `elif` ≠ `else if`
* 使用 `and / or / not`

---

## 六、循环语句

### for 循环

```python
for fruit in fruits:
    print(fruit)

for i in range(len(fruits)):
    print(i, fruits[i])

for index, fruit in enumerate(fruits):
    print(index, fruit)
```

### while 循环

```python
count = 0
while count < 3:
    print(count)
    count += 1
```

⚠️ Python 没有 `++` / `--`

---

## 七、JS → Python 实战转换

### JS 原代码

```js
function calculateGrades(scores) {
  let total = 0;
  let max = scores[0];
  let min = scores[0];

  for (let i = 0; i < scores.length; i++) {
    total += scores[i];
    if (scores[i] > max) max = scores[i];
    if (scores[i] < min) min = scores[i];
  }

  return {
    average: total / scores.length,
    max,
    min
  }
}
```

### Python 版本

```python
def calculate_grades(scores):
    total = 0
    max_score = scores[0]
    min_score = scores[0]

    for i in range(len(scores)):
        total += scores[i]
        if scores[i] > max_score:
            max_score = scores[i]
        if scores[i] < min_score:
            min_score = scores[i]

    return {
        "average": total / len(scores),
        "max": max_score,
        "min": min_score
    }
```

---

## 八、Python 特色语法

### 列表推导式

```python
even_numbers = [x for x in range(1, 11) if x % 2 == 0]
squares = [x**2 for x in range(1, 6)]
```

### 字符串格式化（推荐 f-string）

```python
name = "张三"
age = 25

print(f"我叫{name}，今年{age}岁")
```

---

## 九、常见错误汇总

```python
# 缩进错误
# IndentationError

# 缺少冒号
# SyntaxError

# 未定义变量
# NameError

# 类型错误
"5" + 3  # TypeError

# 索引越界
arr = [1, 2, 3]
arr[5]  # IndexError
```

---

## 🔁 JS → Python 速查表

```python
js_to_python = {
    "console.log": "print",
    "let / const": "直接赋值",
    "arr.length": "len(arr)",
    "arr.push": "arr.append",
    "function": "def",
    "&& || !": "and or not",
    "模板字符串": "f-string",
    "for(let i=0;i<n;i++)": "for i in range(n)",
}
```

---

## ✅ Day 01 总结

* Python 语法比 JS 更简洁
* 缩进和冒号是最重要的规则
* 列表、字典非常强大
* JS 转 Python 是最高效的学习方式

👉 **明日重点：函数 + 参数 + 返回值 + 模块化**


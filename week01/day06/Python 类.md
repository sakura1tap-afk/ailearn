# Python 类与对象

类（class）可以理解成**创建对象的模板**，对象（object）是类创建出来的具体实例。

```python
class Person:
    pass

p1 = Person()
p2 = Person()
```

这里：

```text
Person → 类
p1/p2  → Person 的对象（实例）
```

## 对象里通常有什么

对象最核心的两部分：

```text
属性 attribute → 保存状态 / 数据
方法 method    → 定义行为
```

例如：

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hi, I'm {self.name}"

person = Person("Tom", 18)

print(person.name)
print(person.greet())
```

## `self` 是什么

当前阶段把 `self` 理解成：

> 正在操作的这个对象本身。

```python
self.name = name
```

表示把传入的 `name` 保存到**当前对象**的 `name` 属性里。

## `__init__`

```python
def __init__(self, ...):
```

在创建对象时自动调用，通常用于初始化实例属性。

```python
person = Person("Tom", 18)
```

会触发 `Person.__init__()`。

## 和 Java 的联系

你以前接触过 Java，所以可以先建立这个映射：

```text
class        → 类
object       → 对象
attribute    → 属性 / 字段
method       → 方法
__init__     → 初始化对象
self         → 当前实例，作用上接近 Java 的 this
```

语法不同，但“用类描述一类对象”的核心思想是相通的。

关联：[[Python 面向对象编程]]
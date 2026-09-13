# Python 面向对象编程

面向对象编程（OOP, Object-Oriented Programming）不是 Python 独有概念。你以前在 Java 里接触过的类、对象、继承，在 Python 里仍然存在，只是语法更轻。

当前阶段不需要一次吃完 OOP。先把主线抓住：

```text
类 class
→ 对象 object
→ 实例属性
→ 实例方法
→ 继承 inheritance
→ 方法重写 override
```

## 1. 类与对象

```python
class Person:
    pass

person = Person()
```

```text
Person → 类
person → Person 的对象 / 实例
```

类是模板，对象是根据模板创建出来的具体实例。

## 2. 实例属性与 `__init__`

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

person = Person("Tom", 18)
```

这里：

```text
name / age        → 创建对象时传入的数据
self.name/self.age → 保存在当前对象里的属性
```

`__init__()` 会在创建对象时自动调用。

## 3. 实例方法

```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        return f"Hi, I'm {self.name}"

person = Person("Tom")
print(person.greet())
```

方法本质上是和对象绑定的函数。

## 4. `self`

当前阶段把 `self` 理解成：

> 当前正在操作的实例对象。

```python
self.name
```

表示“这个对象自己的 `name` 属性”。

和 Java 中的 `this` 在作用上很接近。

## 5. 类属性

实例属性属于各自对象：

```python
self.name
```

类属性由整个类共享：

```python
class Person:
    species = "human"
```

访问：

```python
Person.species
```

当前知道两者有区别即可。

## 6. 继承

```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        return f"Hi, I'm {self.name}"


class Employee(Person):
    def __init__(self, name, job):
        super().__init__(name)
        self.job = job
```

这里：

```text
Person   → 父类 / 基类
Employee → 子类
```

`Employee` 可以复用 `Person` 已有的属性和方法。

`super()` 用来调用父类实现：

```python
super().__init__(name)
```

## 7. 方法重写

子类可以重新定义父类已有方法：

```python
class Employee(Person):
    def greet(self):
        return f"我是员工 {self.name}"
```

这就是方法重写（override）。

## 8. classmethod 与 staticmethod

教程里可能会继续出现：

```python
@classmethod
@staticmethod
```

现在只需要认识，不要求熟练。

`@classmethod` 的第一个参数通常是 `cls`，表示类本身。

`@staticmethod` 不自动接收 `self` 或 `cls`，更像“放在类里的普通工具函数”。

等真正项目里遇到再深入。

## 当前优先级

```text
★★★★★ class / object
★★★★★ __init__ / self
★★★★★ 实例属性 / 实例方法
★★★★☆ 继承 / super()
★★★☆☆ 方法重写
★★☆☆☆ 类属性
★☆☆☆☆ classmethod / staticmethod
```

你有 Java 基础，概念可能看起来熟，但现在真正需要补的是 **Python 里的实际写法和工程使用经验**，而不是重新背一遍 OOP 定义。

关联：[[Python 类]]
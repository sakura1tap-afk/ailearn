## 你将学到的东西[](https://www.pythontutorial.net/python-oop/#what-youll-learn "Anchor for What you'll learn")

- 通过定义类和方法来创建 Python 中的对象。
- 利用继承扩展类。
- 面向对象编程中的SOLID原则。
## Python 面向对象编程导论[](https://www.pythontutorial.net/python-oop/python-object-oriented-programming/#introduction-to-python-object-oriented-programming "Anchor for Introduction to Python Object-oriented Programming")

Python 中的一切都是一个对象。一个对象有一个状态和行为。创建对象时，首先定义一个类。然后，你可以从类中创建一个或多个对象。这些对象是类的实例。

## 定义一个类[](https://www.pythontutorial.net/python-oop/python-object-oriented-programming/#define-a-class "Anchor for Define a class")

定义[类](https://www.pythontutorial.net/python-oop/python-class/)时，你用关键词跟类名。例如，以下定义了一个类：`class``Person`

```python
class Person:
    pass
```

要从类创建对象，使用类名和括号 ，就像调用函数一样：`Person``()`

```python
person = Person()
```

在这个例子中，是该类的一个实例。课程[可以叫到](https://www.pythontutorial.net/python-built-in-functions/python-callable/)。`person``Person`

## 定义实例属性[](https://www.pythontutorial.net/python-oop/python-object-oriented-programming/#define-instance-attributes "Anchor for Define instance attributes")

Python 是动态的。这意味着你可以在运行时动态地为类的实例添加属性。

例如，以下为对象添加属性：`name``person`

```python
person.name = 'John'
```

但是，如果你创建另一个对象，新对象就不会有该属性。`Person``name`

要定义并初始化所有类实例的属性，你使用该方法。以下定义了具有两个实例属性和的类：`[__init__](https://www.pythontutorial.net/python-oop/python-__init__/)``Person``name``age`

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
```

当你创建对象时，Python 会自动调用该方法来初始化实例属性。在该方法中， 是类的实例。`Person``__init__``__init__``self``Person`

以下过程生成一个名为：`Person``person`

```python
person = Person('John', 25)
```

对象现在拥有 和 属性。要访问实例属性，使用点符号。例如，以下返回对象名称属性的值：`person``name``age``person`

```python
person.name
```

## 定义实例方法[](https://www.pythontutorial.net/python-oop/python-object-oriented-programming/#define-instance-methods "Anchor for Define instance methods")

以下内容为该类添加了一个调用的实例方法：`greet()``Person`

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hi, it's {self.name}."
```

调用实例方法时，你也使用点符号。例如：

```python
person = Person('John', 25)
print(person.greet())
```

输出：

```python
Hi, it's John
```

## 定义类属性[](https://www.pythontutorial.net/python-oop/python-object-oriented-programming/#define-class-attributes "Anchor for Define class attributes")

与实例属性不同，类属性是所有该类实例共享的。如果你想定义类常数或变量来记录类实例数，它们很有用。

例如，以下定义了该类中的类属性：`counter``Person`

```python
class Person:
    counter = 0

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        return f"Hi, it's {self.name}."
```

你可以从该类中访问属性：`counter``Person`

```python
Person.counter
```

或者从该类的任何实例中获得：`Person`

```python
person = Person('John',25)
person.counter
```

为了让变量更有用，创建对象后可以将其值增加1。要做到这一点，你需要在该方法中增加类属性：`counter``counter``__init__`

```python
class Person:
    counter = 0

    def __init__(self, name, age):
        self.name = name
        self.age = age
        Person.counter += 1

    def greet(self):
        return f"Hi, it's {self.name}."
```

以下方法创建了两个该类的实例，并显示了 的值：`Person``counter`

```python
p1 = Person('John', 25)
p2 = Person('Jane', 22)
print(Person.counter)
```

输出：

```python
2
```

## 定义类方法[](https://www.pythontutorial.net/python-oop/python-object-oriented-programming/#define-class-method "Anchor for Define class method")

像类属性一样，类方法被该类的所有实例共享。类方法的第一个参数是类本身。按照惯例，其名称为 。Python 会自动将这个参数传递给类方法。另外，你用@classmethod装饰器来装饰一个班级的方法。`cls`

以下示例定义了一个返回匿名对象的类方法：`Person`

```python
class Person:
    counter = 0

    def __init__(self, name, age):
        self.name = name
        self.age = age
        Person.counter += 1

    def greet(self):
        return f"Hi, it's {self.name}."

    @classmethod
    def create_anonymous(cls):
        return Person('Anonymous', 22)
```

以下展示了如何调用类方法：`create_anonymous()`

```python
anonymous = Person.create_anonymous()
print(anonymous.name)  # Anonymous
```

## 定义静态方法[](https://www.pythontutorial.net/python-oop/python-object-oriented-programming/#define-static-method "Anchor for Define static method")

静态方法不绑定于类或该类的任何实例。在 Python 中，你用静态方法将逻辑相关的函数分组到一个类中。要定义静态方法，你用装饰器。`@staticmethod`

例如，以下定义了一个类，其有两个静态方法，分别将摄氏度转换为华氏度，反之亦然：`TemperatureConverter`

```python
class TemperatureConverter:
    @staticmethod
    def celsius_to_fahrenheit(c):
        return 9 * c / 5 + 32

    @staticmethod
    def fahrenheit_to_celsius(f):
        return 5 * (f - 32) / 9
```

调用静态方法时，你使用语法。例如：`ClassName.static_method_name()`

```python
f = TemperatureConverter.celsius_to_fahrenheit(30)
print(f)  # 86
```

注意，Python 并不是隐式地传递实例（）和类（）作为静态方法的第一个参数。`self``cls`

## 单一继承[](https://www.pythontutorial.net/python-oop/python-object-oriented-programming/#single-inheritance "Anchor for Single inheritance")

类可以通过继承另一个类来重复使用。当子类继承父类时，子类可以访问父类的属性和方法。

例如，你可以定义一个继承自该类的类：`Employee``Person`

```python
class Employee(Person):
    def __init__(self, name, age, job_title):
        super().__init__(name, age)
        self.job_title = job_title
```

在类的方法内部调用了该类的方法来初始化和属性。允许子类访问父类的方法。`__init__``Employee``__init__``Person``name``age``super()`

该类通过添加一个称为 的属性来扩展该类。`Employee``Person``job_title`

是父类，而 是子类。要覆盖该类的方法，你可以定义该类的方法如下：`Person``Employee``greet()``Person``greet()``Employee`

```python
class Employee(Person):
    def __init__(self, name, age, job_title):
        super().__init__(name, age)
        self.job_title = job_title

    def greet(self):
        return super().greet() + f" I'm a {self.job_title}."
```

该 中的方法也称为类的方法。换句话说，它委派给父类的方法。`greet()``Employee``greet()``Person`

以下步骤创建该类的新实例并调用该方法：`Employee``greet()`

```python
employee = Employee('John', 25, 'Python Developer')
print(employee.greet())
```

输出：

```python
Hi, it's John. I'm a Python Developer.
```

在本教程中，你已经简要了解了Python面向对象编程的知识。
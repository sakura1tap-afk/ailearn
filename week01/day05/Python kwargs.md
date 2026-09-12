# Python `**kwargs`

`**kwargs` 用来接收**数量不固定的关键字参数**。

如果 `*args` 负责接住：

```python
func(1, 2, 3)
```

那么 `**kwargs` 负责接住：

```python
func(name="Tom", age=18)
```

## 1. `**kwargs` 在函数内部是字典

```python
def show_info(**kwargs):
    print(kwargs)

show_info(name="Tom", age=18)
```

输出：

```python
{"name": "Tom", "age": 18}
```

所以：

```text
kwargs 是 dict（字典）
```

你可以像普通字典一样使用它：

```python
def show_info(**kwargs):
    for key, value in kwargs.items():
        print(key, value)
```

## 2. 为什么要用它

有些函数允许调用者传很多可选配置，而且参数数量不固定：

```python
def create_user(name, **kwargs):
    print("name:", name)
    print("other:", kwargs)

create_user(name="Tom", age=18, city="Beijing")
```

此时：

```text
name = "Tom"
kwargs = {"age": 18, "city": "Beijing"}
```

## 3. `**` 也可以在调用函数时解包字典

```python
def introduce(name, age):
    print(name, age)

user = {
    "name": "Tom",
    "age": 18
}

introduce(**user)
```

相当于：

```python
introduce(name="Tom", age=18)
```

所以同样要区分：

```text
定义函数：**kwargs  → 收集多个关键字参数
调用函数：**some_dict → 把字典拆成关键字参数
```

## 4. 和 `*args` 放在一起

常见形式：

```python
def func(a, *args, **kwargs):
    print(a)
    print(args)
    print(kwargs)
```

调用：

```python
func(1, 2, 3, name="Tom", age=18)
```

得到：

```text
a = 1
args = (2, 3)
kwargs = {"name": "Tom", "age": 18}
```

## 当前阶段记住

```text
*args   → 多出来的位置参数 → tuple
**kwargs → 多出来的关键字参数 → dict
```

`args` 和 `kwargs` 只是惯用名字，真正决定行为的是 `*` 和 `**`。
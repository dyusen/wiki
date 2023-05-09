# Аннотации типов

Аннотации типов - это нововведение в Python, которое позволяет указывать типы аргументов функций, переменных и возвращаемых значений. Это дополнительная информация, которая помогает улучшить понимание кода и выявить ошибки во время выполнения.

Введение аннотаций типов в Python началось с версии 3.5. Для использования аннотаций типов, вы можете просто указать тип переменной или аргумента функции, используя двоеточие и имя типа.

Например, давайте посмотрим на функцию, которая принимает два аргумента - строку и число, и возвращает строку:

```python
def greet(name: str, age: int) -> str:
    return "Hello, {}! You are {} years old.".format(name, age)
```

Здесь мы указали, что `name` является строкой (`str`), `age` - целым числом (`int`), а функция возвращает строку (`str`).

Теперь, когда мы вызываем эту функцию, различные IDE, например pycharm, могут использовать аннотации для проверки :

```python
greet("John", 25)
greet(25, "John") 
```

Также стоит отметить, что аннотации типов не обязательны. Вы можете не указывать типы аргументов или возвращаемых значений, если не хотите. Однако, использование аннотаций типов делает ваш код более понятным и уменьшает вероятность ошибок во время выполнения.

Еще одно важное применение аннотаций типов - это помощь в документировании вашего кода. Если вы указываете типы аргументов и возвращаемых значений, это может помочь другим разработчикам лучше понять, как использовать ваш код.

Но нужно помнить, что аннотации типов не являются проверкой типов во время выполнения. Python не будет проверять, соответствует ли тип аргумента или возвращаемого значения указанному типу в аннотации. Если вам нужна проверка типов во время выполнения, вы можете использовать сторонние библиотеки, такие как `mypy`.

Давайте рассмотрим некоторые дополнительные возможности аннотаций типов:

- Аннотации типов могут быть не только именами типов, но и любыми выражениями, которые возвращают тип. Например, вы можете использовать типы из других модулей:

```python
from typing import List

def my_function(values: List[str]) -> int:
    return len(values)
```

Здесь мы использовали тип `List` из модуля `typing`, чтобы указать, что values является списком строк.

- Вы также можете использовать `Optional` из модуля `typing`, чтобы указать, что аргумент может быть `None`:

```python
from typing import Optional

def my_function(value: Optional[str]) -> str:
    if value is None:
        return "No value"
    else:
        return value
```

Здесь мы указали, что value может быть None, используя `Optional[str]`.

- Вы можете использовать аннотации типов для классов и методов классов:

```python
class MyClass:
    def __init__(self, value: str) -> None:
        self.value = value

    def get_value(self) -> str:
        return self.value
```

Здесь мы указали, что метод `__init__` принимает аргумент `value` типа `str` и ничего не возвращает (`None`), а метод `get_value` возвращает строку (`str`).

# Заключение

Помните, что использование аннотаций типов - это хорошая практика, которая помогает сделать ваш код более понятным и уменьшить вероятность ошибок во время выполнения.
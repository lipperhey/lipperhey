```python

from dataclasses import dataclass
from typing import Tuple


class Meta(type):
    def __new__(cls, name, bases, attrs):
        new_cls = super().__new__(cls, name, bases, attrs)
        return dataclass(unsafe_hash=True, frozen=True)(new_cls)


class Bio(metaclass=Meta):
    name        : str = "Johann Fischer"
    designation : str = "Data Scientist"
    company     : str = "Fischer"
    base        : str = "Linz, Austria"
    blog        : str = "lipperhey.github.io"


class Stack(metaclass=Meta):
    languages   : Tuple[str, ...] = ("Python", "Go", "Shell")
    databases   : Tuple[str, ...] = ("MySQL", "PostgreSQL", "Mongo", "Redis")
    misc        : Tuple[str, ...] = ("Docker", "Celery")
    ongoing     : Tuple[str, ...] = ("Django", "GraphQL")


class Social(metaclass=Meta):
    twitter     : str = "lipperhey"
    linkedin    : str = "lipperhey"
```

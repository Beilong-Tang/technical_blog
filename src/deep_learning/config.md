# Environment and Config


The following simple config describes my normal Environment setting:

```python
from argparse import Namespace
import argparse

class AttrDict(Namespace):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)

    def __getattribute__(self, name: str):
        try:
            return super().__getattribute__(name)
        except AttributeError:
            return None

    def __getitem__(self, key):
        return self.__getattribute__(key)

x = argparse.ArgumentParser()
x.add_argument("--x", default = 2)
x.add_argument('--y', default = 3)
args = x.parse_args()


name = AttrDict(**vars(args))

print(name)
print(name.x) # valid
print(name['x']) # valid
print(name['y']) # valid
```

# Tip: Caching a property

How to cache a method response


```python
from django.db import models
from django.utils.functional import cached_property

class SomeModel(models.Model):
    @cached_property
    def heavy_method(self):
        return 1+1
```

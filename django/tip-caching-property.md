# Tip - Caching a property

For some reason I always tend to forget this little snippet.


```python
from django.db import models
from django.utils.functional import cached_property

class SomeModel(models.Model):
    @cached_property
    def heavy_method(self):
        return 1+1
```

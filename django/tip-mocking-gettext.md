# Tip: Mocking unittest translations in Django

This is a simple example on how you can mock gettext/translation in django.

```python
from django.utils import translation

class MyTestCase(TestCase):
    def setUp(self):
        swe_trans = translation.trans_real.translation("sv-se")
        swe_trans._catalog['Name'] = 'Namn'
        swe_trans._catalog['Cat'] = 'Katt'

    def test_hello():
        ...
```

# Tip - Timing code blocks

```python
import time; start_time = int(round(time.time() * 1000))  # XXX Debug Timer
my_func()
print('marker:', int(round(time.time() * 1000)) - start_time, 'ms')  # XXX Debug Timer
```

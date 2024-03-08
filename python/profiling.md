# Profiling python

```
import cProfile, pstats
from io import StringIO

# Code to be profiled

pr.disable()  # end profiling
s = StringIO()
sortby = 'cumulative'
ps = pstats.Stats(pr, stream=s).sort_stats(sortby)
ps.print_stats()
print(s.getvalue())
```

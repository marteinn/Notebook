# How to measure page load

### Using curl

```
curl -o /dev/null -s -w 'Total: %{time_total}s\n'  https://mysite.test
```

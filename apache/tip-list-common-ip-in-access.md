# Tip - List the most common ip's in apache access log

This snippet will generate a list with the 10 most common ips in the access log.

`cat access_log | awk '{print $1}' | sort | uniq -c | sort -n | tail`

Returns:
```
2223 111.111.222.222
2363 111.111.333.333
```

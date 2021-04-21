# Nginx Snippets

## Logging

### Show how many times certain IP:s has requested route

```
>>> cat /var/log/nginx/access.log | grep myroute | awk '{print $3}' | sort | uniq -c | sort -nr

   2032 xx.xx.xx.xx
     58 xx.xx.xx.xx
     46 xx.xx.xx.xx
     45 xx.xx.xx.xx
     44 xx.xx.xx.xx
     44 xx.xx.xx.xx
     34 xx.xx.xx.xx
```

### Show all 404 routes sorted by number of requests

```
cat /var/log/nginx/access.log | awk '/" 404 / {print $8}' | sort | uniq -c | sort -n
```

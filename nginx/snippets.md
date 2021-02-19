# Nginx Snippets

## Logging

### Show show many times certain ips has requested route

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

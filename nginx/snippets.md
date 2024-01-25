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


### Show most called routes on combined .log and compressed log files

```
{ cat /var/log/nginx/access.log ; zcat /var/log/nginx/access.log.1.gz ; zcat /var/log/nginx/access.log.2.gz ; } | awk '{print $8}' | sort | uniq -c | sort -n
```

### Most common paths

```
cat /var/log/nginx/access.log | awk '{print $8}' | sort | uniq -c | sort -nr
```

### Most common ips

```
cat /var/log/nginx/access.log | awk '{print $3}' | sort | uniq -c | sort -nr
```

### Amount of requests per minute

```
cat /var/log/nginx/access.log | grep '2024:07:11' | wc -l
```

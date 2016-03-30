# Tip - Show all databases in redis

```
redis-cli INFO | grep ^db
db5:keys=300,expires=30
db6:keys=300,expires=30
```

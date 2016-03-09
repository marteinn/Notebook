# Tip - Flush DNS on OSX

```
sudo dscacheutil -flushcache
sudo killall -HUP mDNSResponder
```

## Reference
- http://www.igeeksblog.com/how-to-flush-dns-in-mac-os-x/

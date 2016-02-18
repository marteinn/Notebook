# Varnish - Cheat Sheet

## Application

#### Start
- `varnishd -a 127.0.0.1:80 -s file,/tmp,500M -f ./varnish/default.vcl`

## Stop
- `pkill varnishd`


## Cache

#### Ban (ban certain content from being served from your cache)
- `curl -X BAN http://domain.com/*`

#### Purge (pick out an object from the cache and discard)
- `curl -X PURGE http://domain.com`

## Reference
- [Purging and banning](https://www.varnish-cache.org/docs/3.0/tutorial/purging.html)

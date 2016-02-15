# Varnish - Cheat Sheet

## Application

#### Start
- `varnishd -a 127.0.0.1:80 -s file,/tmp,500M -f ./varnish/default.vcl`

## Stop
- `pkill varnishd`


## Cache

#### Ban domin
- `curl -X BAN http://domain.com/*`


# TODO: Add explanation about purge vs ban

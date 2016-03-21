# Tip - Redirect from http to https

This will redirect all traffic from http to https with pemantent redirects.

```
server {
    listen         [::]:80;
    return 301 https://$host$request_uri;
}
```

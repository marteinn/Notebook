# Tip - Disable any xmlrpc access for WP

```
# Block any call to xmlrpc
<Files "xmlrpc.php">
Order Allow,Deny
Deny from all
</Files>
```

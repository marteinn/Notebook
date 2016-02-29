# Tip - Create htpasswd

1. Create htpasswd file
```
htpasswd -c ./.htpasswd USER
```

3. In your .htaccess
```
AuthName "Restricted Area"
AuthType Basic
AuthUserFile /var/www/example.com/htdocs/.htpasswd
AuthGroupFile /dev/null
require valid-user
```

3. Update permissions
```
chmod -v 666 .htaccess
```

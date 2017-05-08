# Tip - Create htpasswd

1. Create htpasswd file
```
htpasswd -c ./.htpasswd USER
```

2. In your .htaccess
```
AuthName "Restricted Area"
AuthType Basic
AuthUserFile /var/www/example.com/htdocs/.htpasswd
AuthGroupFile /dev/null
require valid-user
```

2. ... or nginx
```
server {
  satisfy any;
  allow <myip>
  deny all;
  # Htpasswd
  auth_basic "Restricted";
  auth_basic_user_file /absolute/path/to/.htpasswd;
}
```

3. Update permissions
```
chmod -v 666 .htaccess
```

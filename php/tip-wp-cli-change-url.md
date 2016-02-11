# Tip - Change domain for wordpress using wp-cli

```bash
wp option update home 'http://new-domain.com/'
wp option update siteurl 'http://new-domain.com/'

wp search-replace 'http://original-domain.com' 'http://new-domain.com'
wp search-replace 'http://original-domain.com' 'http://new-domain.com'
```

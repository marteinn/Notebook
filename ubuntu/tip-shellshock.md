# Tip - Shellshock fix for Ubuntu

### Test if vulnerable
`env x='() { :;}; echo vulnerable' bash -c "echo this is a test"`

### Update bash
`sudo apt-get update && sudo apt-get install bash`

### Restart ssh
`ssh service restart`
or
`/etc/init.d/ssh restart`

### Restart apache
`apachectl -k restart`

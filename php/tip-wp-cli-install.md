# Tip - Install wp-cli on remote machine

#### Install and set permissions

```
cd ~
curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
php wp-cli.phar --info

chmod +x wp-cli.phar
mkdir ~/.wp-cli
mv wp-cli.phar ~/.wp-cli/wp
```

#### Export wp
```
vim ~/.bashrc
export PATH="$PATH:$HOME/.wp-cli"
```

#### Autoload bash from base_profile
```
if [ -f ~/.bashrc ]; thenj
    source ~/.bashrc
fi
```

#### Reload:
```
source ~/.bashrc
/usr/bin/env wp --info
```


## Reference:
- https://github.com/wp-cli/wp-cli/wiki/Alternative-Install-Methods#installing-locally-better-way

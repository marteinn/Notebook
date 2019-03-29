# Devops - Snippets

## Processes/ports

#### Show process associated to port
`lsof -i:8000 -n`

#### Show process associated to port (alt)
`lsof -n -P -i :3000`

#### Check if mysql is running
`sudo netstat -tap | grep mysql`

#### Check process on top
`top -pid $(pgrep -f php)`

#### Check process on top (alt)
top -p `pgrep mysql | tr "\\n" "," | sed 's/,$//'`

#### Check how long a process has been running
`ps -p 000 -o etime=`


## Mysql

#### Import sql dump into database
`mysql -u username -p -h localhost DATA-BASE-NAME < data.sql`

#### Export sql
`mysqldump -u username -p -h localhost DATA-BASE-NAME > data.sql`


## Hashing

#### Generate md5 hash
`echo "this will be encrypted" | md5`


## SCP

#### Copy from local machine to remote
`scp /path/to/file username@host:/path/to/destination`

#### Copy from remote machine to local
`scp username@host:/path/to/remote/file /path/to/local/file`

## Rsync

#### Sync remote to local folder
`rsync -r username@host:/remote/path/ /local/path/`

#### Sync local to remote folder
`rsync -r /local/path/ username@host:/remote/path/`


## Tar/gz/zip

#### Compress file
`tar -zcvf archive_name.tar.gz folder_to_compress`

#### Uncompress .tar
`tar -zxvf archive_name.tar.gz`

#### Generate zip with password
`zip -e <file_name>.zip <list_of_files>`

#### Uncompress .gz
`gunzip file.gz`


## Domains

#### Lookup domain through Google DNS
`nslookup -debug <domain> 8.8.8.8`

#### Lookup dns name servers
`dig +recurse +trace <domain> any`


## Jobs

#### Get process id
`pgrep -f keyword`


## Tmux

#### Kill pane in session
`tmux kill-window -t <number>`


## Cron

#### Check if running
`ps -ef | grep cron | grep -v grep`


## Filesystem

### Du

#### Sort folders by size in human readable format
`du -sk * --human-readable | sort --human-numeric-sort`

### Ls

#### Long list all(a) files(l) in CWD, ordering by size(S) ascending(r) and displaying size in human readable form(h).
`ls -Sharl`

### Stat

#### Show numerical unix permissions of files
`stat -c '%a %n' *`

### Df

#### Check inodes used
`df -i`

#### Check space left
`df -h`

### Find

#### Remove recursive files of a certain format
`find . -name '*.pyc' -delete`

### Pwd

#### Resolve symlink
`pwd -P`

### Namei

#### Check file permissions in path
`namei -om /path/to/check`


## s3cmd

#### Put folder to bucket
`s3cmd -P put --recursive /localfolder s3://bucketname/bucketfolder`


## SSH

#### Creates a new ssh key
`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`


## Apache

#### Generate htpasswd-file
`htpasswd -nb username password > .htpasswd`


## SMTP

#### Check if we have access to smtp server
`telnet mx1.example.com 25`

# Redis - Cheat Sheet

## Common commands

#### Select database
`SELECT <db_number>` (1 is default)

#### Show all keys in database
`KEYS *`

#### Delete key from database
`DEL "<keyname>"`

#### Delete all keys from current database
`FLUSHDB`

Example: `redis-cli -n <db_number> FLUSHDB`

#### Show key value
`GET "<keyname>"`

#### Get key type
`TYPE "<keyname>"`

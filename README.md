- `docker compose up` to run redis server..
- `docker exec -it redis-container redis-cli` to run redis-cli

### database

selecet some databae use `select 1`

### string

- set (key) (value)
- get (key)
- exists (key)
- append (key) "value"
- get key
- keys *
- keys test*
- del key
- get key
- setrange
- getrange
- mget key key key
- mset key value key value

## expired key
# Set a key with a value and expiration time in one command
SETEX mykey 10 "myvalue"

# Set a key to expire in 5000 milliseconds (5 seconds)
PEXPIRE mykey 5000

# Set a key to expire at a specific UNIX timestamp (e.g., 1627872000)
EXPIREAT mykey 1627872000

# Set a key to expire at a specific UNIX timestamp in milliseconds (e.g., 1627872000000)
PEXPIREAT mykey 1627872000000

# Check the remaining TTL in seconds
TTL mykey

# Check the remaining TTL in milliseconds
PTTL mykey

# Remove the expiration from a key
PERSIST mykey

# Check if a key exists (1 if exists, 0 if not exists/expired)
EXISTS mykey


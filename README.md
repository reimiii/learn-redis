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
```
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

## increment and decrement
# Set an initial value
SET mycounter 10

# Increment the value by 1
INCR mycounter
# Output: (integer) 11

# Increment the value by 5
INCRBY mycounter 5
# Output: (integer) 16

# Increment the float value by 2.5
INCRBYFLOAT mycounter 2.5
# Output: "18.5"

# Decrement the value by 1
DECR mycounter
# Output: "17.5"

# Decrement the value by 3
DECRBY mycounter 3
# Output: "14.5"
```
## flushdb
```
# Set some keys in the default database (DB 0)
SET key1 "value1"
SET key2 "value2"
# Output: OK

# Flush the current database (DB 0)
FLUSHDB
# Output: OK

# Check if the keys are deleted
EXISTS key1
# Output: (integer) 0
EXISTS key2
# Output: (integer) 0

# Set some keys in the default database (DB 0) again
SET key3 "value3"
SET key4 "value4"
# Output: OK

# Switch to another database (DB 1)
SELECT 1
# Output: OK

# Set some keys in DB 1
SET key5 "value5"
SET key6 "value6"
# Output: OK

# Flush all databases
FLUSHALL
# Output: OK

# Check if the keys are deleted in DB 1
EXISTS key5
# Output: (integer) 0
EXISTS key6
# Output: (integer) 0

# Switch back to DB 0 and check if the keys are deleted
SELECT 0
# Output: OK
EXISTS key3
# Output: (integer) 0
EXISTS key4
# Output: (integer) 0
```

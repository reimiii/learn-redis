## Redis CLI Transactional Operations

To run the Redis CLI, use the following command:
```sh
docker exec -it redis-container redis-cli
```

### Starting a Transaction
To start a transaction, use the `MULTI` command. This queues up subsequent commands until you execute them with `EXEC`.

```sh
docker exec -it redis-container redis-cli

# Start a transaction
MULTI
```

### Setting a Key
Within the transaction, you can set a key using the `SET` command.

```sh
# Set a key
SET key_MeaningOfLife 1
```

### Incrementing a Key
You can increment the value of a key using the `INCR` command.

```sh
# Increment the key
INCR key_MeaningOfLife
```

### Incrementing a Key by a Specific Value
To increment the value of a key by a specific amount, use the `INCRBY` command.

```sh
# Increment the key by 40
INCRBY key_MeaningOfLife 40
```

### Getting the Value of a Key
To retrieve the value of a key, use the `GET` command.

```sh
# Get the value of the key
GET key_MeaningOfLife
```

### Discarding a Transaction
If you want to discard all the queued commands in a transaction, use the `DISCARD` command.

```sh
# Discard the transaction
DISCARD
```

### Watching Keys for Conditional Execution
To watch one or more keys for changes, use the `WATCH` command. This is useful for implementing optimistic locking.

```sh
# Watch a key
WATCH key_MeaningOfLife
```

### Unwatching Keys
To stop watching all keys, use the `UNWATCH` command.

```sh
# Unwatch all keys
UNWATCH
```

### Executing the Transaction
Finally, execute all the queued commands with the `EXEC` command.

```sh
# Execute the transaction
EXEC
```

### Example Transaction
Here is a complete example of a transaction:

```sh
docker exec -it redis-container redis-cli

# Start a transaction
MULTI

# Set a key
SET key_MeaningOfLife 1

# Increment the key
INCR key_MeaningOfLife

# Increment the key by 40
INCRBY key_MeaningOfLife 40

# Get the value of the key
GET key_MeaningOfLife

# Execute the transaction
EXEC
```

### Output
After running the above commands, you should see the following output:

```sh
1) OK
2) (integer) 2
3) (integer) 42
4) "42"
```

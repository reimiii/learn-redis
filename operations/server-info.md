## Redis Server Information Operations

To run the Redis CLI, use the following command:
```sh
docker exec -it redis-container redis-cli
```

### 1. **PING**
Checks if the server is running and responds with "PONG."

```sh
PING
# Output: PONG
```

### 2. **INFO**
Retrieves information about the Redis server, including memory usage, clients, and more.

```sh
INFO
# Output: Various server information (e.g., memory, clients, keyspace, etc.)
```

### 3. **CONFIG GET**
Retrieves configuration parameters from the server.

```sh
CONFIG GET maxmemory
# Output: "maxmemory" value (e.g., "1000000000")
```

### 4. **CLIENT LIST**
Lists connected clients and their details.

```sh
CLIENT LIST
# Output: List of connected clients
```

### 5. **DBSIZE**
Returns the number of keys in the current database.

```sh
DBSIZE
# Output: Total number of keys
```

### 6. **LASTSAVE**
Returns the timestamp of the last successful save to disk.

```sh
LASTSAVE
# Output: Timestamp (e.g., 1679809437)
```

### 7. **TIME**
Returns the current server time.

```sh
TIME
# Output: Array with seconds and microseconds (e.g., [1679809437, 123456])
```

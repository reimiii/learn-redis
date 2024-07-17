## Redis Client Operations

To run Redis commands using the CLI, execute the following command:
```sh
docker exec -it redis-container redis-cli
```

Replace `redis-container` with the actual name of your Redis container. Now let's dive into the commands:

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

### 3. **CLIENT LIST**
Lists connected clients and their details.

```sh
CLIENT LIST
# Output: List of connected clients

CLIENT KILL ID ADDR
```

### 4. **DBSIZE**
Returns the number of keys in the current database.

```sh
DBSIZE
# Output: Total number of keys
```

### 5. **LASTSAVE**
Returns the timestamp of the last successful save to disk.

```sh
LASTSAVE
# Output: Timestamp (e.g., 1679809437)
```

### 6. **TIME**
Returns the current server time.

```sh
TIME
# Output: Array with seconds and microseconds (e.g., [1679809437, 123456])
```

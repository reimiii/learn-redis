## Redis CLI Monitor Commands

To monitor Redis activity in real-time, you can use the `MONITOR` command. It streams back every command processed by the Redis server. Here's how you can run it:

```sh
docker exec -it redis-container redis-cli monitor
```

This command will display a continuous stream of all executed Redis commands. It's useful for debugging and understanding what's happening in your database.

### Example Output:
```
1339518083.107412 [0 127.0.0.1:60866] "keys" "*"
1339518087.877697 [0 127.0.0.1:60866] "dbsize"
1339518090.420270 [0 127.0.0.1:60866] "set" "x" "6"
1339518096.506257 [0 127.0.0.1:60866] "get" "x"
1339518099.363765 [0 127.0.0.1:60866] "del" "x"
1339518100.544926 [0 127.0.0.1:60866] "get" "x"
```

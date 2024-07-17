## Redis Protected Mode

Redis is designed to be accessed by trusted clients within trusted environments. It's generally not recommended to expose Redis instances directly to the internet or any environment where untrusted clients can directly access the Redis TCP port or UNIX socket. Instead, untrusted access should always be mediated by a layer implementing access control lists (ACLs) and validating user input.

### Protected Mode

Since version 3.2.0, Redis enters a special mode called **protected mode** when executed with the default configuration (binding to all interfaces) and without any password set. In this mode:

- Redis only replies to queries from the loopback interfaces (localhost).
- Clients connecting from other addresses receive an error message explaining the issue and how to configure Redis properly.

To check if protected mode is enabled, use the following command:

```sh
redis-cli CONFIG GET protected-mode
```

If protected mode is enabled, it will respond with `"yes"`. To disable protected mode, modify the Redis configuration file (usually `redis.conf`) by setting `protected-mode no`.

### Access redis container from other machine
change in redis.conf
```sh
bind 0.0.0.0
```
This setting allows Redis to listen on all network interfaces within the Docker container. restart docker container to save the change

```sh
redis-cli -h <docker-host-ip> -p 6379

# Here, <docker-host-ip> is the IP address of the machine where Docker is running.
```



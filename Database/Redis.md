# Redis

Redis is a fast in-memory database and cache, open source under a BSD license, written in C and optimized for speed.
Redis’ name comes from "**RE**mote **DI**ctionary **S**erver".

Redis is often called a data structure server because its core data types are similar to those found in programming
languages like strings, lists, dictionaries (or hashes), sets, and sorted sets. It also provides many other data
structures and features for approximate counting, geolocation, and stream processing.

## Some features

- Storing data with key - value
- Storing data in memory
- Fast
- Case-insensitive

## Instalation

- Windows (https://github.com/microsoftarchive/redis/releases)
- Linux Distributions (https://redis.io/download)

## Useful commands

You can write `redis-cli` command to CMD or Terminal to use Redis CLI

### Basic

| Command               | explanation                                                                  |
|-----------------------|------------------------------------------------------------------------------|
| `HELP <Cammand>`      | Help                                                                         |
| `PING`                | Ping the server                                                              |
| `QUIT`                | Close the connection                                                         |
| `SET name Masoud`     | Set the string value of a key                                                |
| `GET name`            | Get the value of a key                                                       |
| `DEL name`            | Delete a key                                                                 |
| `EXISTS name`         | Determine if a key exists - If exists key - return 1 and not return exists 0 |
| `KEYS *`              | Find all keys matching the given pattern                                     |
| `FLUSHALL`            | Remove all keys from all databases                                           |
| `MSET a 10 b 20 c 30` | Set multiple keys to multiple values                                         |
| `MGET a b c`          | Get the values of all the given keys                                         |
| `type name`           | Determine the type stored at key                                             |

### Expirations

| Command                | explanation                                                                                     |
|------------------------|-------------------------------------------------------------------------------------------------|
| `TTL name`             | Get the time to live for a key - return -1 means no expiration and return -2 means was deleted  |
| `EXPIRE name 10`       | Set a key's time to live in seconds                                                             |
| `SETEX name 10 Masoud` | Set the value and expiration of a key                                                           |

### Lists (Array)

| Command               | explanation                                |
|-----------------------|--------------------------------------------|
| `LPUSH friends Mahdi` | Prepend one or multiple values to a list   |
| `RPUSH friends Reza`  | Append one or multiple values to a list    |
| `LRANGE friends 0 -1` | Get a range of elements from a list        |
| `LPOP friends`        | Remove and get the first element in a list |
| `RPOP friends`        | Remove and get the last element in a list  |
| `LTRIM friends 0 999` | Trim a list to the specified range         |

### Sets (Unique)

| Command                         | explanation                              |
|---------------------------------|------------------------------------------|
| `SADD hobbies "Weight lifting"` | Add one or more members to a set         |
| `SMEMBERS hobbies`              | Get all the members in a set             |
| `SREM hobbies "Weight lifting"` | Remove one or more members from a set    |

### Hashes (Dictionaries)

| Command                   | explanation                                                                       |
|---------------------------|-----------------------------------------------------------------------------------|
| `HSET person name Masoud` | Set the string value of a hash field                                              |
| `HGET person name`        | Get the value of a hash field                                                     |
| `HGETALL person`          | Get all the fields and values in a hash                                           |
| `HDEL person name`        | Delete one or more hash fields                                                    |
| `HEXISTS person name`     | Determine if a hash field exists - if exists - return 1 and not return  exists 0  |

# Redis

## What is Redis

- Redis can be used in any application and make it more performent.
- Redis is a NoSQL database, but not very similar to other NoSQL databases like MongoDB.
- Redis doesn't use tables or documents to store information. Instead it uses key-value pairs, similar to a JSON object.
- Redis is like one giant JSON object containing many key-value pairs.
- Unlike a normal database that runs on your disk and stores all your database information on this disk, Redis actually runs inside of your working memory (the RAM on your computer). This means that Redis is incredibly fast because it's all working inside of RAM.
- The downside of this is that your data is much more volatile, if your system crashes then you'll lose all your data unless you're backing it up consistently.
- Redis isn't typically used as a persistent database like PostgreSQL or MongoDB. Instead it's used for caching.
- So if you have expensive computations that you make consitently you can store those inside of Redis for quicker access next time.
- Redis will almost always be built on top of a traditional database. Instead of consistently making expensive queries to your traditional DB you can quickly check Redis to see if data already exists there, saving you hundreds to thousands of milliseconds.
- When writing Redis commands it's best practice to write the command name in all-caps simimlar to SQL.
- Everything stored in Redis will be of type string.

## Basic Redis Commands

- This starts Redis server:
  `redis-server`

- Access Redis CLI tool:
  `redis-cli`

- Exit Redis CLI tool:
  `exit` or `quit`

- Create new key-value pair in Redis:
  `SET <key> <value>`

- Access value:
  `GET <key>`

- Check if value exists in DB:
  `GET <key> <value>`

- Deletes key-value pair:
  `DEL <key>`

- Checks if key exists in DB:
  `EXISTS <key>`

- Access all keys:
  `KEYS *`

- Deletes everything from DB:
  `FLUSHALL`

- Clear input:
  `clear`

## Handling Expirations

- You can check the expiration time on items in your DB with the Time To Live command (TTL).
- If the value returned is -1 then that means no expiration was specified.
- If the value returned is -2 then that means the item has expired.

- Check time until expiration:
  `TTL <key>`

- Set expiration on key:
  `EXPIRES <key> <time amount in seconds>`

- Add new key-value pair with an expiration:
  `SETEX <key> <time amount in seconds> <value>`

## Lists

- Similar to a standard array or list.

- Add item to the beginning of list:
  `LPUSH <list name> <value>`

- Add item to the end of list:
  `RPUSH <list name> <value>`

- Remove item from the beginning of list:
  `LPOP <list name> <value>`

- Remove item from the end of list:
  `RPOP <list name> <value>`

- Access specific range or values from list starting from the left:
  `LRANGE <list name> <starting index> <ending index>`

- Access specific range or values from list starting from the right:
  `RRANGE <list name> <starting index> <ending index>`

## Sets

- A set is list of unique items.

- Adds value to the set if it exist, if it does not exits then the set will automatically be created:
  `SADD <set name> <value>`

- Removes value from set:
  `SREM <set name> <value>`

- Lists out all values in the set:
  `SMEMBERS <set name>`

## Hashes

- Hashes are key value that don't allow nesting within them. Meaning you can't nest hashes within each other.

- Creates or updates hash with specified key and its corresponding value:
  `HSET <hash name> <key> <value>`

- Returns value from specified hash at specified key:
  `HGET <hash name> <key>`

- Returns all key-value pairs in the hash:
  `HGETALL <hash name>`

- Deletes specified key-value pair:
  `HDEL <hash name> <key>`

- Checks if specified hash exists or not:
  `HEXISTS <hash name>`

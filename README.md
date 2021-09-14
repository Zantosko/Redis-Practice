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

## Basic Redis Commands

- This starts Redis server:

`redis-server`

- Access Redis CLI tool:

`redis-cli`

- Exit Redis CLI tool:

`exit` or `quit`

## Handling Expirations

## Lists

- Similar to a standard array

## Sets

- A sets is list of unique items.

- Adds value to the set if it exist, if it does not exits then the set will automatically be created:

`SADD <set name> <value>`

- Removes value from set:

`SREM <set name> <value>`

- Lists out all values in the set:

`SMEMBERS <set name>`

## Hashes

- Hashes are key value that don't allow nesting within them. Meaning you can't nest hashes within each other.

`HSET <hash name> <key> <value>`

- Creates or updates hash with specified key and its corresponding value.

`HGET <hash name> <key>`

- Returns value from specified hash at specified key.

`HGETALL <hash name>`

`HDEL <hash name> <key>`

- Deletes specified key-value pair.

`HEXISTS <hash name>`

- Checks if specified hash exists or not.

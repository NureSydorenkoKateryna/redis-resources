# redis-resources

# Redis Learning Resources

## Table of Contents
1. [Introduction](#introduction)
2. [Popular Use Cases](#popular-use-cases)
3. [Key-Value Storage and Data Structure](#key-value-storage-and-data-structure)
4. [Getting Started with Redis](#getting-started-with-redis)
5. [Supported Data Types](#supported-data-types)
6. [Retrieving Data](#retrieving-data)
7. [Memcached vs Redis](#memcached-vs-redis)
8. [Redis Configuration](#redis-configuration)
9. [High Availability in Redis](#high-availability-in-redis)
10. [Persistence in Redis](#persistence-in-redis)
11. [Additional Reading](#additional-reading)

## Introduction
- **What is Redis?**  
  [Read more](https://architecturenotes.co/p/redis) about Redis (Remote Dictionary Server), an in-memory key–value database. It is commonly used as a cache due to its ability to store data in RAM, making data retrieval extremely fast.

## Popular Use Cases
- **Redis Use Cases**  
  [Deep dive](https://medium.com/@rimac.code/deep-dive-into-redis-use-cases-eec3ca77a658) into Redis use cases such as caching, real-time analytics, and message brokering.

## Key-Value Storage and Data Structure
- **How do key-value stores work?**  
  Explanation in [Chapter 8 of NoSQL Distilled: A Brief Guide to the Emerging World of Polyglot Persistence by Pramod J. Sadalage, Martin Fowler].

## Getting Started with Redis
- **Installation Guide**  
  Learn how to install Redis on different platforms: [Redis installation guide](https://redis.io/docs/latest/operate/oss_and_stack/install/install-redis/). 
- **Running Redis on Docker**  
  Instructions for running Redis in Docker: [Guide](https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/docker/).
  [YouTube Explanation](https://youtu.be/1pfvz24BAUs?si=-XIzHj5Wi84gydZ3)
- **Connecting to Redis**  
  Use **Redis CLI** or **Redis Insights GUI** to connect to a running Redis instance.
- **Client APIs**  
  Interact with Redis using various programming languages: [Client APIs](https://redis.io/docs/latest/develop/clients/).

## Supported Data Types
- **Redis Data Types**  
  Learn about data structures like strings, hashes, lists, sets, sorted sets, and more:  
  - [Official documentation](https://redis.io/technology/data-structures/)  
  - [Additional insights](https://estuary.dev/blog/redis-data-types/)

## Retrieving Data
- **Basic commands**   
  - Naming convention: [Keyspace documentation](https://redis.io/docs/latest/develop/use/keyspace/)
- **Useful commands cheat sheet**  
  [Redis quick-start cheat sheet](https://redis.io/learn/howtos/quick-start/cheat-sheet)
- **Database Namespaces**  
  See [Seven Databases in 7 Days, page 281].

## Memcached vs Redis
- **Comparison**  
  [Read more](https://architecturenotes.co/p/redis) about the differences between Redis and Memcached, including single-threaded vs multi-threaded architecture and data eviction policies.

## Redis Configuration
- **Deployment Methods**  
  Redis can be deployed as:  
  1. **Single Redis Instance**  
  2. **Redis High Availability (HA)**  
  3. **Redis Sentinel**  
  4. **Redis Cluster**  
- **Persistence Configuration**  
  Redis stores data in memory but can persist data using:  
  - **RDB (Snapshotting)**
  - **AOF (Append-Only File)**  
  Learn more in the [official persistence documentation](https://redis.io/docs/latest/operate/oss_and_stack/management/persistence/).

## High Availability in Redis
- **Scaling with replication**  
  When data is written to the master instance, it sends copies to replicas to improve scalability and fault tolerance.

## Persistence in Redis
- **How Redis saves data**  
  Redis can save data to disk using RDB snapshots or AOF logs:  
  - Explanation of process and configurations.
- **Checklist for Configuration Management**  
  - Modify `redis.config` file manually.
  - Change settings dynamically using the CLI [Checklist of commands](https://github.com/NureSydorenkoKateryna/redis-resources/blob/main/rdb-aof-config.md)

## Additional Reading
- **7 Redis Features You Might Not Know**  
  [Read more](https://medium.com/codex/7-redis-features-you-might-not-know-bab8c9beb2c)
- **What is Redis and How Does it Work?**  
  [Article](https://medium.com/@ayushsaxena823/what-is-redis-and-how-does-it-work-cfe2853eb9a9)
- **Understanding Redis Persistence: AOF vs RDB**  
  [Detailed comparison](https://medium.com/@gauravpatilsde/understanding-redis-data-persistence-aof-vs-rdb-58688dda2c32)

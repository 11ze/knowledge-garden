---
title: 29｜无锁的原子操作：Redis 如何应对并发访问？
tags:
  - Redis
created: 2023-05-23T21:09:33+08:00
updated: 2023-09-06T01:55:56+08:00
---

- 原子操作

  - 单命令操作

    - 多个操作在 Redis 中实现成一个操作（如改源码）
    - INCR/DECR 命令

  - 以原子性方式执行 Lua 脚本

    - redis-cli --eval {lua.script} {keys}, {args}
    - 要避免把不需要做并发控制的操作写入脚本

- 并发访问中需要控制的操作

  - 读取 - 修改 - 写回操作（RMW）

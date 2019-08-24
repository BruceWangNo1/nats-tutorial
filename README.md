# NATS Tutorial

If you are a microservice rookie developer looking for tutorials on how to use a message queue like RabbitMQ or NATS, etc., then you have come to the right place. I compiled enough information you need to know to get you well started.

## Download

You can download NATS binary executable file directly from the official website and then put it in a PATH directory to make it available.

In case you are wondering the name of the binary, it is **nats-server**.

## Putting nats-server in PATH



## Starting NATS

```bash
nats-server -m 8222
```

You can see that NATS is listening for client connections on **0.0.0.0:4222** by default from the stdout.

**-m 8222**: Use port 8222 for http monitoring. This is for **nats-top**.

For more information on NATS, please refer to [the official documentation](https://nats-io.github.io/docs/).

## Monitoring NATS

nats-top is a top-like tool for monitoring nats-server servers. For more information on nats-top, please refer to [this page](https://nats-io.github.io/docs/nats_tools/nats_top/).

```bash
go get github.com/nats-io/nats-top
nats-top -m 8222
```

The output is something like the following.

```text
nats-server version 0.6.4 (uptime: 31m42s)
Server:
  Load: CPU: 0.8%   Memory: 5.9M  Slow Consumers: 0
  In:   Msgs: 34.2K  Bytes: 3.0M  Msgs/Sec: 37.9  Bytes/Sec: 3389.7
  Out:  Msgs: 68.3K  Bytes: 6.0M  Msgs/Sec: 75.8  Bytes/Sec: 6779.4

Connections: 4
  HOST                 CID      SUBS    PENDING     MSGS_TO     MSGS_FROM   BYTES_TO    BYTES_FROM  LANG     VERSION SUBSCRIPTIONS
  127.0.0.1:56134      2        5       0           11.6K       11.6K       1.1M        905.1K      go       1.1.0   foo, hello
  127.0.1.1:56138      3        1       0           34.2K       0           3.0M        0           go       1.1.0    _INBOX.a96f3f6853616154d23d1b5072
  127.0.0.1:56144      4        5       0           11.2K       11.1K       873.5K      1.1M        go       1.1.0   foo, hello
  127.0.0.1:56151      5        8       0           11.4K       11.5K       1014.6K     1.0M        go       1.1.0   foo, hello
  ```

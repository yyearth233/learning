# RabbitMQ

消息队列
用于消息缓冲，消息分发，应用程序异步操作，应用解藕。

优点：
解藕，异步，削峰

缺点：
可用性降低：MQ 挂了
复杂度提高：如何保证消息没有重复，消息丢失怎么办，消息顺序
一致性：


#### 优点：
解藕：
A 向 B, C, D 系统写入数据，如果改成 B, C, E 写入，需要改程序，
现把 A 的数据写入到 MQ，B, C, D, E 需要数据的自取。

异步：
A 向 B，C，D 写库各需要 200ms，一共需要 600ms
现写入各自的 MQ，几乎 0ms。

削峰：
某个时间，大量操作涌现，系统承受不了，
把消息放到 MQ 缓存，一点一点来。

#### RabbitMQ 与 Kafka

|        | RabbitMQ             | Kafka  |
| ------ | -------------------- | ------ |
| 吞吐量 | 1w 级                | 10w 级 |
|        | 支持多种协议，重量级 |        |
| 可靠性 | 高                   |        |
| 应用   | 企业级开发           | 日志   |


# fastlogagent

1、当前场景
  1）一个机器上部署多个应用，每个应用独立在一个jvm里，通过logback将日志写入磁盘；
  2）该机器上的日志代理（logstash等）从多个文件中读出日志数据，并可选择性地做二次处理（过滤、格式转换、字段增删等），最终将日志处理发送给日志中控（ES等）。

2、面临的问题
  1）多个应用并发写入日志，争抢机器IO资源，写入延迟较大。当然，设置为异步写入方式，能适当缓解；
  2）
  
  
3、解决方式
  通过共享内存机制优化。

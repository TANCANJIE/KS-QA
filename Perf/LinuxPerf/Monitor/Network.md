# 网络


## 统计指标
* 数据源: /proc/net/dev

* 网络IO
```md
采集方式：累计值，每10秒采集一次取差值； 指标: net.dev (key: system)；
rxbytes: 入口字节数，rxbytes*8/10 -> bit/s;
txbytes: 出口字节数，txbytes*8/10 -> bit/s;
```

## 网卡

*  /proc/net/dev

* 网卡入口流量
* 网卡出口流量
```md
数据源: /proc/net/dev; 采集方式：累计值，每10秒采集一次取差值； 指标: net.dev (key: system)；
rxbytes0.8: 网卡入口流量，rxbytes8/10 -> bit/s;
txbytes0.8: 网卡出口流量，txbytes8/10 -> bit/s;
```
* 网卡入口包量
* 网卡出口包量
```md
数据源: /proc/net/dev; 采集方式：累计值，每10秒采集一次取差值； 指标: net.dev (key: system)；
rxpackets/10: 网卡入口包量，rxpackets/10 -> op/s;
txpackets/10: 网卡出口包量，txpackets/10 -> op/s;
```
* 网卡入口丢包
* 网卡出口丢包
```md
数据源: /proc/net/dev; 采集方式：累计值，每10秒采集一次取差值； 指标: net.dev (key: system)；
rxdrop/10: 网卡入口丢包量，rxdrop/10 -> op/s;
txdrop/10: 网卡出口丢包量，txdrop/10 -> op/s;
```
* 网卡入口收包出错数
* 网卡出口发包出错数
```md
数据源: /proc/net/dev; 采集方式：累计值，每10秒采集一次取差值； 指标: net.dev (key: system)；
rxerrs/10: 网卡每秒入口收包错误数，rxerrs/10 -> op/s;
txerrs/10: 网卡每秒出口丢包错误数，txerrs/10 -> op/s;
```

## 网络协议
### 统计指标
* /proc/net/snmp
```md
数据源: /proc/net/snmp; 采集方式：累计值，每10秒采集一次取差值； 指标：net.snmp.tcp (key: system);
```
* /proc/net/netstat
```md
数据源: /proc/net/netstat; 采集方式：累计值，每10秒采集一次取差值； 指标：net.netstat.tcp (key: system);
```
```md
* In Segs - tcp协议层收到的数据包个数
* Out Segs
* Syn Ack Timeout -  tcp数据在指定时间内没有受到应答 ack 而超时的次数
* Listen Overflow(backlog full): Listen状态的端口因syn过多导致请求数量超过了sock的最大可积压数量的次数
* Listen drops: 请求数量超出或者是其他错误原因例如内存不足等导致监听新端口失败的次数
* Syn Cookies: SYN cookie是用于阻止SYN flood攻击的技术
* Syn Drops: syn_table过载，丢掉SYN的次数
* Passive Opens: 被动发送SYN包完成三次握手成功建立连接的次数
* Active Opens: 主动发送SYN包完成三次握手成功建立连接的次数
* Out of order packets received: 接收到的乱序包的数量
* Out of order packets drop(no space): 因空间不足进入乱序队列被丢弃的包数量
* Out of order packets merge(received before): 乱序包被合并的次数（重复接收）
* Duplicate sack received: 接收到相同sack包的次数
* Duplicate sack receive(out of order packet): 接收到相同的乱序sack包次数
* Duplicate sack sent(out of order data receive): 发送乱序sack包的次数
* Undo cwnd reduction(duplicate sack acked all retransmitted data): 撤销了发送DSACK包的次数
* Duplicate sack sent(old data receive): 发送过期DSACK包的次数
* Delayed acks: 发送延迟ACK包的次数
* Delayed ack locked by user: 发送延迟ACK时，用户已经锁定socket而导致ACK再次延迟发送的次数
* Delayed ack lost: 因为延迟ACK包丢失而再次发送的次数
* Retransmit segs: tcp层重传的数据包数量
* Prune called(no space): 由于接收缓冲区空间不足而进行tcp内存回收的次数
* Receive pruned(purge failed): 由于接收缓冲区空间不足而进行tcp内存回收后但空间还是不够的次数
* tcp_fast_retrans: tcp快速重传的包数量
* Time waited: timewait状态sock超时后被回收的个数
* Time wait killed: 使用PAWS机制后释放timewait状态sock的个数
* Time wait recycle: 试图进行timewait状态sock回收的次数，当新sock进行connect而hash时与原有的sock或timewait状态的sock冲突时，会触发回收工作
* Abort on timeout: tcp协议栈各定时器超时重复次数超过最大限制而关闭sock的次数
* Abort on close(data was unread): 当sock关闭时还有相关数据未读的次数
* Abort on syn: 接收到错误的syn包(序号错误)导致连接被reset的次数
* Abort on data: 当sock状态在TCP_FIN_WAIT1或TCP_FIN_WAIT2状态已经进入半连接但还是接收到数据而引起连接被reset的次数
* Abort on linger2(fin-wait2 with tcp_linger2): 当sock关闭时状态是TCP_FIN_WAIT2状态直接被reset的次数
* Abort on memory(out of memory. should tuning tcp_mem): 当sock关闭时由于内存不足而直接被reset的次数
* Abort failed(alloc/transmit skb failed): tcp协议栈在发送reset包而发送失败的次数
* Out rst: tcp协议层发送的reset数据包的个数
* Attempt failed: tcp syn_recv状态被reset的次数
* In checksum errors: tcp协议层接收校验失败的数据包的个数
* In error: tcp协议层接收出错的数据包的个数
```
## TCP
* /proc/net/tcp
```md
数据源: /proc/net/tcp; 采集方式: 对该状态tcp连接进行统计后输出； 指标: tcp.stat (key: system);
```
```
* Listen
* Established
* Time Wait
* Close Wait
* Sync Send
* Syn Receive
* Fin Wait 1
* Fin Wait 2
* Closing
* Last Ack
```
```md
listen: 
    处于监听状态的端口数；
established: 
    TCP建立完成后的稳定状态；
syn_sent: 
    发送SYN后，尚未完成三次握手；
syn_recv: 
    对方发送SYN后，返回了SYN，但未收到对方最后一个SYN包，还未完成三次握手；
fin_wait1: 
    设备可能处在等待接收对方回应收到 FIN的ACK，也可能处在等待接收对方发送的FIN；
fin_wait2: 
    设备已经发送了FIN，并且收到了对方回应的 ACK，还在等待对方发送 FIN；
time_wait: 
    设备处于 TIME-WAIT 状态表明设备收到了对方的 FIN，并且回应了 ACK，设备发送了 FIN，也收到了对方回应的 ACK。
    此时可以关闭连接。不过我们还是要倒计一段时间再关闭，防止影响连接端接收这边发送过去的 ACK。也防止和新连接产生冲突；
close_wait: 
    设备接收到连接方传来的FIN，现在需要等待设备上的程序为关闭连接做相应的工作；
last_ack: 
    设备已经接收了另一端发送过来的 FIN，并回应了ACK。
    也向对方发送了 FIN，此时还需等待接收对方回应的 ACK，以确认对方成功接收了这边发送过去的 FIN；
closing: 
    设备已经接收到了对方的FIN，自己也回应了ACK，还需等待接收对方回应自己FIN的ACK；
```
## 监控工具
```bash
$ cat /proc/interrupts
$ sar -n ALL 2 1
```
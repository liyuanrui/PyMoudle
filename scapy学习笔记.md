
### OSI七层模型：
```
第七层：应用层
第六层：表示层
第五层：会话层："GET/HTTP/1.0\n\n"
第四层：传输层：TCP()、UDP()、ICMP()
第三层：网络层：IP()
第二层：数据链路层：Ether()
第一层：物理层
```

### 写在开头
```
 /操作符在两层之间起到一个组合的作用。
summary()   显示一个关于每个数据包的摘要列表。
_表示上一句执行结果。
```

### 发送数据包
```
send()函数将会在第3层发送数据包。
>>> send(IP(dst="1.2.3.4")/ICMP())

sendp()函数将会工作在第2层。
>>> sendp("I'm travelling on Ethernet", iface="eth1", loop=1, inter=0.2)
```

### 发送和接收数据包（sr）
```
sr()函数是用来发送数据包和接收应答。
sr1()发送的数据包必须是第3层报文（IP，ARP等）。
srp()则是使用第2层报文（以太网，802.3等）。
dns查询
>>> sr1(IP(dst="192.168.5.1")/UDP()/DNS(rd=1,qd=DNSQR(qname="www.slashdot.org")))

SYN scans
>>>sr1(IP(dst='120.25.0.67')/TCP(dport=8000,flags="S"))
返回SA则表明端口是open的
```

### 模拟udp数据包
```
sr1(IP(dst='112.74.208.92')/UDP(dport=1024,sport=6666)/"hello world")
```

### 抓包
```
sniff(iface='wlan0',filter='udp and port 1024',count=5,prn=lambda x:x.summary())
```
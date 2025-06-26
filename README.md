# FCM Hosts

Android 14+或某些时期可能需要这个

## 新方案

hosts方案请优先尝试IPv6 hosts，IPv4有时候也会断连。也可以尝试DNS分流方案

hosts失效可以自己去 www.itdog.cn ping FCM的域名替换

## dns分流方案

<details><summary>展开/收起</summary>

0. 如果以前设置过hosts，请删掉
1. 添加`geosite:googlefcm`策略，DNS使用国内doh服务。注意，无论你设置了`cn`还是`!cn`策略，保证它是最后一条
2. `proxy_group`中添加谷歌FCM，并设为直连
3. 如果仍然连接失败且发现解析到IPv6，关闭IPv6

![image](https://github.com/user-attachments/assets/ca5e614e-9916-4193-938a-8da71b31962f)

</details>

## hosts方案

<details><summary>展开/收起</summary>

IPv4 hosts
```
142.250.107.188     mtalk.google.com
108.177.125.188     mtalk4.google.com
108.177.125.188     mtalk-staging.google.com
142.251.170.188     mtalk-dev.google.com
142.250.101.188     alt1-mtalk.google.com
173.194.208.188     alt2-mtalk.google.com
142.251.190.188     alt3-mtalk.google.com
192.178.212.188     alt4-mtalk.google.com
192.178.162.188     alt5-mtalk.google.com
142.250.96.188      alt6-mtalk.google.com
192.178.131.188     alt7-mtalk.google.com
192.178.131.188     alt8-mtalk.google.com
180.163.151.161     dl.google.com
180.163.150.33      dl.l.google.com
```
IPv6 hosts
```
2404:6800:4008:c07::bc mtalk.google.com
2607:f8b0:4023:c0b::bc alt1-mtalk.google.com
2404:6800:4008:c07::bc alt2-mtalk.google.com
2607:f8b0:4003:c0a::bc alt3-mtalk.google.com
2404:6800:4008:c07::bc alt4-mtalk.google.com
2607:f8b0:4024:c0b::bc alt5-mtalk.google.com
2404:6800:4008:c07::bc alt6-mtalk.google.com
2607:f8b0:4002:c08::bc alt7-mtalk.google.com
2404:6800:4008:c07::bc alt8-mtalk.google.com
2404:6800:4008:c05::bc mtalk-staging.google.com
2404:6800:4008:c1b::bc mtalk-dev.google.com
108.177.125.188 mtalk4.google.com
2401:3800:4001:16::1001 dl.google.com
2401:3800:4002:807::1001 dl.l.google.com
```
如果你的手机上装了 APatch / KernelSU / Magisk，也可以考虑使用 [bindhosts](https://github.com/bindhosts/bindhosts) 订阅

## 规则订阅

原作者链接：

https://gcore.jsdelivr.net/gh/entr0pia/fcm-hosts@fcm/fcm-hosts

https://github.com/entr0pia/fcm-hosts/raw/fcm/fcm-hosts

以下是自用链接：

https://gcore.jsdelivr.net/gh/sakana164/fcm-hosts@fcm/fcm-hosts

https://gcore.jsdelivr.net/gh/sakana164/fcm-hosts@fcm/fcm-hosts-v6

https://github.com/sakana164/fcm-hosts/raw/fcm/fcm-hosts

https://github.com/sakana164/fcm-hosts/raw/fcm/fcm-hosts-v6

</details>



## 测试

可以使用 [FCM Toolbox](https://github.com/SimonMarquis/FCM-toolbox) 测试消息送达的情况


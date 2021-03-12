---
title: "Freeswitch Stunserver"
date: 2020-10-31T09:49:45+08:00
lastmod: 2020-10-31T09:49:45+08:00
draft: true
keywords: []
description: "freeswitch default stunserver stun.freeswitch.org unreachable."
tags: [freeswitch]
categories: [pub]
author: "bob"

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: false
toc: true
autoCollapseToc: false
postMetaInFooter: false
hiddenFromHomePage: false
# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
contentCopyright: false
reward: false
mathjax: false
mathjaxEnableSingleDollar: false
mathjaxEnableAutoNumber: false

# You unlisted posts you might want not want the header or footer to show
hideHeaderAndFooter: false

# You can enable or disable out-of-date content warning for individual post.
# Comment this out to use the global config.
#enableOutdatedInfoWarning: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

<!--more-->
# stun unreachable
最近的freesiwtch stun server stun.freeswitch.org因不明原因不可达。
默认的stun.freeswitch.org是指向第三方的stun server的，自从stun.freeswitch.org指向stun.signalwire.com，很有可能freeswitch team自举了stunserver，丢弃了外部的stun请求。
这样造成了采取默认配置的freeswitch启动的时候失败，mod_sofia获取不到external ip加载失败。

可以调整配置中默认的stun地址解决，也可以配置sofia的external ip地址来解决。

以上源自FS-11604: [Configuration] Improve Vanilla config所造成。

## 公共的stun
stun.xten.com

stun.sipgate.net

...

在启动freeswitch后可以用过stun命令尝试更多的public stun server。
```shell
freeswitch@debian10> stun stun.xten.com
x.85.239.46:22427

freeswitch@debian10> stun stun.sipgate.net
x.85.239.46:22429

freeswitch@debian10>
```
## 修改vars.xml

```xml
    <X-PRE-PROCESS cmd="set" data="local_ip_v4=x.x.x.x"/>
    <X-PRE-PROCESS cmd="stun-set" data="external_sip_ip=auto-nat"/>
    <X-PRE-PROCESS cmd="stun-set" data="external_rtp_ip=auto-nat"/>
```
# maillist
在邮件列表里的讨论后，stun.freeswitch.org在不被滥用的前提下暂时恢复...
```
[Freeswitch-users] Replace stun.freeswitch.org in default	configuration since it's gone.

They are responding, but it's literally only there as a quick start, and is currently being abused to a level that is off the charts.  If your company depends on our stun servers, make your own.
I have two servers in rotation and they both get 500-1000 requests per second.

from brian(brian@freeswitch.com)
2020/11/10 7:22

```
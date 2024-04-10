# OCP Security Misconfiguration vulnerability

## Description

ocp（open-capacity-platform） is an enterprise microservice framework based on layui+springcloud (user rights management, Configuration center management, application management,....). Its core design goal is to separate the front and back end, rapid development and deployment, simple learning, powerful, to provide fast access to the core interface capabilities, its goal is to help enterprises build a set of similar Baidu ability open platform framework.

The auth-server component of ocp has a security configuration vulnerability. It can access all actuator terminals, including dangerous ports such as heapdump, which exposes sensitive information.

## Affected version

ocp == 2.0.1

## Vendor:

https://gitee.com/dromara/open-capacity-platform

## Software:

https://gitee.com/dromara/open-capacity-platform/releases/download/ocp-v2.0.1realse/auth-server.rar

## Poc

```shell
/actuator/heapdump
```

## Debug
The bootstrap.yml configuration shows that all endpoints of actuator are open.
![pic1](https://github.com/ggfzx/OCP-Security-Misconfiguration/blob/main/debug.png)

---
author: Marco Molteni
categories:
- Spring
color: '#7AAB13'
date: "2018-08-30T10:41:48Z"
description: How to change the level of output
image: /assets/img/
introduction: How to change the level of output
main-class: spring
tags:
- spring
title: Spring Boot logging level
url: /2018/08/30/spring-boot-logging-level/
---

# How to change the level of output in Spring Boot

Problem: When I'm testing my Spring application hundreds of lines of log code appear (DEBUG level).

The quantity of log is particularly important using Spring integration.

According to the spring documentation it should be possible to set the level of debug in the `application.properties` but the level of logs did not change.

The solution is to create a `logback.xml` in the classpath of the test (`[PROJECT_ROOT]/src/test/resources`):

<img src="/assets/img/uploads/2018/11/2018-08-31_23-19-41.png" />

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
	<include resource="org/springframework/boot/logging/logback/base.xml"/>
	<logger name="org.springframework" level="INFO"/>
</configuration>
```

## Before and after the change

Before:
<img src="/assets/img/uploads/2018/11/log_2018-08-31_23-11-24.png" />
After:
<img src="/assets/img/uploads/2018/11/log_2018-08-31_23-12-09.png" />



## Documentation
[Spring logging](https://docs.spring.io/spring-boot/docs/current/reference/html/howto-logging.html#howto-logging)

[Spring Logback.xml](https://docs.spring.io/spring-boot/docs/current/reference/html/howto-logging.html#howto-configure-logback-for-logging)
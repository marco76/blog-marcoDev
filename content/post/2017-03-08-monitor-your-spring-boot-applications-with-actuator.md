---
author: Marco Molteni
categories:
- Spring
date: "2017-03-08T00:09:26Z"
guid: http://marco.dev/?p=1024
id: 1024
image: /assets/img/wp-content/uploads/2017/03/header-springboot-100x23.png
main-class: spring
tags:
- actuator
- java
- spring
title: Monitor your Spring Boot applications with Actuator
url: /2017/03/08/monitor-your-spring-boot-applications-with-actuator/
---
When you have deployed many applications in your server / cloud it&#8217;s not easy to monitor their individual status.

You should verify that the server, the application and the database are working correctly.

Spring Boot help us to go in the direction of an automatic control of the status of the application exposing (on request) many information about it.

If you use the **@SpringBootApplication** annotation in your Application class and you add the Actuator dependency to your maven dependencies

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-actuator</artifactId>
    </dependency>
    

Spring generates for you a lot of predefined endpoints (accessible via REST) with a lot of internal information of the application: memory, beans, etc.

You can find the list of the endpoints here: <http://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-endpoints.html>

The type and quantity of information can be configured. This endpoints allow us to use external tools (e.g. regular ping or analysis of the JSON response) to create status dashboards and monitor if everything is working correctly or an intervention is required.

Spring cleverly hides some sensitive fields like &#8216;password&#8217; automatically and it can cache the results to reduce the impact of DDoS attacks.

You can see some examples of the result on my sample website:

<http://angular.cafe/app-spring-monitoring>

<img class="alignnone size-full wp-image-1022" src="/assets/img/uploads/2017/03/monitoring_2.png?resize=106%2C138" data-recalc-dims="1" />

<img class="alignnone size-full wp-image-1023" src="/assets/img/uploads/2017/03/monitoring_1.png?resize=300%2C475" data-recalc-dims="1" />
---
author: Marco Molteni
categories:
- Demo Application
- Intermediate
- Uncategorized
date: "2016-09-27T06:33:48Z"
guid: http://ngjava.com/?p=73
id: 755
main-class: spring
tags:
- angularjs
- java
- spring
title: 'Java and AngularJS 1.5x: Spring Boot tutorial'
url: /2016/09/27/java-and-angularjs-1-5x-spring-boot-tutorial/
---
Few months ago I created a demo application with Java EE, Angular JS and MongoDB. The article is here: [http://marco.dev/2016/03/14/openshift-angularjs-javaee-mongodb-css-mycv/](http://marco.dev/2016/03/14/openshift-angularjs-javaee-mongodb-css-mycv/ "http://marco.dev/2016/03/14/openshift-angularjs-javaee-mongodb-css-mycv/")

The result is visible here: <a href="http://myCv.host" target="_blank">myCv.host</a>

I like a lot Angular 2 but I know that the market is still Angular 1.5x dominated. For this reason I will maintain and upgrade this demo, maybe using it to shows the differences between AngularJS and Angular 2.

I converted the example to be a simple auto deploy tomcat jar file. MongoDB has been replaced with H2. The Git Repository is here: [https://github.com/marco76/myCv_spring](https://github.com/marco76/myCv_spring "https://github.com/marco76/myCv_spring")

&nbsp;

After ‘mvn package’ you can launch the application with this command: java –jar ./target/ROOT.jar

If you go to <http://localhost:8080> you should see this:

[<img style="background-image: none; padding-top: 0px; padding-left: 0px; display: inline; padding-right: 0px; border: 0px;" title="mycv" src="/assets/img/uploads/2016/09/mycv_thumb.png?resize=551%2C480" alt="mycv" border="0" data-recalc-dims="1" />](https://marco.dev/assets/img/wp-content/uploads/2016/09/mycv.png)

The technical details will follow!
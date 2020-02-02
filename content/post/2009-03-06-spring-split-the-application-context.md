---
author: Marco Molteni
categories:
- java
- Spring
date: "2009-03-06T09:49:19Z"
guid: http://molteni.wordpress.com/?p=18
id: 18
title: 'Spring: split the application context'
url: /2009/03/06/spring-split-the-application-context/
---
There are many reasons to declare the beans in more than one xml file. The most important reason is to maintain the code clear with a logical separation of the content of the file. The second reason is that when the application begin big only one file is not enough for the configuration.

In Spring is easy to split the content of the applicationContext.xml:
  
**web.xml**
  
You have to declare the **contextConfigLocation
  
`<br />
<context-param><param-name><br />
contextConfigLocation<br />
<param-value><br />
/WEB-INF/yourApplicationServices.xml, /WEB-INF/yourApplicationDatabase<br />
</param-value></context-param><br />
` 
  
<span style="font-weight:normal;">You can use Ant-style pattern to call your files e.g. /WEB-INF/yourApplication*.xml</span>**

[Spring reference](http://static.springframework.org/spring/docs/2.5.x/api/org/springframework/web/context/ContextLoader.html)
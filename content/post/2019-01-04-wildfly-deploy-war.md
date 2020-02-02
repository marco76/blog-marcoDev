---
author: Marco Molteni
categories:
- JavaEE, WildFly
color: '#7AAB13'
date: "2019-01-04T04:41:48Z"
description: ""
image: /assets/img/
introduction: Deploy to /
main-class: javaee
tags:
- JavaEE, WildFly
title: Deploy a WAR as root in WildFly
url: /use-wildfly-deploy-root
---

## using maven / manual deploy
Save your war with the name ROOT.war and deploy it, WildFly will configure it as root application.

## using configuration files
In your `[MAVEN_ROOT]/webapp/WEB-INF` create `jboss-web.xml` and add:

```xml
<jboss-web>
    <context-root>/</context-root>
</jboss-web>
```

## serve index.html
To serve your main page update web.xml:
```xml
<welcome-file-list>
    <welcome-file>index.html</welcome-file>
</welcome-file-list>
```

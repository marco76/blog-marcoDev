---
author: Marco Molteni
categories:
- Java
date: "2018-10-08T10:41:48Z"
description: ""
image: /assets/img/
introduction: How to initialize an HashMap inline in a Java lambda expression
main-class: java
tags:
- java
title: HashMap inline initialization
url: /hashmap-inline-initialization/
---

# Create and initialize HashMap inline in a lambda stream

Working with Spring Integration I had the need to create MessageHeaders class in a Lambda expression.The MessageHeaders object requires an HashMap as constructor parameter and the inline initializations of an HashMap is not the most intuitive.
The solution:

```java
@Override
public List<Message> handleFileRequest() {
// we create a list from an enumerator
List<Message> messageList = Arrays.stream(FileType.values())
      // we read the file content from an external provider
      .map(externalProviderService::readFileFromExternalProvider)
      // for each object we create a new message
      .map(file -> MessageBuilder.createMessage(file,
         new MessageHeaders(new HashMap<String, Object>() { {
        put("fileName", file.getTitle());
      } })))
      .collect(Collectors.toList());

  return messageList;
}
```

In detail:

```java
new HashMap<String, Object>() { {put("valueText", Object} }
```

The first brace ({ }) creates an Anonymous Inner Class, the second brace initializes a block inside the Anonymous Inner Class.
This Java notation is not new but very unusual. 

You can consider to call an external method to generate your hashmap.
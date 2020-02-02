---
author: Marco Molteni
categories:
- Web, Javascript, Vue
color: '#7AAB13'
date: "2019-01-02T01:41:48Z"
description: ""
image: /assets/img/
introduction: Use the Showdown markup library in Vue.js
main-class: vue.js
tags:
- Web, Javascript, Vue
title: Use Showodown in Vue.js
url: /markdown-vuejs
---

# Import and use Showdown

In this use case the user can write some MD and convert it to html clicking a button in the form.

Import [ShowDown](https://github.com/showdownjs/showdown) in your project using npm `npm install showdown`

Add the library to your component:

```javascript
<script>
     import showdown from "showdown";
...
</script>
```

Declare a variable that contains the markdown text:

```javascript
 data() {
    return {
       markdown: '# hello'
    }
 }
```

Add a method that convert the markdown in html:
```javascript
methods: {
    convert() {
        let converter = new showdown.Converter(),
            text = '# hello, markdown!';
            this.htmlData = converter.makeHtml(text);
    },
```

Add a button to call the conversion from Markdown to HTML:

`<button @click="convert">Convert to HTML</button>`

Write the html in your page:

`<span v-html="htmlData"></span>`

`v-html` tells Vue.js that the content is safe html and can be interpreted.
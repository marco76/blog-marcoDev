---
author: Marco Molteni
categories:
- Angular
color: '#7AAB13'
date: "2019-12-12T01:41:48Z"
description: ""
draft: true
introduction: Few tips/reminders about Angular
main-class: angular
tags:
- Angular
title: Angular Tips
url: /angular-tips
---

## Change detection: OnPush

``` javascript
@Component({
  ...
  changeDetection: ChangeDetectionStrategy.OnPush
})
```

`OnPush` improves performancesreducing change detection cycles. Detection limited to:
- @Input property changes
- An event emits
- A bound observable emits
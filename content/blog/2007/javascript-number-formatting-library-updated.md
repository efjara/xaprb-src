---
title: JavaScript number-formatting library updated
date: "2007-06-19"
url: /blog/2007/06/19/javascript-number-formatting-library-updated/
categories:
  - Web
---

I've released a new version of my [powerful, flexible, efficient JavaScript number-formatting library](/blog/2006/01/05/javascript-number-formatting/), which is probably the best available. This release adds a fix for zero-padding negative numbers.

If you find bugs, please send me test cases I can use to reproduce and add to the unit test suite. One test per line, like "input", "format", "expected" is best. For example, this is a great test case:

```
-1, "#,#.00", "-1.00"
```

I can plug that directly into the unit test suite, run it, and if it gives back "-01.00" it will fail the test. This makes it much easier and more convenient for me to fix bugs.


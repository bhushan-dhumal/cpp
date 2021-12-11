---
tags: [Effective C++]
title: Item 2
created: '2021-12-11T07:37:01.366Z'
modified: '2021-12-11T07:43:28.238Z'
---

# Item 2
## Prefer consts, enums and inlines to #defines

This item might better be called "prefer the compiler to the preprocessor"
- For simple constants, prefer const objects or enums to #defines.
- For function-like mcaros, prefer inline functions to #defines.

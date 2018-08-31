---
id: Query
title: Query
sidebar_label: Query
---

**Warning!** This function can not be called outside of the library.

Returns function which takes one argument and calls to server to query profile.

Response structure from server is 
```javascript
    {
      ans: '1 if user matches segment and 0 otherwise'
    }
```
---
id: event-guide
title: Event
sidebar_label: Event 
---

Another big part of Personic is that you can track you users and save track data to profile.
Let's start tracking our user


```javascript
    import Personic from 'personic'
    
    let sdk = new Personic('app_id')
    
    sdk.identify('user_id')
      .then(() => {
        let evname = 'buy';
        let event = {
         type: "shoes",
         size: 42,
         price: 16,
        }
         
        return sdk.track(evname, event);          
      })
      .then((result) => {
        console.log(result)
      })
```
In the `result` you can see success of profile update and version of profile.
It is very simple to track your users.Just remember to `indentify` the user you want so that sdk knows what profile to update.



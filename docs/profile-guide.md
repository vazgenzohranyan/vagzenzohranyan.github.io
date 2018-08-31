---
id: profile-guide
title: Profile
sidebar_label: Profile
---

The main purpose of Personic is to make it less difficult to manage users and their profiles.
So the most important part of Personic is `profile`.
Lets create profile with sdk and make some changes to it.

```javascript
    import Personic from 'personic'
    
    let sdk = new Personic('app_id')
    
    sdk.identify('user_id')
      .then(() => {
        console.log('User identified')
      })
```
`identify` function on `sdk` lets you identify user or create it if there is not.

Now when you identified user you can manipulate it.

You can add some properties to it with 
```javascript
    sdk.getProfile().set('age',16)
```
It is simple way to add `age` property to user profile.For more functions check [Profile](api-internals.md#Profile).
To check other good part of Personic go to [Event](event-guide.md). 
---
id: quick-start
title: Quick Start
sidebar_label: Quick Start
---

Here is the way to start using Personic SDK.

## Step 1 - installation
```bash
    npm i personic
```
Install personic with `npm`.

For more about installing `presonic` and `personic-cli` see [Installation](Installation.md).

## Step 2 - creating SDK client

Require it in your project and create SDK.

```javascript
    import Personic from 'personic'
    
    // Create new SDK with app id
    let sdk = new Personic('123456789abcd')
```
In order to create SDK you first need to create [application](CLI-app.md).

In order to find application id you can use [CLI](CLI.md) command.

## Step 3 - adding and identifying users

Start adding users in your application.

In order to do it 
```javascript
    sdk.indentify('user_id')
      .then(() => console.log('User identified'))
```
Then in your console you will see the result of request.
```
Request Data:
 { method: 'POST',
  url: 'http://127.0.0.1:9000/api/v1/identify',
  body: 
   { app_id: '123456789abcd',
     user_id: null,
     sdk: 'personic-sdk',
     v: 'v1',
     api_data: { user_id: 'user_id' },
     hash: '39e6ded62332644dfde27f25515f93bc' },
  json: true,
  encoding: 'utf8' }
Identify Result:
 { token: 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoiam9obl8xNyIsInVoIjoiYWFhX2pvaG5fMTciLCJhcHBfaWQiOiJhYWEiLCJzaWQiOiI1OTEzNjBjMGJlNzZjYTAzIiwiZXhwIjoxNTM0MDc1NDAxMjEyLCJpc3UiOjE1MzQwNzE4MDEyMTJ9.ySAuHQhO3i3gYeCg7qvKr_3syik4HHtqgE0pS2awzmE',
  up: {},
  upv: 1 }
```

## Step 4 - updating profile

Add some properties to user profile using SDK.

```javascript
    sdk.getProfile().set('age', '16')
    .then((pofile) => {
      console.log(profile)
    });
```
`profile` contains updated profile of user.
```
    { upv: 1534072175, up: { age: 16 } }
```

| Result property | Description                  |
| --------------- | ---------------------------- |
| `upv`             | Version of user profile      |
| `up`              | User profile data            |

## Step 5 - tracking user

Track your users using sdk.

```javascript
    sdk.track('login', {'dat': Date.now()})
      .then((result)=> console.log(result));
```
In your console you will see request info and the result.

``` 
    Request Data:
     { method: 'POST',
      url: 'http://127.0.0.1:9000/api/v1/track',
      body: 
       { app_id: 'aaa',
         user_id: 'asd',
         sdk: 'personic-sdk',
         v: 'v1',
         token: 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoiYXNkIiwidWgiOiJhYWFfYXNkIiwiYXBwX2lkIjoiYWFhIiwic2lkIjoiMTM4ZDdiMmUyNWE4OGZhNSIsImV4cCI6MTUzNDA3NTk5OTQ2NCwiaXN1IjoxNTM0MDcyMzk5NDY0fQ.idkrCKAibe2konG2hiiHyMVgJ5ebNPThQufaUt8wf7I',
         api_data: { evn: 'buy', evd: [Object] },
         hash: '21227d1f63e1102265dbbb9fb9811bfe' },
      json: true,
      encoding: 'utf8' }
    // Result object
    { success: 1, v: 3 }
```

| Result property | Description                  |
| --------------- | ---------------------------- |
| `success`             | Boolean value defining the success of request(1 is true,0 otherwise)      |
| `v`              | Revision number of profile       |

## Step 6 - querying user with segment

After all this you can start making queries on user.

```javascript
    import {And, Or, FilterFunctions, ProfileCondition, BehaviorCondition, PropertyCondition} from 'personic'
     
    // Segment example
    
    let profileCondition = ProfileCondition('age', FilterFunctions.isLessThan(50))
    let propertyCondition = PropertyCondition('date', FilterFunctions.isBetween(Date.now() - 10 * 24 * 3600 * 1000, Date.now()))
    let behaviorCondition = BehaviorCondition('login').where(propertyCondition).count().isMoreThan(10)
    let segment = sdk.profileMatch(profileCondition).behaviorMatch(behaviorCondition)
    
    sdk.execute(segment)
    .then((result) => console.log(result))
```
Checks if user log ins mor than 10 times last 10 days and have age less than 50.

The result example will be
``` 
    { ans : 0 }
```
| Result property | Description                  |
| --------------- | ---------------------------- |
| `ans`             | 1 if user is in segment,0 otherwise      |

For more see [Segment](Segment.md).

To see more about SDK see [SDk](SDK.md).
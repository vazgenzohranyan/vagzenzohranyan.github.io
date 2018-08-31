---
id: segment-guide
title: Segment
sidebar_label: Segment
---

Besides all the part about profile and events, Personic is designed particularly for segmentizing your users.
In order to create segment we just need a few steps.

```javascript
    import Personic from 'personic'
    
    let sdk = new Personic('app_id')
    
    sdk.identify('user_id')
      .then(() => {
        let profileConditions = ProfileCondition('age', FilterFunctions.isLessThan(100));
        let propertyCondition = PropertyCondition('type',FilterFunctions.equals('shoes'));
        let bevaiour = BehaviorCondition('buy').where(propertyCondition).count().isMoreThan(1); 
        let segment = sdk.profileMatch(profileConditions).behaviorMatch(bevaiour);
        return sdk.execute(segment);
      })
```
Here we define `profileCondition` for user profile part and `propertyCondition` for tracking part.
If you want to query user's event data you neew first to define event property condition than make aggregation on it.
Then when you already created segment just execute it.In the result you will see 
``` 
        { ans : Bool }
```
which defines the result of execution.`1` defines that you user is under the segment and `0` otherwise.
For more about conditions see
* [Profile conditions](#profile-sdk)
* [Property conditions](#property-sdk)
* [Behaviour condition](#event-sdk)

And for making segment see
[SDK](#sdk-api)
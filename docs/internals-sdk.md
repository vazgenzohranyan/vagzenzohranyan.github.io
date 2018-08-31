---
id: internals-sdk
title: Internals
sidebar_label: Internals 
---

**Note** All this functions can not be called outside of library but defined here to make user use Personic SDK clearly.

<a name="Profile"></a>
## <span style="color:green">Profile</span>

The response structure from server in every update of profile is 
```javascript
    {
      up: 'user updated profile data'
      upv: 'user profile version'
    }
```
Returns object with this properties.
### .getUserId()

Returns an id of indentified user.

### .getToken()

Returns token of the indentified user.

### .getProfileVersion()

Returns version of the profile.

### .indentify(user_id)

`user_id` is the id of a user to indentify.
Check `user_id` to be valid user id and calls server with that id to get user profile and saves it.

### .sync() 

Syncs user profile from server.

### .setOnce(attrName, attrVal)

`attrName` is attribute name of profile and `attrVal` is attribute value to assign.
Checks params to be valid and calls server to update profile.If `attrname` of profile is not defined,then sets `attrVal` to profile object.
Otherwise does not do anything.

### .set(attrName, attrVal)

`attrName` is attribute name of profile and `attrVal` is attribute value to assign.
Checks params to be valid and calls server to update profile.Sets `attrVal` to `attrName` of the profile.

### .setBatch(attrMap) 

`attrMap` is key value object, where keya are attribute names of the profile and values are attribute values that should be set.
Checks params to be valid and calls server to update user profile based on `attrMap`.

### .append(attrName, attrVal)

`attrName` is attribute name of profile and `attrVal` is attribute value to append.
Checks params to be valid and calls server to update profile.Appends the list of `attrName` with `attrVal`.

### .prepend(attrName, attrVal)

`attrName` is attribute name of profile and `attrVal` is attribute value to prepend.
Checks params to be valid and calls server to update profile.Appends the list of `attrName` from the start with `attrVal`.

### .unset(attrName)

`attrName` is attribute name of profile.
Checks params to be valid and calls server to update profile.Deletes `attrName` from profile object.

### .unsetBatch(attrArray)

`attrArray` is array of attribute names to be deleted.
Checks params to be valid and calls server to update profile.Deletes all attributes from `attrArray`.

### .increment(attrName, attrVal)

`attrName` is attribute name of profile and `attrVal` is attribute value to increment.
Checks params to be valid and calls server to update profile.Increments `attrName` property with `attrVal`.

### .incrementBatch(attrMap)

`attrMap` is key value object where keys are attribute names and values are the values that attributes should be incremented with.


<a name="Query"></a>
## <span style="color:green">Query</span>


Returns function which takes one argument and calls to server to query profile.

Response structure from server is 
```javascript
    {
      ans: '1 if user matches segment and 0 otherwise'
    }
```



<a name="Request"></a>
## <span style="color:green">Request</span>

This function is used anywhere from sdk to make requests to server.

Returns object with only one function 

### .post(endpoint, data)

`endpoint` is the url of server to call and `data` is request data to send.


<a name="Event"></a>
## <span style="color:green">Event</span>

Returns object with only one function.

### .track(evn, evd)

`evn` is the event name and `evd` is event data.
Calls server with `evn` and `evd` to update profiles events attribute. 


<a name="Segment"></a>
## <span style="color:green">Segment</span>

Main function to make segment for querying users.Excepts two arguments
``` 
    profile - Condtions object for user profile type
    behavior - Conditions object and aggragtion for user track data 
```
If `profile` is in arguments, returns object with 3 functions
* behaviorMatch - takes one argument as behavior object and returns new segment with it and profile defined earlier
* toObject - returns segment object
* toString - returns stringified segment object


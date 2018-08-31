---
id: Profile
title: Profile
sidebar_label: Profile
---

**Warning!** This function can not be called outside of the library.

The response structure from server in every update of profile is 
```javascript
    {
      up: 'user updated profile data'
      upv: 'user profile version'
    }
```
Returns object with this properties.
## getUserId()

Returns an id of indentified user.

## getToken()

Returns token of the indentified user.

## getProfileVersion()

Returns version of the profile.

## indentify(user_id)

`user_id` is the id of a user to indentify.
Check `user_id` to be valid user id and calls server with that id to get user profile and saves it.

## sync() 

Syncs user profile from server.

## setOnce(attrName, attrVal)

`attrName` is attribute name of profile and `attrVal` is attribute value to assign.
Checks params to be valid and calls server to update profile.If `attrname` of profile is not defined,then sets `attrVal` to profile object.
Otherwise does not do anything.

## set(attrName, attrVal)

`attrName` is attribute name of profile and `attrVal` is attribute value to assign.
Checks params to be valid and calls server to update profile.Sets `attrVal` to `attrName` of the profile.

## setBatch(attrMap) 

`attrMap` is key value object, where keya are attribute names of the profile and values are attribute values that should be set.
Checks params to be valid and calls server to update user profile based on `attrMap`.

## append(attrName, attrVal)

`attrName` is attribute name of profile and `attrVal` is attribute value to append.
Checks params to be valid and calls server to update profile.Appends the list of `attrName` with `attrVal`.

## prepend(attrName, attrVal)

`attrName` is attribute name of profile and `attrVal` is attribute value to prepend.
Checks params to be valid and calls server to update profile.Appends the list of `attrName` from the start with `attrVal`.

## unset(attrName)

`attrName` is attribute name of profile.
Checks params to be valid and calls server to update profile.Deletes `attrName` from profile object.

## unsetBatch(attrArray)

`attrArray` is array of attribute names to be deleted.
Checks params to be valid and calls server to update profile.Deletes all attributes from `attrArray`.

## increment(attrName, attrVal)

`attrName` is attribute name of profile and `attrVal` is attribute value to increment.
Checks params to be valid and calls server to update profile.Increments `attrName` property with `attrVal`.

## incrementBatch(attrMap)

`attrMap` is key value object where keys are attribute names and values are the values that attributes should be incremented with.






---
id: doc1
title: Personic SDK
sidebar_label: SDK
---

Class for creating Personic SDK.
For creating new SDK, call
```javascript
    let sdk = new SDK(appId)
```
With creating sdk, constructor also calls 
- [Profile](internals-sdk.md#Profile) and assigns returned object to `sdk.profile`
- [Request](internals-sdk.md#Request) and assigns returned object to `sdk.request`
- [Query](internals-sdk.md#Query) and assigns returned function to `sdk.query`
- [Event](internals-sdk.md#Event) and assigns returned object to `sdk.event`

## getAppId()

Returns application id,from which SDK created.

## getRequest()

Returns `this.request` object.

## getProfile()

Returns `this.profile`.

## getSDK()

Returns `SDK` config,which includes `version` and `name`.

## indentify(user_id)

Calls `this.profile.indentify()` with argument `user_id`.

## track(evn, evd)

`evn` is event name and `evd` event data.
Calls `this.event.track()` with `evn` and `evd`.

## execute(segment)

`segment` is segment object to run on profile,identified with sdk.
Calls `this.query()` with argument `segment`.

## profileIs(pc)

Calls [Segment](internals-sdk.md#Segment) with `pc`, which is profile condition object,which in its turn returns new segment object.

## behaviorIs(bc)

Calls [Segment](internals-sdk.md#Segment) with `null` and `bc`, which is behavior condition for querying events.This in its turn returns new behavior segment object.




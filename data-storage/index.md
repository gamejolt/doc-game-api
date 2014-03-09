# Data Store

[GameJolt API](../index.md) > Data store

## Description

A Cloud-based Data Storage storage system.
It is completely up to you what you use this for - the more inventive the better!

## URL Endpoint

```
/data-store/
```

## Requests

Name							| Description
---								| ---
[__Fetch__](/data-storage/data-store.md) | Fetches data from the data store.
[__Get keys__](/data-storage/get-keys.md)	| Fetches keys of data items from the data store.
[__Remove__](/data-storage/remove.md)		| Removes data items from the data store.
[__Set__](/data-storage/set.md)				| Sets data in the data store.
[__Update__](/data-storage/update.md)		| Updates data in the data store with various functions.

## Example uses

- Global Game Statistics
- User-Specific Statistics
- Private Messaging System
- User-Generated Content Hosting, e.g. Level Packs
- Turn Based Strategy Games
- Instant Replay System

## Remarks

- The Data-Storage is limited to `16MB` per key.

## Version history

Version		| Description
---			| ---
1.0			| First implementation
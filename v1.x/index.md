# GameJolt API

## Introduction

Calls to the system are done over the HTTP protocol, so nothing special is needed, and you can even test the service using a normal Web browser.

## Namespaces

These are the features the API supports right now:

Namespace											| Description
---													| ---
[__Data-store__](data-storage/index.md)				| Manipulate items in a cloud-based data storage.
[__Get Time__](get-time/index.md)					| Get the server's time.
[__Scores__](scores/index.md)						| Manipulate scores in score tables.
[__Sessions__](sessions/index.md)					| Setup sessions for your game.
[__Trophies__](trophies/index.md)					| Manage trophies for your game.
[__Users__](users/index.md)							| Access user-based features.
[__Batch__](batch/index.md)							| Merge multiple API calls into one request.

## Constructing requests

Every request consists of multiple parts.

This page instructs you how to construct the API requests: [Constructing Requests](construction.md)

## Multiple Formats

Requests can be sent in four different formats.

Check the [Formats](formats/index.md) page for more.
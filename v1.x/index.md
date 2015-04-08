# GameJolt API

## Introduction

Calls to the system are done over HTTP, so nothing special is needed, and you can test the service using a normal web browser.

## Namespaces

These are the features currently supported by the API:

Namespace											| Description
---													| ---
[__Data-store__](data-storage/index.md)				| Manipulate items in a cloud-based data storage.
[__Get Time__](get-time/index.md)					| Get the server's time.
[__Scores__](scores/index.md)						| Manipulate scores on score tables.
[__Sessions__](sessions/index.md)					| Set up sessions for your game.
[__Trophies__](trophies/index.md)					| Manage trophies for your game.
[__Users__](users/index.md)							| Access user-based features.
[__Batch__](batch/batch.md)							| Merge multiple API calls into one request.

## Constructing Requests

Every request consists of multiple parts.

This page shows you how to construct API requests: [Constructing Requests](construction.md)

## Multiple Formats

Requests can be sent in four different formats.

Check the [Formats](formats/index.md) page for more.

## Version history

These are the changes made to version 1.2 of the API: [__Version History__](version_history.md).
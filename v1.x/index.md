# GameJolt API

There are many libraries and plugins developed by the community already. Rather than write custom
code for interfacing with the Game API directly, most developers tend to use one of the already
written libraries.

[View libraries and plugins](https://gamejolt.com/game-api/doc/libraries).

If you do decide to write your own code for calling the Game API directly, then fear not, it's easy!
Calls to the system are done over HTTP or HTTPS, so nothing special is needed, and you can test the
service using a normal web browser.

## Namespaces

These are the features currently supported by the API:

| Namespace                                                      | Description                                     |
| -------------------------------------------------------------- | ----------------------------------------------- |
| [**Data-store**](https://gamejolt.com/game-api/doc/data-store) | Manipulate items in a cloud-based data storage. |
| [**Time**](https://gamejolt.com/game-api/doc/time)             | Get the server's time.                          |
| [**Scores**](https://gamejolt.com/game-api/doc/scores)         | Manipulate scores on score tables.              |
| [**Sessions**](https://gamejolt.com/game-api/doc/sessions)     | Set up sessions for your game.                  |
| [**Trophies**](https://gamejolt.com/game-api/doc/trophies)     | Manage trophies for your game.                  |
| [**Users**](https://gamejolt.com/game-api/doc/users)           | Access user-based features.                     |
| [**Friends**](https://gamejolt.com/game-api/doc/friends)       | List a user's friends.                          |
| [**Batch**](https://gamejolt.com/game-api/doc/batch)           | Merge multiple API calls into one request.      |

## Constructing Requests

Every request consists of multiple parts.

This page shows you how to construct API requests:
[Constructing Requests](https://gamejolt.com/game-api/doc/construction).

## Multiple Formats

Requests can be sent in four different formats.

Check the [Formats](https://gamejolt.com/game-api/doc/formats) page for more.

## Version history

These are the changes made to version 1.2 of the API:
[**Version History**](https://gamejolt.com/game-api/doc/version-history).

# API Errors

Every API response comes with a `success` field that indicates whether the request was a success.  
If the request was _not_ successful, the response also includes a `message` field, which indicates what went wrong with the request so you can debug it.

Each endpoint has its own set of errors than can occur when used incorrectly, and all endpoints share a set of basic request errors.

## Shared errors

These errors are shared by all endpoints.

| Affected parameter | Description                        | Error `message`                                           |
| ------------------ | ---------------------------------- | --------------------------------------------------------- |
| _`-none-`_         | Something unexpected has happened  | Unknown fatal error occurred.                             |
| `signature`        | No `signature` parameter passed in | You must enter a signature with your request.             |
| `signature`        | Invalid `signature`                | The signature you entered for the request is invalid.     |
| `game_id`          | Invalid/Empty `game_id`            | The game ID you passed in does not point to a valid game. |

## User request related errors

Certain endpoints can perform user scoped requests by passing the `username` and `user_token` parameters.  
When they do, these user related errors can occur:

| Affected parameter | Description | Error `message` |
| - | - | - |
| `username` / `user_token` | No user info passed in, but it is required _OR_ <br> `username` / `user_token` doesn't match any user | No such user with the credentials passed in could be found. |
| `username` / `user_token` | No user info passed in _OR_ <br> user with incorrect permissions passed to restricted data store key | This key has restrictions placed on it. Please pass in a restriction user with valid permissions. | 

## Endpoint specific errors

Each endpoint might have specific errors.  
To get information about these errors, visit the endpoint's API page.

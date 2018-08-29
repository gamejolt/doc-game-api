# Version History

## Version 1.2

- Default output format changed from `keypair` to `json`
- POST parameters must be signed. Check out [**URL Construction**](https://gamejolt.com/game-api/doc/construction)
- HTTPS support. We allow you to use HTTP as a fallback if you're engine doesn't support HTTPS.
- Domain name changed to `api.gamejolt.com`

### New URL Endpoints

- [**/friends/**](https://gamejolt.com/game-api/doc/friends)
- [**/time/**](https://gamejolt.com/game-api/doc/time)
- [**/batch/**](https://gamejolt.com/game-api/doc/batch)
- [**/scores/get-rank/**](https://gamejolt.com/game-api/doc/scores/get-rank)
- [**/trophies/remove-achieved**](https://gamejolt.com/game-api/doc/trophies/remove-achieved)
- [**/sessions/check/**](https://gamejolt.com/game-api/doc/sessions/check)

### Updated URL Endpoints

- [**/users/**](https://gamejolt.com/game-api/doc/users/fetch): The `developer_*` fields are sent for all users now, not just devs.
- [**/data-store/get-keys**](https://gamejolt.com/game-api/doc/data-store/get-keys):<br>Added `pattern` parameter.<br>Limited request to return up to 100 items.
- [**/scores/**](https://gamejolt.com/game-api/doc/scores):<br>
	Added `stored_timestamp` to the [fetch](https://gamejolt.com/game-api/doc/scores/fetch) request.<br>
	Added `better_than` and `worse_than` parameters to the [fetch](https://gamejolt.com/game-api/doc/scores/fetch) request<br>
	Added `guest` parameter to the [fetch](https://gamejolt.com/game-api/doc/scores/fetch) request

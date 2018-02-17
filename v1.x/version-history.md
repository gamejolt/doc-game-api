# Version History

## Version 1.2

### New URL Endpoints

- [**/friends/**](/friends/index.md)
- [**/time/**](/time/index.md)
- [**/batch/**](/batch/index.md)
- [**/scores/get-rank/**](/scores/index.md)
- [**/trophies/remove-achieved**](/trophies/index.md)
- [**/sessions/check/**](/sessions/check.md)

### Updated URL Endpoints

- [**/users/**](/users/fetch.md): The `developer_*` fields are sent for all users now, not just devs.
- [**/data-store/**](/data-store/index.md): Added restriction feature to the [/set/](/data-store/set.md) request.
- [**/data-store/**](/data-store/index.md): Added `pattern` parameter to the [/get-keys/](/data-store/get-keys.md) request.
- [**/data-store/**](/data-store/index.md): Limited [/get-keys/](/data-store/get-keys.md) to return up to 100 entries.
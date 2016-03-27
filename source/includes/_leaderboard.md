# Leaderboard

Leaderboards are cached on the server for 15 minutes to increase overall performance.

## Ranked Leaderboard

```shell
curl "https://api.rocketleaguestats.com/v1/leaderboard/ranked?playlist_id=10" \
  -H "Authorization: Bearer api_key"
```

Retrieves an array of 100 players sorted by their season 2 rank points.

### HTTP Request

`GET https://api.rocketleaguestats.com/v1/leaderboard/ranked`

### Query Parameters

Parameter | Description
--------- | ---------
playlist_id | A ranked playlist id, can be found in the [playlists data call](#playlists).

## Stat Leaderboard

```shell
curl "https://api.rocketleaguestats.com/v1/leaderboard/stat?type=wins" \
  -H "Authorization: Bearer api_key"
```

Retrieves an array of 100 players sorted by their specified stat amount.

Parameter | Description
--------- | ---------
type | `wins` / `goals` / `mvps` / `saves` / `shots` / `assists`

# Data

These calls should be used to get specific data which you should then store for later use.

## Platforms

```shell
curl "https://api.rocketleaguestats.com/v1/data/platforms" \
  -H "Authorization: api_key"
```

```json
[
  {
    "id": 1,
    "name": "Steam"
  },
  {
    "id": 2,
    "name": "PS4"
  },
  {
    "id": 3,
    "name": "XboxOne"
  }
]
```

This endpoint retrieves platform data.

### HTTP Request

`GET https://api.rocketleaguestats.com/v1/data/platforms`

## Seasons

```shell
curl "https://api.rocketleaguestats.com/v1/data/seasons" \
  -H "Authorization: api_key"
```

```json
[
  {
    "seasonId": 1,
    "startedOn": 1441836000,
    "endedOn": 1455058800
  },
  {
    "seasonId": 2,
    "startedOn": 1455058800,
    "endedOn": null
  }
]
```

This endpoint retrieves season data.

The `endedOn` property is `null` when a season hasn't ended yet.

### HTTP Request

`GET https://api.rocketleaguestats.com/v1/data/seasons`

## Playlists

```shell
curl "https://api.rocketleaguestats.com/v1/data/playlists" \
  -H "Authorization: api_key"
```

```json
[
  {
    "id": 1,
    "name": "Duel",
    "population": {
      "players": 929,
      "updatedAt": 1458929400
    }
  },
  {
    "id": 2,
    "name": "Doubles",
    "population": {
      "players": 7916,
      "updatedAt": 1458929400
    }
  },
  etc..
]
```

This endpoint retrieves playlist data.

At the moment only returns the following playlists:

 * Duel
 * Doubles
 * Standard
 * Chaos
 * Ranked Duel
 * Ranked Doubles
 * Ranked Solo Standard
 * Ranked Standard
 * Snow Day
 * Rocket Labs
 * Hoops
 * Rumble
 * Dropshot

### HTTP Request

`GET https://api.rocketleaguestats.com/v1/data/playlists`

## Tiers

```shell
curl "https://api.rocketleaguestats.com/v1/data/tiers" \
  -H "Authorization: api_key"
```

```json
[
  {
    "tierId": 0,
    "tierName": "Unranked"
  },
  {
    "tierId": 1,
    "tierName": "Prospect I"
  },
  etc..
]
```

This endpoint retrieves tier data.

Returns all season 5 tiers.

### HTTP Request

`GET https://api.rocketleaguestats.com/v1/data/tiers`

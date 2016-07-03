# Players

You can view an example of a single player response [here](#single-player).

**Extra field information:**

The `rankedSeasons` field works like this: `rankedSeasons.seasonId.playlistId`

If a particular `seasonId` does not exist, that means the player hasn't participated yet.

Field | Information
--------- | ---------
rankedSeasons>tier | Tier name can be found in the [tier data call](#tiers).
rankedSeasons>division | Division is 0 when tier is also 0 (Unranked).

**The following fields can be null:**

Field | When
--------- | ---------
avatar | An avatar could not be found for this user. Always for PS4 users and when Steam gives an invalid response to us, this is mostly fixed in the next platform-specific update.
rankedSeasons>rankPoints | Not played in this specific playlist.
rankedSeasons>matchesPlayed | Not played in this specific playlist.
rankedSeasons>tier | Not played in this specific playlist.
rankedSeasons>division | Not played in this specific playlist.
updatedInfoAt | When there have been no platform-specific updates for this user.

## Single Player

```shell
curl "https://api.rocketleaguestats.com/v1/player?unique_id=76561198033338223&platform_id=1" \
  -H "Authorization: Bearer api_key"
```

```json
{
  "uniqueId": "76561198033338223",
  "displayName": "Mike ' AeonLucid",
  "platform": {
    "id": 1,
    "name": "Steam"
  },
  "avatar": "http://cdn.akamai.steamstatic.com/steamcommunity/public/images/avatars/56/560e94689827bbdba66d34511de14e2442a5a786_full.jpg",
  "profileUrl": "https://rocketleaguestats.com/profile/Steam/76561198033338223",
  "signatureUrl": "http://signature.rocketleaguestats.com/normal/Steam/76561198033338223.png",
  "stats": {
    "wins": 177,
    "goals": 492,
    "mvps": 70,
    "saves": 252,
    "shots": 1050,
    "assists": 167
  },
  "rankedSeasons": {
    "1": {
      "10": {
        "rankPoints": 366
      },
      "11": {
        "rankPoints": 715
      },
      "12": {
        "rankPoints": 515
      },
      "13": {
        "rankPoints": 517
      }
    },
    "2": {
      "10": {
        "rankPoints": 557,
        "matchesPlayed": 15,
        "tier": 6,
        "division": 1
      },
      "11": {
        "rankPoints": 744,
        "matchesPlayed": 137,
        "tier": 8,
        "division": 1
      },
      "12": {
        "rankPoints": 708,
        "matchesPlayed": 44,
        "tier": 7,
        "division": 3
      },
      "13": {
        "rankPoints": 660,
        "matchesPlayed": 10,
        "tier": 7,
        "division": 1
      }
    }
  },
  "lastRequested": 1459095218,
  "createdAt": 1456424665,
  "updatedAt": 1459093964,
  "nextUpdateAt": 1459097564,
  "updatedInfoAt": 1459061514
}
```

This endpoint retrieves a single player. If it does not exist in our database, we will check if the player exist at Rocket League. If the Rocket League player does not exist we will return a 404 response.

A player exists will only be stored when he has one or more goals. This is our only way to check if a player is an actual player at the moment.

### HTTP Request

`GET https://api.rocketleaguestats.com/v1/player`

### Query Parameters

Parameter | Description
--------- | ---------
unique_id | Steam 64 ID / PSN Username / Xbox GamerTag or XUID
platform_id | The platform id. Ids can be found in the [platform data call](#platforms).

### Extra information regarding xbox

When you request an xbox user, the first request can be a bit slow when requesting by `gamertag`.

The API we use to receive `xuid` from `gamertag` is a bit slow.

If you received a player object when requesting by `gamertag`, you should use the `uniqueId` (`xuid`) field for future calls instead of the `gamertag`. This saves you at least **1 seconds** if the `xuid` is not cached but the user is stored.

<aside class="notice">
Did you know that <code>xuid</code> stands for <strong>Xbox User ID</strong>?
</aside>

## Batch Players

> This call works a bit different, you need to send a `POST` request with the header `Authorization: Bearer api_key`. Put the following in the body.

```json
[
    {"platformId":"1", "uniqueId":"76561198033338223"},
    {"platformId":"1", "uniqueId":"76561197981122126"},
    {"platformId":"3", "uniqueId":"Loubleezy"},
    {"platformId":"2", "uniqueId":"Wizwonk"}
]
```

> The response is a json array of all found players using the [player](#single-player) object.

You may only request 10 players at a time. If a player is not found, it will be excluded from the response.

### HTTP Request

`POST https://api.rocketleaguestats.com/v1/player/batch`

### Json Parameters

Parameter | Description
--------- | ---------
uniqueId | Steam 64 ID / PSN Username / Xbox GamerTag or XUID
platformId | The platform id. Ids can be found in the [platform data call](#platforms).

## Search Players

```shell
curl "https://api.rocketleaguestats.com/v1/search/players?display_name=Mike" \
  -H "Authorization: Bearer api_key"
```

> The `data` field contains an array of [player](#single-player) objects.

```json
{
  "page": 0,
  "results": 20,
  "totalResults": 91,
  "maxResultsPerPage": 20,
  "data": [

  ]
}
```

This endpoint retrieves multiple players. It will only search for players in our database, not all rocket league players.

### HTTP Request

`GET https://api.rocketleaguestats.com/v1/search/players`

### Query Parameters

Parameter | default | Description
--------- | --------- | ---------
display_name | None | A part of the display name you want to search for.
page | 0 | The page you want to receive.

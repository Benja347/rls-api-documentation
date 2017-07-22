---
title: RocketLeagueStats API Documentation

language_tabs:
  - shell

toc_footers:
  - <a href='https://developers.rocketleaguestats.com'>Request an API key</a>
  - <a href='https://github.com/RocketLeagueStats/rls-api-documentation'>Documentation Source</a>

includes:
  - libraries
  - authentication
  - data
  - players
  - leaderboard
  - errors

search: true
---

# Introduction

Welcome to the RocketLeagueStats API Documentation.

You may use this API to create applications that require Rocket League data once you have obtained an API key. We are working on official RLS libraries to consume the HTTP API.

All libraries can be found [here](#libraries).

If you are working on an unofficial library, please let us know and we will make sure to list it in the documentation.
You may also add them yourself by creating a pull request to this [repository](https://github.com/RocketLeagueStats/rls-api-documentation).

<aside class="notice">
You need to have an API key to use this API.<br>
Click <a href='https://developers.rocketleaguestats.com'>here</a> to request a key, you can get started within 5 minutes.
</aside>

## API Versioning

We use API versioning to make sure that we don't break applications.

There is just one API version at the moment, but `v2` may appear in the future when needed for breaking changes.

## API v1

This API version will only receive backwards compatible updates based on feedback, such as:
  * A new endpoint.
  * A new query parameter with a default option or optional.
  * Performance improvements.

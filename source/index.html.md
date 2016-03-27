---
title: RocketLeagueStats API Documentation

language_tabs:
  - shell

toc_footers:
  - <a href='mailto:aeonlucid@outlook.com'>Request an API key</a>
  - <a href='https://github.com/RocketLeagueStats/ApiDocumentation'>Documentation Source</a>

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

You may use this API to create applications that require Rocket League data once you have obtained an API key.

We are working on official RLS libraries to access this API, and you are allowed to contribute.

All official libraries can be found [here](#libraries).

If you are working on an unofficial library, please let us know and we will make sure to list it in the documentation.

You may also add them yourself by creating a pull request.

<aside class="notice">
It is not possible to register for an API key yet, you'll have to ask for one manually.<br>
There will be a developers portal available really soon.<br>
You can find ways to contact me <a href='https://rocketleaguestats.com/contact'>here</a>.
</aside>

## API Versioning

We use API versioning to make sure that we don't break applications.

There is just one API version at the moment, but `v2` may appear in the future when needed for experimental use.

## API v1

This API version will only receive backwards compatible updates based on feedback.

Like:

  * A new endpoint
  * A new query parameter with a default option or optional
  * Performance improvements

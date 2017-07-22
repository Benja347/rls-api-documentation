# Authentication

> To authorize, use this code:

```shell
curl "https://api.rocketleaguestats.com/v1/data/platforms" -H "Authorization: <api_key>"
```

```shell
curl "https://api.rocketleaguestats.com/v1/data/platforms?apikey=<api_key>"
```

> Make sure to replace `api_key` with your API key and not include <>.

We use API keys to allow access to the API. You can register for an API key at our [developers](https://developers.rocketleaguestats.com) website.

The API expects an API key in all requests. If not included the API will respond with a **401 Unauthorized** error.

We accept an API key either through the "Authorization" header or "apikey" GET query. Please use the header if it is possible to do so.

`Authorization: <api_key>` or `<request>?apikey=<api_key>`

<aside class="notice">
You must replace <code>&lt;api_key&gt;</code> with your personal API key.
</aside>

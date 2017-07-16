# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" -H "Authorization: api_key"
```

> Make sure to replace `api_key` with your API key.

We use API keys to allow access to the API. You can register for an API key at our [developers](https://developers.rocketleaguestats.com) website.

The API expects an API key in all requests. If not included the API will respond with a **401 Unauthorized** error.

`Authorization: api_key`

<aside class="notice">
You must replace <code>api_key</code> with your personal API key.
</aside>

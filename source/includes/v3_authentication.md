# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "https://cbe.vdhelm.com/api/v3/<resource>"
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
```

> Make sure to replace `FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv` with your API key.

The VDH CBE tool uses bearer authentication to authenticate requests. Contact your VDH CBE tool representative to receive a new CBE tool API access token.

In order to authenticate properly, please put <code>Authorization: Bearer &lt;API Access Token&gt;</code> in the request header. The CBE tool expects for the API access token to be included in all API requests to the server in a header that looks like the following:

`Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv`

<aside class="warning">
You must replace <code><strong>FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv</strong></code> with your personal API key.
</aside>

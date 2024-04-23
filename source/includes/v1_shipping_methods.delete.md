## Delete a Specific Shipping Method

```shell
curl "https://crossborder.omniship.eu/api/v2/shipping_methods/19"
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
```

> The above command returns JSON structured like this:

```
HTTP/1.1 204 NO CONTENT
Content-Type:application/json;charset=UTF-8
```
```json
[]
```

This endpoint deletes a specific Shipping Method.

### HTTP Request

<span class="http-verb get">DELETE</span> `https://crossborder.omniship.eu/api/v2/shipping_methods/<ID>`

### URL Parameters

| Parameter | Description                   |
|-----------|-------------------------------|
| ID        | The ID of the Shipping Method |

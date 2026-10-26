## List all Shipping Methods


```shell
curl "https://crossborder.omniship.eu/api/v3/shipping_methods"
  -H "Authorization: Bearer FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
```

> The above command returns JSON structured like this:

```
HTTP/1.1 200 OK
Content-Type:application/json;charset=UTF-8
```
```json
{
  "data": [
    {
			"name": "DEDHL",
			"address": {
				"company": "DHL Bochum",
				"line_1": "Opelring 1",
				"city": "Bochum",
				"country": "DE",
				"country_full": "Germany",
				"is_pickup": false
			},
			"customer": "Acme"
		},
		{
			"name": "DEDP",
			"address": {
				"company": "Deutsche Post  Essen",
				"line_1": "Daniel-Eckhardt-Straße 7",
				"city": "Essen",
				"country": "DE",
				"country_full": "Germany",
				"is_pickup": false
			},
			"customer": "Acme"
		},
    {"..."},
    {"..."}
	]
}
```

This endpoint retrieves all Shipping Methods of your account.

### HTTP Request

<span class="http-verb get">GET</span> `/api/v3/shipping_methods`


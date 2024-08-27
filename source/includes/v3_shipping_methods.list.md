## List all Shipping Methods


```shell
curl "https://cbe.vdhelm.com/api/v3/shipping_methods"
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
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
			"customer": "Acme",
			"print_label": false
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
			"customer": "Acme",
			"print_label": false
		},
    {"..."},
    {"..."}
	]
}
```

This endpoint retrieves all Shipping Methods.

### HTTP Request

<span class="http-verb get">GET</span> `/api/v3/shipping_methods`


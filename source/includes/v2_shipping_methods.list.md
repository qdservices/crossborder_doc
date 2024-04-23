## List all Shipping Methods


```shell
curl "https://crossborder.omniship.eu/api/v2/shipping_methods"
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
      "id": 7,
      "name": "MONDIAL RELAY",
      "address": {
        "id": 9515,
        "name": null,
        "company": "MONDIAL RELAY",
        "line_1": "AVENUE ANTOINE PINAY",
        "line_2": "SORTING CENTRE 5",
        "postal_code": "59510",
        "city": "HEM",
        "state": null,
        "country": "FR",
        "addressable_id": null,
        "addressable_type": null,
        "type_id": null,
        "original_id": null,
        "created_by": 1,
        "created_at": "2022-02-10T01:08:09.000000Z",
        "updated_at": "2022-02-10T01:08:09.000000Z"
      },
      "customer": "Global Freight Services"
    },
    {
      "id": 8,
      "name": "Colisprive",
      "address": {
        "id": 9516,
        "name": null,
        "company": "Colisprive",
        "line_1": "RUE GEOERGES LEFEBVRE",
        "line_2": "HUB COLIS PRIVE",
        "postal_code": "62117",
        "city": "BREBIERES",
        "state": null,
        "country": "FR",
        "addressable_id": null,
        "addressable_type": null,
        "type_id": null,
        "original_id": null,
        "created_by": 1,
        "created_at": "2022-02-10T01:09:12.000000Z",
        "updated_at": "2022-02-10T01:09:12.000000Z"
      },
      "customer": "Global Freight Services"
    },
    {
      "id": 19,
      "name": "DHLAMS",
      "address": {
        "id": 9597,
        "name": null,
        "company": "DHL Amsterdam",
        "line_1": "Kappstadweg 25",
        "line_2": null,
        "postal_code": "1047 HG",
        "city": "AMSTERDAM",
        "state": null,
        "country": "NL",
        "addressable_id": null,
        "addressable_type": null,
        "type_id": null,
        "original_id": null,
        "created_by": 66,
        "created_at": "2022-02-21T14:19:37.000000Z",
        "updated_at": "2022-02-21T14:19:37.000000Z"
      },
      "customer": "Global Freight Services"
    },
    {"..."},
    {"..."}
	]
}
```

This endpoint retrieves all Shipping Methods.

### HTTP Request

<span class="http-verb get">GET</span> `https://crossborder.omniship.eu/api/v2/shipping_methods`


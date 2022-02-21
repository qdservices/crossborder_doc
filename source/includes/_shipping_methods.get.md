## Retrieve a Specific Shipping Method

```shell
curl "https://crossborder.omniship.eu/api/v2/shipping_methods/19"
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
}
```

This endpoint retrieves a specific Shipping Method.

### HTTP Request

<span class="http-verb get">GET</span> `https://crossborder.omniship.eu/api/v2/shipping_methods/<ID>`

### URL Parameters

| Parameter | Description                   |
|-----------|-------------------------------|
| ID        | The ID of the Shipping Method |

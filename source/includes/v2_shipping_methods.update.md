## Update a Shipping Method

```shell
curl "https://crossborder.omniship.eu/api/v2/shipping_methods/19"
  -X PATCH
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  -d '{
        "name": "Post Delivery Rotterdam",
        "address": {
          "postal_code": "1092 TE"
        }
      }'
```

> The above command returns JSON structured like this:

```
HTTP/1.1 200 OK
Content-Type:application/json;charset=UTF-8
```
```json
{
  "id": 19,
  "name": "Post Delivery Rotterdam",
  "address": {
    "id": 9596,
    "name": null,
    "company": "DHL Amsterdam",
    "line_1": "Kappstadweg 25",
    "line_2": null,
    "postal_code": "1092 TE",
    "city": "AMSTERDAM",
    "state": null,
    "country": "NL",
    "addressable_id": null,
    "addressable_type": null,
    "type_id": null,
    "original_id": null,
    "created_by": 66,
    "created_at": "2022-02-21T14:17:34.000000Z",
    "updated_at": "2022-02-21T14:17:34.000000Z"
  },
  "customer": "Global Freight Services"
}
```

This endpoint updates a Shipping Method in OMNISHIP cross border. This is helpful if you want to change the name, or you want to change the address of a Shipping Method.

### HTTP Request

<span class="http-verb patch">PATCH</span> `https://crossborder.omniship.eu/api/v2/shipping_methods/<ID>`

### URL Parameters

| Parameter | Description                             |
|-----------|-----------------------------------------|
| ID        | The ID of the Shipping Method to update |

### Arguments

| Attribute | Type                             | Description                                                         |
|-----------|----------------------------------|---------------------------------------------------------------------|
| name      | <span class="type">string</span> | Unique code to identify a Shipping Method.                          |
| address   | <span class=type>Object</span>   | Address associated with the shipping method.                        |

## Create a Shipping Method

```shell
curl "https://crossborder.omniship.eu/api/v2/shipping_methods"
  -X POST
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  -d '{
        "name": "DHLAMS",
        "address": {
          "company": "DHL Amsterdam",
          "line_1": "Kappstadweg 25",
          "postal_code": "1047 HG",
          "city": "AMSTERDAM",
          "country": "NL"
	      }
      }'
```

> The above command returns JSON structured like this:

```
HTTP/1.1 201 Created
Content-Type:application/json;charset=UTF-8
```

```json
{
  "id": 19,
  "name": "DHLAMS",
  "address": {
    "id": 9596,
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
    "created_at": "2022-02-21T14:17:34.000000Z",
    "updated_at": "2022-02-21T14:17:34.000000Z"
  },
  "customer": "Global Freight Services"
}
```

This endpoint creates a new Shipping Method in OMNISHIP cross border. 

### HTTP Request

<span class="http-verb post">POST</span> `https://crossborder.omniship.eu/api/v2/shipping_methods`

### Arguments

| Attribute | Type                             | Description                                                                                    |
|-----------|----------------------------------|------------------------------------------------------------------------------------------------|
| name      | <span class="type">string</span> | <span class="required">required</span> Unique code to identify a Shipping Method.              |
| address   | <span class="type">object</span> | <span class="required">required</span> The Address object associated with the shipping Method. |

### Address Parameters

| Attribute     | Type                             | Description                                                                                                          |
|---------------|----------------------------------|----------------------------------------------------------------------------------------------------------------------|
| `name`        | <span class="type">string</span> | <span class="optional">optional</span> Contact name associated with the address. Maximum 35 characters.              |
| `company`     | <span class="type">string</span> | <span class="required">required</span> Company name associated with the address. Maximum 70 characters.              |
| `line_1`      | <span class="type">string</span> | <span class="required">required</span> Address Line 1 associated with the address.                                   |
| `line_2`      | <span class="type">string</span> | <span class="optional">optional</span> Address Line 2 associated with the address.                                   |
| `postal_code` | <span class="type">string</span> | <span class="optional">optional</span> Postal Code associated with the address.                                      |
| `city`        | <span class="type">string</span> | <span class="required">required</span> City associated with the address.                                             |
| `country`     | <span class="type">string</span> | <span class="required">required</span> Country code associated with the address. (needs to be ISO 3166 2-char code). |

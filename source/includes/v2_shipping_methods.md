# Shipping Methods

> Example:

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

A Shipping Method represents the destination that can be assigned to parcels by using the `name` attribute in the pre-alert upload.

| Attribute | Type                            | Description                                                    |
|-----------|---------------------------------|----------------------------------------------------------------|
| `id`      | <span class=type>integer</span> | Unique ID of a Shipping Method. This is used as an identifier. |
| `name`    | <span class=type>string</span>  | Unique code to identify a Shipping Method.                     |
| `address` | <span class=type>Object</span>  | Address associated with the shipping method.                   |








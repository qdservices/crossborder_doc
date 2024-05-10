# Shipping Methods

> Example:

```json
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
}
    
```

A Shipping Method represents the destination that can be assigned to parcels by using the `name` attribute in the pre-alert upload.

| Attribute     | Type                            | Description                                                             |
|---------------|---------------------------------|-------------------------------------------------------------------------|
| `id`          | <span class=type>integer</span> | Unique ID of a Shipping Method. This is used as an identifier.          |
| `name`        | <span class=type>string</span>  | Unique code to identify a Shipping Method.                              |
| `address`     | <span class=type>Object</span>  | Address associated with the Shipping Method.                            |
| `customer`    | <span class=type>string</span>  | Customer associated with the Shipping Method.                           |
| `print_label` | <span class=type>boolean</span> | Indicates if final mile relabeling is enabled for this Shipping Method. |








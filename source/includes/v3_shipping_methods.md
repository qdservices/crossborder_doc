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
  "customer": "Acme"
}
    
```

A Shipping Method represents the destination that can be assigned to parcels by using the `name` attribute as `shippingMethod` when adding a parcel. A parcel can only use a shipping method whose pricing agreement is valid today.

| Attribute     | Type                            | Description                                                             |
|---------------|---------------------------------|-------------------------------------------------------------------------|
| `name`        | <span class=type>string</span>  | Unique code to identify a Shipping Method.                              |
| `address`     | <span class=type>Object</span>  | Address associated with the Shipping Method: `company`, `line_1`, `city`, `country` (Alpha 2), `country_full` and `is_pickup`. |
| `customer`    | <span class=type>string</span>  | Customer associated with the Shipping Method.                           |








# Waybills

> Example:

```json
{
  "customer_code": "GFS",
  "waybill_type": "air",
  "waybill_number": "784-65428952",
  "reference": 71577,
  "weight_unit": "grams",
  "pre_alert_rows": [
    {
      "parcel_id": null,
      "mawb_nr": null,
      "seller_name": null,
      "seller_ioss_nr": null,
      "seller_street": null,
      "seller_city": null,
      "seller_country_code": null,
      "transaction_type": null,
      "package_barcode": null,
      "buyer_street": null,
      "buyer_name": null,
      "buyer_eori": null,
      "buyer_street": null,
      "buyer_city": null,
      "buyer_country_code": null,
      "item_hs_code": null,
      "quantity": null,
      "weight": null,
      "item_hs_code": 0,
      "goods_description": null,
      "invoice_currency": null,
      "invoice_amount": null,
      "charges_currency": null,
      "other_charges": null
    },
    {"..."},
    {"..."}
  ]
}
    
```

A waybill is a document that represents the contents of a shipment ready for transport. It details
the exact quantity, price and delivery details of the individual packages. 
Perform the simple operations mentioned below to create and manage your Waybill pre alert.

Attribute | Type | Description
--------- | ------- | -----------
`customer_code` | <span class=type>string</span> | Unique ID of a customer. This is used as an identifier.
`waybill_type` | <span class=type>string</span> | The type of waybill. Valid values are ('air', 'road', 'train', 'sea', 'other').
`waybill_number` | <span class=type>string</span> | Identifies the total shipment. If waybill type is 'air' a validation check is done on the format of the waybill_number given.
`reference` | <span class=type>string</span> | Unique identifier of the shipment. Usually an id of the original system where the pre-alert was uploaded.
`weight_unit` | <span class=type>string</span> | Unit of weight used in the pre-alert. Valid values are ('grams', 'kilograms')
`pre_alert_rows` | <span class=type>array</span> | A pre alert contains multiple pre_alert rows. Each pre alert row contains `parcel_id`,`mawb_nr`,`seller_name`,`seller_ioss_nr`,`seller_street`,`seller_city`,`seller_country_code`,`transaction_type`,`package_barcode`,`buyer_street`,`buyer_name`,`buyer_eori`,`buyer_street`,`buyer_city`,`buyer_country_code`,`item_hs_code`,`quantity`,`weight`,`item_hs_code`,`goods_description`,`invoice_currency`,`invoice_amount`,`charges_currency`,`other_charges`








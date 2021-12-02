## Create a Waybill

```shell
curl "https://crossborder.omniship.eu/api/v1/waybills"
  -X POST
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  -d '{
        "customer_code": "GFS",
        "waybill_type": "air",
        "waybill_number": "784-65428952",
        "reference": 71577,
        "weight_unit": "grams",
        "pre_alert_rows": [
            {
              "mawb_nr": "235-23549621",
              "parcel_id": "WBDEM100073974019U",
              "package_barcode": "226003462045", 
              "seller_name": "Wildberries LLC",
              "seller_ioss_nr": "IM2760006126",
              "seller_street": "Koledino village 6 building 1",
              "seller_city": "Podolsk",
              "seller_country_code": "RU",
              "transaction_type": "B2C",
              "buyer_street": "Berlin",
              "buyer_name": "Marco Polo",
              "buyer_eori": null,
              "buyer_street": "Engelbertring 1",
              "buyer_city": "Arnsberg",
              "buyer_country_code": "59755",
              "quantity": "1",
              "weight": "2.29",
              "item_hs_code": "950300",
              "goods_description": "Book",
              "invoice_currency": "EUR",
              "invoice_amount": "7.23",
              "charges_currency": null,
              "other_charges": null
            },
            {"..."},
            {"..."}
        ],
      }'
```

> The above command returns JSON structured like this:

```
HTTP/1.1 200 Created
Content-Type:application/json;charset=UTF-8
```

```json
{
  "id": 3263,
  "number": "784-65428961",
  "reference": 71583,
  "total_weight": null,
  "total_bags": null,
  "status": "pre_upload",
  "status_changed": "2021-06-29T11:41:18.000000Z",
  "status_changed_human": "1 second ago",
  "inbound": 0,
  "outbound": 0,
  "job_state": "uploading",
  "date_received": "2021-06-29T11:41:18.000000Z",
  "updated_at": "2021-06-29T11:41:18.000000Z",
  "customer": "OminiShip",
  "bags": [],
  "in_container": 0,
  "total": 1,
  "container_count": 0,
  "airline": {
    "id": 196,
    "prefix": "784",
    "code": "CZ",
    "name": "China Southern Airlines "
  }
}
```

This endpoint creates a new Waybill pre alert in OMNISHIP cross border. 

### HTTP Request

<span class="http-verb post">POST</span> `https://crossborder.omniship.eu/api/v1/waybills`

### Arguments

Attribute | Type | Description
--------- | ----------- | ----------
customer_code | <span class="type">string</span> | <span class="required">required</span> The unique customer code. This code should reflect a customer code in the database.
waybill_type | <span class="type">string</span> | <span class="required">required</span> The type of waybill. Valid values are `air`, `road`, `train`, `other`
waybill_number | <span class="type">string</span> | <span class="required">required</span> Unique number of the waybill. This number cannot already exist in the database for the same customer.
reference | <span class="type">string</span> | <span class="required">required</span> Unique reference usually the ID of the external system where shipment is uploaded from.
weight_unit | <span class="type">string</span> | <span class="optional">optional</span> The weight unit used for the weights in the pre-alert. Valid values are `grams`, `kilograms`. When omitted or empty the default customer weight unit will be used.
pre_alert_rows | <span class="type">array</span> | <span class="required">required</span> Line with details of the specific shipment. Each line must contain `order_number`, `bag_grade`, `country_code`.

### Pre Alert Row Parameters

Attribute | Type | Description
--------- | ------- | ---------
`mawb_nr` | <span class="type">string</span> | <span class="required">required</span> Unique number of the waybill. This number cannot already exist in the database for the same customer.
`parcel_id` | <span class="type">string</span> | <span class="required">required</span> Parcel ID for the shipment line.
`package_barcode` | <span class="type">string</span> | <span class="required">required</span> Package Barcode for the shipment line.
`seller_name` | <span class="type">string</span> | <span class="optional">optional</span> Name of the company of the package consignee.
`seller_ioss_nr` | <span class="type">string</span> | <span class="optional">optional</span> IOSS number is required by distance sellers and marketplaces in order to sell goods to buyers in the EU under the IOSS scheme.
`seller_street` | <span class="type">number</span> | <span class="optional">required</span> Street address of the of the package consignee.
`seller_city` | <span class="type">string</span> | <span class="optional">optional</span> City or town of the of the package consignee.
`seller_country_code` | <span class="type">string</span> | <span class="optional">optional</span> Country code of the of the package consignee. (needs to be ISO 3166 2-char code).
`transaction_type` | <span class="type">string</span> | <span class="optional">optional</span> Transaction type (B2B or B2C) of the package.
`package_barcode` | <span class="type">string</span> | <span class="optional">optional</span> Barcode of the package. Usually the final mile carrier barcode.
`buyer_street` | <span class="type">string</span> | <span class="optional">optional</span> Street address of the of the package consignee.
`buyer_name` | <span class="type">string</span> | <span class="optional">optional</span> Name of the of the package buyer.
`buyer_eori` | <span class="type">string</span> | <span class="optional">optional</span> Eori is the European Union registration and identification number used in all customs procedures performed by economic operators.
`buyer_street` | <span class="type">string</span> | <span class="optional">optional</span> Street address of the package buyer.
`buyer_city` | <span class="type">string</span> | <span class="optional">optional</span> City or town of the of the package buyer.
`buyer_country_code` | <span class="type">string</span> | <span class="required">required</span> Country code of the package buyer. (needs to be ISO 3166 2-char code).
`item_hs_code` | <span class="type">string</span> | <span class="optional">optional</span> HS code of the of the item(s) in the package.
`quantity` | <span class="type">string</span> | <span class="optional">optional</span> Quantity of the of the item(s) in the package.
`weight` | <span class="type">string</span> | <span class="optional">optional</span> Weight of the of the item(s) in the package.
`goods_description` | <span class="type">string</span> | <span class="optional">optional</span> Description of the of the item(s) in the package.
`invoice_currency` | <span class="type">string</span> | <span class="optional">optional</span> Currency of the value of the item(s) in the package.
`invoice_amount` | <span class="type">string</span> | <span class="optional">optional</span> Amount of the value of the item(s) in the package.
`charges_currency` | <span class="type">number</span> | <span class="optional">optional</span> Charges Currency of the value of the item(s) in the package.
`other_charges` | <span class="type">string</span> | <span class="optional">optional</span> Other charges of the value of the item(s) in the package.

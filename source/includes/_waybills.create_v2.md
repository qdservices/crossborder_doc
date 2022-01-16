## Create a Waybill

```shell
curl "https://crossborder.omniship.eu/api/v2/waybills"
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
              "parcel_id": "WBDEM100073974019U",
              "package_barcode": "226003462045", 
              "seller_name": "Wildberries LLC",
              "seller_ioss_nr": "IM2760006126",
              "seller_street": "Koledino village 6 building 1",
              "seller_zipcode": "108823",
              "seller_city": "Podolsk",
              "seller_country_code": "RU",
              "transaction_type": "B2C",
              "buyer_name": "Marco Polo",
              "buyer_eori": null,
              "buyer_street": "Engelbertring 1",
              "buyer_zipcode": "59755",
              "buyer_city": "Berlin",
              "buyer_country_code": "DE",
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
  "customer": "Global Freight System",
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

<span class="http-verb post">POST</span> `https://crossborder.omniship.eu/api/v2/waybills`

### Arguments

Attribute | Type | Description
--------- | ----------- | ----------
customer_code | <span class="type">string</span> | <span class="required">required</span> The unique customer code. This code should reflect a customer code in the database.
waybill_type | <span class="type">string</span> | <span class="required">required</span> The type of waybill. Valid values are `air`, `road`, `train`, `other`
waybill_number | <span class="type">string</span> | <span class="required">required</span> Unique number of the waybill. This number cannot already exist in the database for the same customer.
reference | <span class="type">string</span> | <span class="required">required</span> Unique reference usually the ID of the external system where shipment is uploaded from.
weight_unit | <span class="type">string</span> | <span class="optional">optional</span> The weight unit used for the weights in the pre-alert. Valid values are `grams`, `kilograms`. When omitted or empty the default customer weight unit will be used.
pre_alert_rows | <span class="type">array</span> | <span class="required">required</span> Line with details of the specific shipment. Each line must contain `parcel_id`, `package_barcode`, `seller_name`, `seller_ioss_nr`, `seller_street`, `seller_city`, `seller_country_code`, `transaction_type`, `buyer_name`, `buyer_street`, `buyer_city`, `buyer_country_code`, `item_hs_code`, `quantity`, `weight`, `item_hs_code`, `goods_description`, `invoice_currency`, `invoice_amount`.

### Pre Alert Row Parameters

Attribute | Type | Description
--------- | ------- | ---------
`parcel_id` | <span class="type">string</span> | <span class="required">required</span> Barcode of the package. Usually the final mile carrier barcode. Maximum 35 characters.
`package_barcode` | <span class="type">string</span> | <span class="required">required</span> Package Barcode for the shipment line.
`seller_name` | <span class="type">string</span> | <span class="required">required</span> (Company) name of the company of the seller. Maximum 70 characters.
`seller_ioss_nr` | <span class="type">string</span> | <span class="required">required</span> IOSS number of the seller. 12 Characters and must start with IM.
`seller_street` | <span class="type">number</span> | <span class="required">required</span> Street address of the of the seller. Maximum 70 characters.
`seller_zipcode` | <span class="type">number</span> | <span class="optional">optional</span> Zip code of the of the seller.
`seller_city` | <span class="type">string</span> | <span class="required">required</span> City or town of the of the seller. Maximum 35 characters
`seller_country_code` | <span class="type">string</span> | <span class="required">required</span> Country code of the of the seller. (needs to be ISO 3166 2-char code).
`transaction_type` | <span class="type">string</span> | <span class="required">required</span> Transaction type (B2C or C2C) of the package.
`buyer_name` | <span class="type">string</span> | <span class="required">required</span> Name of the of the package consignee. Maximum 70 characters.
`buyer_eori` | <span class="type">string</span> | <span class="optional">optional</span> Eori is the European Union registration and identification number used in all customs procedures performed by economic operators. Maximum 17 characters
`buyer_zipcode` | <span class="type">string</span> | <span class="optional">optional</span> Zip code of the of the package consignee.
`buyer_street` | <span class="type">string</span> | <span class="required">required</span> Street address of the package consignee. Maximum 70 characters.
`buyer_city` | <span class="type">string</span> | <span class="required">required</span> City or town of the of the package consignee. Maximum 35 characters
`buyer_country_code` | <span class="type">string</span> | <span class="required">required</span> Country code of the package consignee. (needs to be ISO 3166 2-char code).
`item_hs_code` | <span class="type">string</span> | <span class="required">required</span> HS code of the of the item(s) in the package. Must be included on the [152 GS-Code list](https://www.belastingdienst.nl/codeboek_sagitta/huidig/html/tabel-codeboek%2C%20onderdeel%20e-commerce-152.html) and not prohibited.
`quantity` | <span class="type">string</span> | <span class="required">required</span> Quantity of the of the item(s) in the package.
`weight` | <span class="type">string</span> | <span class="required">required</span> Weight of the of the item(s) in the package.
`goods_description` | <span class="type">string</span> | <span class="required">required</span> Description of the of the item(s) in the package. Maximum 512 characters.
`invoice_currency` | <span class="type">string</span> | <span class="required">required</span> Currency of the value of the item(s) in the package. 3 letter currency code.
`invoice_amount` | <span class="type">string</span> | <span class="required">required</span> Amount of the value of the item(s) in the package.
`charges_currency` | <span class="type">number</span> | <span class="optional">optional</span> Charges Currency of the value of the item(s) in the package.
`other_charges` | <span class="type">string</span> | <span class="optional">optional</span> Other charges of the value of the item(s) in the package.

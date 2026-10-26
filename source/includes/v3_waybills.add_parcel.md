## Create and add a Parcel to a Waybill

```shell
curl "https://crossborder.omniship.eu/api/v3/waybills/4dcdea18-afb4-4c38-8541-9b83056a5667/parcels"
  -X POST
  -H "Authorization: Bearer FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  -d '{
	"transactionType": "B2C",
	"finalMileTrackingNumber": "1Z1V510W6898496192",
	"bigBagBarcode": "DE202301009-001",
	"sellerDetails": {
		"name": "Shenzhen Duhua technology Co., LTD",
		"street": "Room 402, Building 2, Building B, No. 23 Wanli Road, Henggang Street",
		"zipcode": "51800",
		"city": "Shenzen",
		"countryCode": "CN",
		"iossNumber": "1ZoTwmSCWm/iQY3utehUVQ=="
	},
	"buyerDetails": {
		"name": "juan luis garcia azpitarte",
		"street": "pol. ind. calle tinajuela 39 18657 niguelas Granada Spain",
		"zipcode": "18657",
		"city": "Niguelas",
		"countryCode": "ES"
	},
	"packageWeight": 23.5,
	"items": [{
		"hsCode": "950691",
		"description": "DUMBBELL SET",
		"quantity": 4,
		"weight": 22.95,
		"invoiceCurrency": "EUR",
		"invoiceAmount": 119.99,
		"freightValue": 3.30,
		"sku": "DB-SET-4X5",
		"manufacturerProductId": "MPN-4471",
		"standardProductId": "8712345678906"
	}],
	"shippingMethod": "DPD145"
  }'
```

> The above command returns JSON structured like this:

```
HTTP/1.1 201 Created
Content-Type:application/json;charset=UTF-8
```

```json
{
  "data": {
    "id": "711277a6-239b-4992-ab4a-cac276a27e21",
    "state": "pre_upload",
    "waybillId": "1cb3480a-86d3-44f2-a36d-f082e501fd37",
    "waybillNumber": "112-60318215",
    "finalMileTrackingNumber": "1Z1V510W6898496192",
    "bigBagBarcode": "DE202301009-001",
    "shippingMethod": "DPD145",
    "transactionType": "B2C",
    "invoiceNumber": null,
    "sellerDetails": {
      "name": "Shenzhen Duhua technology Co., LTD",
      "street": "Room 402, Building 2, Building B, No. 23 Wanli Road, Henggang Street",
      "zipcode": "51800",
      "city": "Shenzen",
      "countryCode": "CN"
    },
    "buyerDetails": {
      "name": "juan luis garcia azpitarte",
      "street": "pol. ind. calle tinajuela 39 18657 niguelas Granada Spain",
      "zipcode": "18657",
      "city": "Niguelas",
      "countryCode": "ES"
    },
    "packageWeight": null,
    "items": [
      {
        "hsCode": "950691",
        "description": "DUMBBELL SET",
        "quantity": "4",
        "weight": 22.95,
        "invoiceCurrency": "EUR",
        "invoiceAmount": "119.99",
        "freightValue": "3.30",
        "sku": "DB-SET-4X5",
        "manufacturerProductId": "MPN-4471",
        "standardProductId": "8712345678906"
      }
    ]
  }
}
```

This endpoint creates a new Parcel and adds it to the given Waybill pre alert in the <span style="font-weight: bold">ALL<span style="color: #d83636;">IN</span>E</span> cross border system. Each item becomes one declaration line.

Sending a parcel again with the same `finalMileTrackingNumber` and `bigBagBarcode` replaces it: its items are overwritten in order, and items left out are removed. The response `packageWeight` stays `null` until the waybill is confirmed.

### HTTP Request

<span class="http-verb post">POST</span> `/api/v3/waybills/<ID>/parcels`

### URL Parameters

| Parameter | Description                                                                                                                                                                                                   |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID        | The ID of the <span class="object">Waybill</span> for which a <span class="object">Parcel</span> needs added. The ID was given at creation of the waybill and was either generated or is the given reference. |

### Arguments

| Attribute               | Type                             | Description |
|-------------------------|----------------------------------|-------------|
| transactionType         | <span class="type">string</span> | <span class="required">required</span> Type of transaction. Valid values are `B2C` and `H2C` (high value e-commerce, above €150). |
| invoiceNumber           | <span class="type">string</span> | <span class="optional">optional</span> Invoice number of the parcel, max 70 characters. <span class="required_if">Required if</span> `transactionType` is `H2C` and the parcel is worth more than €150. |
| finalMileTrackingNumber | <span class="type">string</span> | <span class="required">required</span> Tracking number of the final mile parcel. Max 35 characters: letters, digits, `-` and `/`. |
| bigBagBarcode           | <span class="type">string</span> | <span class="required">required</span> Barcode of the bag/box/unit containing the parcel(s). If there is only one parcel and no containing unit with a barcode, the finalMileTrackingNumber can be used instead. All parcels in one bag must use the same shipping method, unless your account allows mixed bags. |
| sellerDetails           | <span class="type">object</span> | <span class="required">required</span> <span class="object">Address</span> object that should be used as sender address. |
| buyerDetails            | <span class="type">object</span> | <span class="required">required</span> <span class="object">Address</span> object that should be used as buyer address. |
| packageWeight           | <span class="type">float</span>  | <span class="optional">optional</span> The total weight of the package in kg. |
| items                   | <span class="type">array</span>  | <span class="required">required</span> Array of <span class="object">Customs Item</span> objects with details of the products in the shipment for customs. |
| shippingMethod          | <span class="type">string</span> | <span class="required">required</span> The `name` of one of your [Shipping Methods](#shipping-methods) with a pricing agreement that is valid today. |

A single parcel worth more than €150 is checked at once: as `B2C` it is refused (unless your account is exempt); as `H2C` every item needs a 10 digit HS code and the parcel an `invoiceNumber`. The [confirm](#confirm-a-waybill-upload) checks all parcels of one buyer together.

### Address Object definitions:

| Field Name    | Type                             | Description |
|---------------|----------------------------------|-------------|
| `name`        | <span class="type">string</span> | <span class="required">required</span> Address contact name. Max 70 characters. |
| `street`      | <span class="type">string</span> | <span class="required">required</span> Address street line. Max 70 characters; for the buyer at least 3. |
| `zipcode`     | <span class="type">string</span> | Seller: <span class="required">required</span>, letters and digits with at most one `-` or `/`. Buyer: <span class="required_if">required if</span> the country uses postal codes, and it must match that country's format. |
| `city`        | <span class="type">string</span> | <span class="required">required</span> Address city. Max 35 characters; for the buyer at least 3. |
| `countryCode` | <span class="type">string</span> | <span class="required">required</span> Address country code in Alpha 2 Format (ISO 3166-1). |
| `eori`        | <span class="type">string</span> | <span class="optional">optional</span> Only for buyerDetails. EORI number of the buyer, max 17 characters. |
| `iossNumber`  | <span class="type">string</span> | Only for sellerDetails. <span class="required_if">Required if</span> the waybill's `declarationType` is `full`. Format `IM` followed by 10 digits. |

Names, streets and cities accept printable ASCII characters except `;` and `~`. The buyer's name and street also may not contain `<`, `=`, `>`, `?` or `@`.

<aside class="notice">
  If an encryption key is set up for your account, the `iossNumber` must be sent AES-128-ECB encrypted and base64 encoded. Please check with your account representative for encryption key information.
</aside>

### CustomsItem definitions:

| Field Name              | Type                             | Description |
|-------------------------|----------------------------------|-------------|
| `hsCode`                | <span class="type">string</span> | <span class="required">required</span> Harmonized Tariff Code of the item being shipped. It must be a known code that Alline accepts. 6 digits for `B2C`; 10 digits (TARIC) for `H2C`. |
| `description`           | <span class="type">string</span> | <span class="required">required</span> Description of the item being shipped. Max 512 characters. |
| `quantity`              | <span class="type">integer</span>| <span class="required">required</span> Quantity of the item, at least 1. |
| `weight`                | <span class="type">float</span>  | <span class="required">required</span> The weight of the item in kg, at least 0.001, at most 3 decimals. |
| `invoiceCurrency`       | <span class="type">string</span> | <span class="required">required</span> The currency of the item value, as ISO 4217 code (for example `EUR`). |
| `invoiceAmount`         | <span class="type">float</span>  | <span class="required">required</span> Total value of the item line, at least 0.01. |
| `freightValue`          | <span class="type">float</span>  | <span class="optional">optional</span> Freight value of the item line. |
| `sku`                   | <span class="type">string</span> | <span class="required">required</span> from 1 November 2026, optional before. Merchant product identification (M-PID, C127): the webshop SKU or ASIN. Max 70 characters. |
| `manufacturerProductId` | <span class="type">string</span> | <span class="required">required</span> from 1 November 2026, optional before. Manufacturer product identification (NS-PID, C128): the model or part number. Max 70 characters. |
| `standardProductId`     | <span class="type">string</span> | <span class="optional">optional</span> Standardised product identification (S-PID, C129): a valid EAN/GTIN-8/12/13/14, UPC or ISBN. Leave it out, or send `Y081`, when the product has none. |

`sku` and `manufacturerProductId` accept printable ASCII characters, without `;` and `"`.

<aside class="notice">
  From 1 November 2026 EU customs requires product identification on every e-commerce declaration line. A line that holds several products lists their ids comma separated, in the same order in each field, for example <code>"sku": "SKU-1,SKU-2"</code>.
</aside>

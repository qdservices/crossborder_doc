## Create and add a Parcel to a Waybill

```shell
curl "https://crossborder.omniship.eu/api/v3/waybills/4dcdea18-afb4-4c38-8541-9b83056a5667/parcels"
  -X POST
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  -d '{
	"waybillId": "4dcdea18-afb4-4c38-8541-9b83056a5667",
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
	"items": [{
		"hsCode": "950691",
		"description": "DUMBBELL SET",
		"quantity": 4,
		"weight": 22.95,
		"invoiceCurrency": "EUR",
		"invoiceAmount": 119.99,
		"freightValue": 3.30
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
    "items": [
      {
        "hsCode": "950691",
        "description": "DUMBBELL SET",
        "quantity": "4",
        "weight": 22.95,
        "invoiceCurrency": "EUR",
        "invoiceAmount": "119.99",
        "freightValue": "3.30"
      }
    ]
  }
}
```

This endpoint creates a new Parcel and adds it to the given Waybill pre alert in the <span class="font-weight: bold">ALL<span style="color: #d83636;">IN</span>E</span> cross border system. 

### HTTP Request

<span class="http-verb post">POST</span> `/api/v3/waybills/<ID>/parcels`

### URL Parameters

| Parameter | Description                                                                                                                                                                                                   |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID        | The ID of the <span class="object">Waybill</span> for which a <span class="object">Parcel</span> needs added. The ID was given at creation of the waybill and was either generated or is the given reference. |

### Arguments

| Attribute               | Type                             | Description                                                                                                                                                                                                      |
|-------------------------|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| transactionType         | <span class="type">string</span> | <span class="optional">Optional</span> Type of transaction. Valid values are `B2C`, `B2B`. Default value is `B2C`.                                                                                               |
| finalMileTrackingNumber | <span class="type">string</span> | <span class="required">required</span> Tracking number of the final mile parcel. This number cannot already exist in the master waybill.                                                                         | 
| bigBagBarcode           | <span class="type">string</span> | <span class="required">required</span> Barcode of the bag/box/unit containing the parcel(s). If there is only one parcel and no containing unit with a barcode, the finalMileTrackingNumber can be used instead. |
| sellerDetails           | <span class="type">object</span> | <span class="required">required</span> <span class="object">Address</span> object that should be used as sender address.                                                                                         |
| buyerDetails            | <span class="type">object</span> | <span class="required">required</span> <span class="object">Address</span> object that should be used as buyer address.                                                                                          |
| items                   | <span class="type">array</span>  | <span class="required">required</span> Array of <span class="object">Customs Item</span> objects with details of the products in the shipment for customs.                                                       |
| shippingMethod          | <span class="type">string</span> | <span class="required">required</span> Shipping Method                                                                                                                                                           |

### Address Object definitions:

<div class="magic-block-parameters">
	<div class="block-parameters-table">
		<div class="table">
			<div class="tr">
				<div class="th" style="min-width: 120px;">Field Name</div>
				<div class="th">Type</div>
				<div class="th">Description</div>
			</div>
			<div class="tr">
				<div class="td"><p><code>name</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required">required</span> Address contact name. Maximum: 70 characters </p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>street</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required">required</span> Address street line. Maximum: 70 characters </p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>zipcode</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required_if">required if</span> Country is postal aware. Address Zip code. </p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>city</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required">required</span> Address city</p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>countryCode</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required">required</span> Address country code in Alpha 2 Format  (ISO 3166-1)</p></div>
			</div>
      <div class="tr">
				<div class="td"><p><code>iossNumber</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required_if">Required If</span> <code>transactionType</code> is <code>B2C</code> and the parcel should be declared to customs. Only for sellerDetails</p></div>
			</div>
		</div>
	</div>
</div>

<aside class="notice">
  The `iossNumber` can be sent as a base64 string after AES encryption. Please check with your account representative for encryption key information.
</aside>


### CustomsItem definitions:

<div class="magic-block-parameters">
	<div class="block-parameters-table">
		<div class="table">
			<div class="tr">
				<div class="th" style="min-width: 120px;">Field Name</div>
				<div class="th">Type</div>
				<div class="th">Description</div>
			</div>
      <div class="tr">
				<div class="td"><p><code>hsCode</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required">required</span> Harmonized Tariff Code of the item being shipped</p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>description</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required">required</span> Description of the item being shipped</p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>quantity</code></p></div>
				<div class="td"><p><span>integer</span></p></div>
				<div class="td"><p><span class="optional">optional</span> Quantity of the item to be shipped, must be greater than zero. Defaults to <code>1</code></p></div>
			</div>
      <div class="tr">
				<div class="td"><p><code>weight</code></p></div>
				<div class="td"><p><span>object</span></p></div>
				<div class="td"><p><span class="required">required</span> The weight of the item being shipped</p></div>
			</div>
      <div class="tr">
				<div class="td"><p><code>invoiceCurrency</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="required">required</span> The currency of the item value</p></div>
			</div>
			<div class="tr">
				<div class="td"><p><code>invoiceAmount</code></p></div>
				<div class="td"><p><span>float</span></p></div>
				<div class="td"><p><span class="required">required</span> Total Value of the item line</p></div>
			</div>
      <div class="tr">
				<div class="td"><p><code>freightValue</code></p></div>
				<div class="td"><p><span>float</span></p></div>
				<div class="td"><p><span class="optional">optional</span> Freight Value of the item line</p></div>
			</div>
      <div class="tr">
				<div class="td"><p><code>sku</code></p></div>
				<div class="td"><p><span>string</span></p></div>
				<div class="td"><p><span class="optional">optional</span> Product SKU </p></div>
			</div>
		</div>
	</div>
</div>

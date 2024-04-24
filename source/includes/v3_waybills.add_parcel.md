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
		"iossNumber": "IM5280002556"
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
		"invoiceAmount": 119.99
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
      "countryCode": "CN"
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
        "invoiceAmount": "119.99"
      }
    ]
  }
}
```

This endpoint creates a new Parcel and adds it to the given Waybill pre alert in the <span class="font-weight: bold">ALL<span style="color: #d83636;">IN</span>E</span> cross border system. 

### HTTP Request

<span class="http-verb post">POST</span> `https://crossborder.omniship.eu/api/v3/waybills/<ID>/parcels`

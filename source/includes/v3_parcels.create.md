## Create a Parcel

```shell
curl "https://crossborder.omniship.eu/api/v3/parcels"
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
    "id": "4dcdea18-afb4-4c38-8541-9b83056a5667",
    "masterWaybillNumber": "180-19687301",
    "transportType": "air",
    "customer": "Acme International",
    "customer_code": "ACE",
    "status": "pre_upload",
    "status_changed": "2024-04-23T09:02:15.000000Z",
    "status_changed_human": "1 second ago",
    "bigBagCount": 1,
    "grossWeight": 13.25,
    "airline": {
      "trackingLink": "https:\/\/cargo.koreanair.com\/tracking",
      "name": "Korean Air Lines",
      "prefix": "180",
      "code": "KE",
      "copyNumber": "19687301"
    },
    "destinationFlightNumber": "KE0925",
    "eta": "2024-05-26T12:52:00.000000Z",
    "declarationType": "full"
  }
}
```

This endpoint creates a new Waybill pre alert in ALL<span style="color: #d83636;">IN</span>E cross border. 

### HTTP Request

<span class="http-verb post">POST</span> `/api/v3/parcels`

### Arguments

| Attribute                 | Type                                    | Description                                                                                                                                                                                                                                                                                                                                                                                                                              |
|---------------------------|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| masterWaybillNumber       | <span class="type">string</span>        | <span class="required">required</span> Unique number of the waybill. This number cannot already exist in the database for the same customer.                                                                                                                                                                                                                                                                                             |
| customer_code             | <span class="type">string</span>        | The unique customer code. This code should reflect a customer code in the database. Only <span class="required_if">required if</span> account has sub-customers.                                                                                                                                                                                                                                                                         | 
| transportType             | <span class="type">string</span>        | <span class="required">required</span> The type of waybill. Valid values are `air`, `road`, `train`, `other`                                                                                                                                                                                                                                                                                                                             |
| grossWeight               | <span class="type">float</span>         | <span class="required">required</span> The given gross weight for the shipment. Should be the same as the gross weight on the Air Waybill copy.                                                                                                                                                                                                                                                                                          |
| parcelCount               | <span class="type">integer</span>       | <span class="required">required</span> The number of parcels contained in the shipment.                                                                                                                                                                                                                                                                                                                                                  |
| bigBagCount               | <span class="type">integer</span>       | <span class="required">required</span> The number of bigBags/Boxes/Units contained in the shipment.                                                                                                                                                                                                                                                                                                                                      |
| destinationFlightNumber   | <span class="type">string</span>        | <span class="optional">optional</span> The incoming flight number to the destination airport. For the Alline warehouse the destination airport is Schiphol (AMS).                                                                                                                                                                                                                                                                        |
| eta                       | <span class="type">date</span>          | <span class="optional">optional</span> The estimated arrival date at the destination airport. The date should be in the timezone of the destination in format `yyyy-mm-dd`.                                                                                                                                                                                                                                                              |
| declarationType           | <span class="type">string</span>        | <span class="optional">optional</span> Indicates if Alline should process the customs declaration for this shipment. Valid values are `full`, `partial`, `none`  Default is `full`.                                                                                                                                                                                                                                                      | 
| waybill_document          | <span class="type">base64_string</span> | <span class="required_if">Required If</span> `waybill_type` is `air` base64 encoded pdf file of the Waybill Document associated with the shipment.                                                                                                                                                                                                                                                                                       |


## Confirm a Waybill upload

```shell
curl "https://crossborder.omniship.eu/api/v3/waybills/4dcdea18-afb4-4c38-8541-9b83056a5667/confirm"
  -X PUT
  -H "Authorization: Bearer FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  
```

> The above command returns JSON structured like this:

```
HTTP/1.1 200 OK
Content-Type:application/json;charset=UTF-8
```
```json
{
  "data": {
    "id": "1cb3480a-86d3-44f2-a36d-f082e501fd37",
    "masterWaybillNumber": "112-60318215",
    "transportType": "air",
    "customer": "Acme",
    "customer_code": "ACE",
    "status": "created",
    "statusChangeUtc": "2024-04-24T07:09:14+00:00",
    "statusChangeLocalTime": "2024-04-24T09:09:14+02:00",
    "statusChangedHuman": "4 minutes ago",
    "bigBagCount": 1,
    "grossWeight": 13.25,
    "airline": {
      "trackingLink": "https:\/\/www.skyteam.com\/en\/cargo\/track-shipment\/",
      "name": "China Cargo Airlines",
      "prefix": "112",
      "code": "MU",
      "copyNumber": "60318215"
    },
    "destinationFlightNumber": "CK210",
    "flight_date": "2024-05-26",
    "eta": "2024-05-26T00:00:00+02:00",
    "declarationType": "full",
    "parcels": [
      "1Z1V510W6898496192"
    ],
    "inboundComplete": false,
    "totalBagsUploaded": 1,
    "totalParcelsUploaded": 1,
    "parcelsInbound": 0,
    "parcelsInboundPercentage": "0%",
    "parcelsReleased": 0,
    "parcelsReleasedPercentage": "0 %",
    "parcelsOutbound": 0,
    "parcelsOutboundPercentage": "0%"
  }
}
```

This endpoint confirms a new AirWaybill in ALL<span style="color: #d83636;">IN</span>E cross border after all parcels have been added through the add-parcel endpoint and the waybill is ready to be created and processed. 

The waybill is confirmed only when:

* it is still in status `pre_upload` (otherwise: `The waybill is already confirmed.`);
* the number of bags added (distinct `bigBagBarcode` values) equals the `bigBagCount` given at creation;
* every parcel has a shipping method, and all parcels in one bag share the same shipping method (unless your account allows mixed bags);
* the transaction types fit the parcel values: when the parcels of one buyer are worth more than €150 together they must be `H2C`, with a 10 digit HS code on every item and an `invoiceNumber`.

Otherwise the request is answered with `422`. Errors about a parcel are keyed by its finalMileTrackingNumber, for example `parcels.1Z1V510W6898496192.shippingMethod`, `parcels.1Z1V510W6898496192.transactionType`, `parcels.1Z1V510W6898496192.invoiceNumber` or `parcels.1Z1V510W6898496192.items.0.hsCode`.

### HTTP Request

<span class="http-verb put">PUT</span> `/api/v3/waybills/<ID>/confirm`

### URL Parameters

| Parameter | Description                                                                                                                                                   |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID        | The ID of the <span class="object">Waybill</span> to confirm. The ID was given at creation of the waybill and was either generated or is the given reference. |


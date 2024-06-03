## Confirm a Waybill upload

```shell
curl "https://cbe.vdhelm.com/api/v3/waybills/4dcdea18-afb4-4c38-8541-9b83056a5667/confirm"
  -X PUT
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
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
    "destinationFlightNumber": "KE0925",
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

This endpoint confirms a new AirWaybill in CBE tool after all parcels have been added through the add-parcel endpoint and the waybill is ready to be created and processed. 

### HTTP Request

<span class="http-verb put">PUT</span> `https://cbe.vdhelm.com/api/v3/waybills/<ID>/confirm`

### URL Parameters

| Parameter | Description                                                                                                                                                   |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID        | The ID of the <span class="object">Waybill</span> to confirm. The ID was given at creation of the waybill and was either generated or is the given reference. |


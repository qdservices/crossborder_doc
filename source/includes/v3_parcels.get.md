## Retrieve a Specific Parcel

```shell
curl "https://cbe.vdhelm.com/api/v3/parcels/4dcdea18-afb4-4c38-8541-9b83056a5667"
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
    "id": "4dcdea18-afb4-4c38-8541-9b83056a5667",
    "masterWaybillNumber": "180-19687301",
    "transportType": "air",
    "customer": "CNE International",
    "customer_code": "CNE",
    "status": "created",
    "status_changed": "2024-04-23T01:30:45.000000Z",
    "status_changed_human": "6 hours ago",
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
    "declarationType": "full",
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

This endpoint retrieves a specific Parcel.

### HTTP Request

<span class="http-verb get">GET</span> `/api/v3/parcels/<ID>`

### URL Parameters

| Parameter | Description          |
|-----------|----------------------|
| ID        | The ID of the Parcel |

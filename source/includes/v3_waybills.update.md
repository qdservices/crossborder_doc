## Confirm a Waybill upload

```shell
curl "https://crossborder.omniship.eu/api/v3/waybills/4dcdea18-afb4-4c38-8541-9b83056a5667/confirm"
  -X PATCH
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
    "status_changed": "2024-04-23T10:19:16.000000Z",
    "status_changed_human": "1 second ago",
    "bigBagCount": 1,
    "grossWeight": 13.25,
    "airline": {
      "trackingLink": "https://cargo.koreanair.com/tracking",
      "name": "Korean Air Lines",
      "prefix": "180",
      "code": "KE",
      "copyNumber": "19687301"
    },
    "destinationFlightNumber": "EK147",
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

This endpoint confirms a new AirWaybill in ALL<span style="color: #d83636;">IN</span>E cross border after all parcels have been added through the add-parcel endpoint and the waybill is ready to be created and processed. 

### HTTP Request

<span class="http-verb patch">PATCH</span> `https://crossborder.omniship.eu/api/v3/waybills/<ID>/confirm`

### URL Parameters

| Parameter | Description                      |
|-----------|----------------------------------|
|  ID       | The ID of the Waybill to confirm |


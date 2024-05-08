# Waybills

> Example:

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
    "statusChangedHuman": "1 second ago",
    "bigBagCount": 1,
    "grossWeight": 13.25,
    "airline": {
      "trackingLink": "https://www.skyteam.com/en/cargo/track-shipment/",
      "name": "China Cargo Airlines",
      "prefix": "112",
      "code": "MU",
      "copyNumber": "60318215"
    },
    "destinationFlightNumber": "CK210",
    "eta": "2024-05-26T00:00:00+02:00",
    "declarationType": "full",
    "parcels": [
      "1Z1V510W6898496192"
    ],
    "inboundComplete": false,
    "totalBagsUploaded": 0,
    "totalParcelsUploaded": 0,
    "parcelsInbound": 0,
    "parcelsInboundPercentage": "0%",
    "parcelsReleased": 0,
    "parcelsReleasedPercentage": "0 %",
    "parcelsOutbound": 0,
    "parcelsOutboundPercentage": "0%"
  }
}
```

A Waybill is a document that represents the contents of a shipment ready for transport and processing. It details
the exact quantity, price and delivery details of the individual packages. 
Perform the simple operations mentioned below to create and manage your Waybill pre alert.

| Attribute                     | Type                             | Description                                                                                                                                                                                                      |
|-------------------------------|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                          | <span class=type>string</span>   | Unique ID of a waybill. This is used as an identifier. The ID Is either created by the system or your own reference given at creation                                                                            |
| `masterWaybillNumber`         | <span class=type>string</span>   | Identifies the total shipment. If waybill `transportType` is `air` a validation check is done on the format of the masterWaybillNumber given.                                                                    |
| `transportType`               | <span class=type>string</span>   | The transport type of the waybill. Valid values are (`air`, `road`, `train`, `sea`, `other`).                                                                                                                    |
| `customer`                    | <span class=type>string</span>   | Customer name of the account associated with the waybill.                                                                                                                                                        |
| `customer_code`               | <span class=type>string</span>   | Unique ID of a customer. This is used as an identifier.                                                                                                                                                          |
| `status`                      | <span class=type>string</span>   | Indicates the current waybill status. Values can be (`pre_upload`, `created`, `noa_received`, `received`, `ready_to_scan`, `scanning...`, `pending_check`, `inbound`, `partial_inbound`, `part_out`, `outbound`) |
| `statusChangeUtc`             | <span class=type>datetime</span> | Identifies the date and time of the last status change in UTC time.                                                                                                                                              |
| `statusChangeLocalTime`       | <span class=type>datetime</span> | Identifies the date and time of the last status change in local time of the warehouse.                                                                                                                           |
| `statusChangedHuman`          | <span class=type>datetime</span> | Human readable representation of the time past since last status change.                                                                                                                                         |
| `bigBagCount`                 | <span class=type>integer</span>  | Indicates the number of pieces (BigBags/Boxes/Units) expected for the shipment.                                                                                                                                  |
| `grossWeight`                 | <span class="type">float</span>  | Indicates the given gross weight for the shipment.                                                                                                                                                               |
| `airline`                     | <span class=type>string</span>   | The airline for the incoming flight in case `transportType` is `air`.                                                                                                                                            |
| `destinationFlightNumber`     | <span class=type>string</span>   | The incoming flight number to the destination airport. For the Alline warehouse the destination airport is Schiphol (AMS)                                                                                        |
| `eta`                         | <span class=type>datetime</span> | The estimated arrival time at the destination airport. (Updates automatically when right flight number and arrival date are given.                                                                               |
| `declarationType`             | <span class=type>string</span>   | The type of customs declaration needed for the shipment. Valid values are (`full`, `partial`, `none`).                                                                                                           |
| `inboundComplete`             | <span class=type>boolean</span>  | Indicates if the inbound scan is (temporarily) completed.                                                                                                                                                        |
| `totalBagsUploaded`           | <span class=type>integer</span>  | The total number of BigBags/Boxes/Units uploaded in the system associated with this waybill.                                                                                                                     |
| `parcelsInbound`              | <span class=type>integer</span>  | The total number of Parcels uploaded in the system associated with this waybill.                                                                                                                                 |
| `parcelsInboundPercentage`    | <span class=type>string</span>   | The percentage of parcels currently inbound.                                                                                                                                                                     |
| `parcelsReleased`             | <span class=type>integer</span>  | The total number of parcels released.                                                                                                                                                                            |
| `parcelsReleasedPercentage`   | <span class=type>string</span>   | The percentage of parcels currently released.                                                                                                                                                                    |
| `parcelsOutbound`             | <span class=type>inbound</span>  | The total number of parcels currently outbound.                                                                                                                                                                  |
| `parcelsOutboundPercentage`   | <span class=type>string</span>   | The percentage of parcels currently outbound.                                                                                                                                                                    |








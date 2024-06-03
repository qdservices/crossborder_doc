# Parcels

> Example:

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

A waybill is a document that represents the contents of a shipment ready for transport. It details
the exact quantity, price and delivery details of the individual packages. 
Perform the simple operations mentioned below to create and manage your Waybill pre alert.

| Attribute                         | Type                             | Description                                                                                                                                                                                                      |
|-----------------------------------|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `id`                              | <span class=type>string</span>   | Unique ID of a waybill. This is used as an identifier.                                                                                                                                                           |
| `masterWaybillNumber`             | <span class=type>string</span>   | Identifies the total shipment. If waybill type is 'air' a validation check is done on the format of the waybill_number given.                                                                                    |
| `transportType`                   | <span class=type>string</span>   | The type of waybill. Valid values are ('air', 'road', 'train', 'sea', 'other').                                                                                                                                  |
| `customer`                        | <span class=type>string</span>   | Customer name.                                                                                                                                                                                                   |
| `customer_code`                   | <span class=type>string</span>   | Unique ID of a customer. This is used as an identifier.                                                                                                                                                          |
| `status`                          | <span class=type>string</span>   | Indicates the current waybill status. Values can be ('pre_upload', 'created', 'noa_received', 'received', 'ready_to_scan', 'scanning...', 'pending_check', 'inbound', 'partial_inbound', 'part_out', 'outbound') |
| `status_changed`                  | <span class=type>datetime</span> | Identifies the date and time of the last status change in UTC time.                                                                                                                                              |
| `bigBagCount`                     | <span class=type>integer</span>  | Indicates the number of pieces (BigBags/Boxes/Units) expected for the shipment.                                                                                                                                  |
| `grossWeight`                     | <span class="type">float</span>  | Indicates the given gross weight for the shipment.                                                                                                                                                               |
| `airline`                         | <span class=type>string</span>   | The airline for the incoming flight in case transportType is 'air'.                                                                                                                                              |
| `destinationFlightNumber`         | <span class=type>string</span>   | The incoming flight number to the destination airport. For the VDH warehouse the destination airport is Schiphol (AMS)                                                                                           |
| `eta`                             | <span class=type>datetime</span> | The estimated arrival time at the destination airport. (Updates automatically when right flight number and arrival date are given.                                                                               |
| `declarationType`                 | <span class=type>string</span>   | The type of customs declaration needed for the shipment. Valid values are ('full', 'partial', 'none').                                                                                                           |
| `inboundComplete`                 | <span class=type>boolean</span>  | Indicates if the inbound scan is (temporarily) completed.                                                                                                                                                        |
| `totalBagsUploaded`               | <span class=type>integer</span>  | The total number of BigBags/Boxes/Units uploaded in the system associated with this waybill.                                                                                                                     |
| `parcelsInbound`                  | <span class=type>integer</span>  | The total number of Parcels uploaded in the system associated with this waybill.                                                                                                                                 |
| `parcelsInboundPercentage`        | <span class=type>string</span>   | The percentage of parcels currently inbound.                                                                                                                                                                     |
| `parcelsReleased`                 | <span class=type>integer</span>  | The total number of parcels released.                                                                                                                                                                            |
| `parcelsReleasedPercentage`       | <span class=type>string</span>   | The percentage of parcels currently released.                                                                                                                                                                    |
| `parcelsOutbound`                 | <span class=type>inbound</span>  | The total number of parcels currently outbound.                                                                                                                                                                  |
| `parcelsOutboundPercentage`       | <span class=type>string</span>   | TThe percentage of parcels currently outbound.                                                                                                                                                                   |








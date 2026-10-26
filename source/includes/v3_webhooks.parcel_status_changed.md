## Webhooks parcel.state.updated

When the status of one of your parcels changes, you'll get the event payload as below:

```json
{
  "eventType": "parcel.state.updated",
  "resourceType": "parcel",
  "resourceId": "a51133c1-a0a4-4867-9507-18a6082aaacc",
  "parcel": {
    "finalMileTrackingNumber": "1Z1V510W6898496192",
    "parcelState": "cb_import_customs_finished",
    "importMrn": "26NL0001234567890A",
    "freightValue": "3.30",
    "packageWeight": 23.5,
    "currency": "EUR",
    "inboundUtc": "2024-05-26T12:03:26+00:00",
    "inboundLocalTime": "2024-05-26T14:03:26+02:00",
    "releasedUtc": "2024-05-26T13:15:02+00:00",
    "releasedLocalTime": "2024-05-26T15:15:02+02:00",
    "outboundUtc": null,
    "outboundLocalTime": null,
    "lastUpdatedUtc": "2024-05-26T13:15:02+00:00",
    "lastUpdatedLocalTime": "2024-05-26T15:15:02+02:00"
  }
}
```

`resourceId` is the parcel `id` returned when the parcel was added. `importMrn` is the MRN of the import declaration once there is one. The dates are `null` until the step has happened.

| parcelState                     | Meaning                                                  |
|---------------------------------|----------------------------------------------------------|
| `created`                       | The parcel is known but not yet received.                |
| `cb_transport_destination_port` | The parcel arrived in the warehouse.                     |
| `cb_import_customs_start`       | Customs clearance started.                               |
| `cb_import_customs_inspection`  | Customs selected the parcel for inspection.              |
| `cb_import_customs_finished`    | Customs released the parcel.                             |
| `cb_transport_handover`         | The released parcel left the warehouse (outbound).       |
| `cb_import_customs_exception`   | Customs raised an exception or confiscated the parcel.   |
| `cb_import_customs_failure`     | The parcel was destroyed.                                |

Other internal states may be sent as they are.

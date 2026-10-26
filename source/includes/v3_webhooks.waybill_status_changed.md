## Webhooks waybill.state.updated

When the status of one of your waybills changes, you'll get the event payload as below:

```json
{
  "eventType": "waybill.state.updated",
  "resourceType": "waybill",
  "resource_id": 123456,
  "waybill": {
    "number": "180-19687301",
    "customer": "Acme",
    "waybill_state": "created",
    "updated_at_utc": "2024-05-26T12:05:32+00:00",
    "updated_at_local_time": "2024-05-26T14:05:32+02:00"
  }
}
```

`waybill.number` is the masterWaybillNumber. `resource_id` is an internal number of the waybill, not its `id` in the API: match events on `waybill.number`.

`waybill_state` takes the values of the Waybill `status`, except that the customs stage is sent as `on_hold` (the API reports it as `pending_clearance`).

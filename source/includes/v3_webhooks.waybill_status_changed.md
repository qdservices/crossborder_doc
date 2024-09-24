## Webhooks waybill.status.updated

When your shipment's tracking status changed, you'll get the event payload as below:

waybill.state.updated

<pre style="float:left">
<code>
{
  "event_type": "waybill.state.updated",
  "resource_type": "waybill",
  "resource_id": "4dcdea18-afb4-4c38-8541-9b83056a5667",
  "waybill_state": {
    "number": "180-19687301",
    "customer": "Acme",
    "waybill_state": "created",
    "updated_at_utc": "2024-05-26T14:05:32",
    "updated_at_local_time": "2024-05-26T15:05:32",
  }
}
</code>
</pre>









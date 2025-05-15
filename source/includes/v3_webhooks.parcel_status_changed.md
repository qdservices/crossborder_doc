## Webhooks parcel.status.updated

When your shipment's tracking status changed, you'll get the event payload as below:

parcel.state.updated
<pre style="float: left">
<code>
{
  "event_type": "parcel.state.updated",
  "resource_type": "parcel",
  "resource_id": "a51133c1-a0a4-4867-9507-18a6082aaacc",
  "parcel_state": {
    "id": "a51133c1-a0a4-4867-9507-18a6082aaacc",
    "finalMileTrackingNumber": "1Z1V510W6898496192",
    "parcelState": "created",
    "freightValue": 3.30,
    "currency": "EUR",
    "inboundUtc": null,
    "inboundLocalTime": null,
    "releasedUtc": null
    "releasedLocalTime": null,
    "outboundUtc": null
    "outboundLocalTime": null
    "lastUpdatedUtc": "2024-05-26T14:03:26",
    "lastUpdatedLocalTime": "2024-05-26T15:03:26"
  }
}
</code>
</pre>








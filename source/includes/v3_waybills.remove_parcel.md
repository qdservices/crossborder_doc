## Remove a Parcel from a Waybill

A parcel can only be removed from a waybill when the waybill is not yet confirmed

```shell
curl "https://crossborder.omniship.eu/api/v3/waybills/4dcdea18-afb4-4c38-8541-9b83056a5667/parcels/a51133c1-a0a4-4867-9507-18a6082aaacc"
  -X DELETE
  -H "Authorization: Bearer FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
```

> The above command returns JSON structured like this:

```
HTTP/1.1 204 No Content
Content-Type:application/json;charset=UTF-8
```

### HTTP Request

<span class="http-verb delete">DELETE</span> `/api/v3/waybills/<WaybillID>/parcels/<ParcelID>`

### URL Parameters

| Parameter | Description                                                                                                                                                                                                            |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| WaybillID | The ID of the <span class="object">Waybill</span> from which a <span class="object">Parcel</span> needs to be removed. The ID was given at creation of the waybill and was either generated or is the given reference. |
| ParcelID  | The ID of the <span class="object">Parcel</span> to be removed                                                                                                                                                         |

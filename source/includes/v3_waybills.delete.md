## Delete a Waybill

A Waybill can only be removed when the state is `pre_upload`, `created` or `noa_received`

```shell
curl "https://cbe.vdhelm.com/api/v3/waybills/4dcdea18-afb4-4c38-8541-9b83056a5667"
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

<span class="http-verb delete">DELETE</span> `/api/v3/waybills/<ID>/`

### URL Parameters

| Parameter | Description                                                                                                                                                                 |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID        | The ID of the <span class="object">Waybill</span> that needs to be deleted. The ID was given at creation of the waybill and was either generated or is the given reference. |

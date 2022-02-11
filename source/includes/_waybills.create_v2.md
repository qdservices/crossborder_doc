## Create a Waybill

```shell
curl "https://crossborder.omniship.eu/api/v2/waybills"
  -X POST
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  -d '{
        "customer_code": "GFS",
        "waybill_type": "air",
        "waybill_number": "784-65428952",
        "reference": 71577,
        "weight_unit": "grams",
        "waybill_document": "JVBERi0xLjQKJeTjz9IKMyAwIG9iago8PC9MZW5ndGggNCAwIFIKL0ZpbHRlci9GbGF0ZURlY29kZQo+PgpzdHJlYW0KeJydlM1ymzAQx+96ij22B9uSAAnl5sbG02k+WpvJTE8dgmUPHQOJgHjch+ozdkUc18aQ4sIwArT72/9+AAOKJ8PLU+5QehCnhNXvBq8LPn8KyYBRCuEvMg0JtVZ253BTu9jTrMkzYS4w4QGjnkCGAqPJinwjtYe1oENfucg+WU48FW91RBmjwOriEK72r+czvAm3e8moQQHzFIQpqc1uyIdJHlepzkrIqvRRm4/hz1ePLhmY4TPhVFwk5UgBZ6wp4XZ+1y+so/w6rOO0l+6dsC51mmFDEy21QchKG53Fup8G6ey74LqXapDOefV1EZvkqUzyrF94X/r/G973z0qwKKOyKg6RRwFDTzoUQshzd44ZSLXftIw3QwR9zbdYxCU87mAWlXob7X4fUXk31Q6kI9uhwffre7h/0eYl0VsYwG2UJStdlCB9dyBQC/UUhSDZaFCMc0EZ9VUj7HkZbEQs4nETOB/9BfzA0grHY/8E1ZN8SuL87oaNAyG+TNnEV9N5Q44aOni0D6f09puIe7NDJKUeZkmldKiSnEoulNsLWk9bB3SdmE0BRZWUvVD15HSgoHefucvb+zyZYp/rZo9NmcQbXfRnem47czxbHGiwMnkK14sH+Jw+5absTxeinb6o0jQyO1jqeBOZyH6+PTXboeksRHPm3mN0JU4vYHSlF+zi/AqN5nqdFKX9sPGJ++KAxl/RH05bj5MKZW5kc3RyZWFtCmVuZG9iago0IDAgb2JqCjUzNgplbmRvYmoKMiAwIG9iago8PC9UeXBlL1BhZ2UKL1BhcmVudCAxIDAgUgovUmVzb3VyY2VzIDggMCBSCi9NZWRpYUJveFswIDAgODQxLjUgNTk0Ljc1XQovQ29udGVudHNbMyAwIFIgXQo+PgplbmRvYmoKOCAwIG9iago8PC9Qcm9jU2V0Wy9QREYvSW1hZ2VCL0ltYWdlQy9JbWFnZUkvVGV4dF0KL0ZvbnQ8PC9GMCA1IDAgUgovRjEgNiAwIFIKL0YyIDcgMCBSCj4+Cj4+CmVuZG9iago5IDAgb2JqCjw8L1N1YmplY3QgKEdXX0RFQ09fRllDT19PVkVSVklFVy5SRDEpCi9UaXRsZSAoR1dfREVDT19GWUNPX09WRVJWSUVXLlJEMSkKL0NyZWF0b3IgKEdhdGV3YXkgVjIpCi9BdXRob3IgKGVob2x0KQovQ3JlYXRpb25EYXRlIChEOjIwMjIwMTE3MTIwMTU1KzAxJzAwJykKL1Byb2R1Y2VyIChHV1BkZiAyLjIxIFwoQysrL1dpbjMyXCkpCj4+CmVuZG9iago1IDAgb2JqCjw8L1R5cGUvRm9udAovU3VidHlwZS9UcnVlVHlwZQovQmFzZUZvbnQvVmVyZGFuYS1Cb2xkCi9Gb250RGVzY3JpcHRvciAxMCAwIFIKL0ZpcnN0Q2hhciAwCi9MYXN0Q2hhciAyNTUKL1dpZHRoc1sKIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAKIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAKIDM0MiA0MDIgNTg3IDg2NyA3MTEgMTI3MiA4NjIgMzMyIDU0MyA1NDMgNzExIDg2NyAzNjEgNDgwIDM2MSA2ODkKIDcxMSA3MTEgNzExIDcxMSA3MTEgNzExIDcxMSA3MTEgNzExIDcxMSA0MDIgNDAyIDg2NyA4NjcgODY3IDYxNwogOTY0IDc3NiA3NjIgNzI0IDgzMCA2ODMgNjUwIDgxMSA4MzcgNTQ2IDU1NSA3NzEgNjM3IDk0OCA4NDcgODUwCiA3MzMgODUwIDc4MiA3MTAgNjgyIDgxMiA3NjQgMTEyOCA3NjQgNzM3IDY5MiA1NDMgNjg5IDU0MyA4NjcgNzExCiA3MTEgNjY4IDY5OSA1ODggNjk5IDY2NCA0MjIgNjk5IDcxMiAzNDIgNDAzIDY3MSAzNDIgMTA1OCA3MTIgNjg3CiA2OTkgNjk5IDQ5NyA1OTMgNDU2IDcxMiA2NTAgOTc5IDY2OSA2NTEgNTk3IDcxMSA1NDMgNzExIDg2NyA3MTEKIDcxMSA3MTEgMzMyIDcxMSA1ODcgMTA0OSA3MTEgNzExIDcxMSAxNzc3IDcxMCA1NDMgMTEzNSA3MTEgNjkyIDcxMQogNzExIDMzMiAzMzIgNTg3IDU4NyA3MTEgNzExIDEwMDAgNzExIDk2NCA1OTMgNTQzIDEwNjggNzExIDU5NyA3MzcKIDM0MiA0MDIgNzExIDcxMSA3MTEgNzExIDU0MyA3MTEgNzExIDk2NCA1OTggODUwIDg2NyA0ODAgOTY0IDcxMQogNTg3IDg2NyA1OTggNTk4IDcxMSA3MjEgNzExIDM2MSA3MTEgNTk4IDU5OCA4NTAgMTE4MiAxMTgyIDExODIgNjE3CiA3NzYgNzc2IDc3NiA3NzYgNzc2IDc3NiAxMDk0IDcyNCA2ODMgNjgzIDY4MyA2ODMgNTQ2IDU0NiA1NDYgNTQ2CiA4MzAgODQ3IDg1MCA4NTAgODUwIDg1MCA4NTAgODY3IDg1MCA4MTIgODEyIDgxMiA4MTIgNzM3IDczNSA3MTMKIDY2OCA2NjggNjY4IDY2OCA2NjggNjY4IDEwMTggNTg4IDY2NCA2NjQgNjY0IDY2NCAzNDIgMzQyIDM0MiAzNDIKIDY3OSA3MTIgNjg3IDY4NyA2ODcgNjg3IDY4NyA4NjcgNjg3IDcxMiA3MTIgNzEyIDcxMiA2NTEgNjk5IDY1MQpdCi9FbmNvZGluZy9XaW5BbnNpRW5jb2RpbmcKPj4KZW5kb2JqCjEwIDAgb2JqCjw8L1R5cGUvRm9udERlc2NyaXB0b3IKL0FzY2VudCA3NjUKL0NhcEhlaWdodCA3MjcKL0Rlc2NlbnQgLTIwNwovRmxhZ3MgMjYyMTc2Ci9Gb250QkJveFstNTUwIC0zMDMgMTcwNyAxMDcyXQovRm9udE5hbWUvVmVyZGFuYSMyMEJvbGQKL0l0YWxpY0FuZ2xlIDAKL1N0ZW1WIDE2NQovWEhlaWdodCA1NDgKPj4KZW5kb2JqCjYgMCBvYmoKPDwvVHlwZS9Gb250Ci9TdWJ0eXBlL1RydWVUeXBlCi9CYXNlRm9udC9DYWxpYnJpLUxpZ2h0Ci9Gb250RGVzY3JpcHRvciAxMSAwIFIKL0ZpcnN0Q2hhciAwCi9MYXN0Q2hhciAyNTUKL1dpZHRoc1sKIDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNwogNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3CiAyMjYgMzI2IDM4MCA0OTggNTA3IDcwNyA2NzAgMjE0IDI5OSAyOTkgNDk4IDQ5OCAyNDUgMzA2IDI0NSAzNjIKIDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyAyNjMgMjYzIDQ5OCA0OTggNDk4IDQ2MwogODkyIDU2MyA1MzUgNTM1IDYwNyA0ODkgNDYwIDYyNyA2MTkgNiA1NTQgODgxIDUwMSA0NjkgNDYzIDI5NyAzNjIgMjk3IDQ5OCA0OTgKIDI4NiA0NzEgNTIwIDQyNSA1MjAgNDk0IDI5OSA0NjkgNTIwIDIyMSAyMzAgNDQxIDIyMSA3OTEgNTIwIDUyMQogNTIwIDUyMCAzNDUgMzg3IDMyOSA1MjAgNDQwIDY5OSA0MTggNDQxIDM5NCAyOTkgNDUzIDI5OSA0OTggNDk4CiA1MDcgNDk4IDI0NSAyOTkgNDA5IDY3OSA0OTggNDk4IDM5MSAxMDI1IDQ1MyAzMzYgODYzIDQ5OCA0NjMgNDk4CiA0OTggMjQ1IDI0NSA0MDkgNDA5IDQ5OCA0OTggOTA1IDQ1NCA2OTcgMzg3IDMzNiA4NTQgNDk4IDM5NCA0NjkKIDIyNiAzMjYgNDk4IDUwNyA0OTggNTA3IDQ5OCA0OTggMzgwIDgzNCAzOTUgNDk4IDQ5OCAzMDYgNTA3IDM5NgogMzM3IDQ5OCAzMzUgMzM0IDI4NyA1NDIgNTgwIDI0NSAzMTAgMjQzIDQxNiA0OTggNjI1IDY2MSA2NjEgNDYzCiA1NjMgNTYzIDU2MyA1NjMgNTYzIDU2MyA3NTcgNTM1IDQ4OSA0ODkgNDg5IDQ4OSAyNDQgMjQ0IDI0NCAyNDQKIDYxNiA2MzggNjU0IDY1NCA2NTQgNjU0IDY1NCA0OTggNjU0IDYzNiA2MzYgNjM2IDYzNiA0NjkgNTA4IDUxMgogNDcxIDQ3MSA0NzEgNDcxIDQ3MSA0NzEgNzcyIDQyNSA0OTQgNDk0IDQ5NCA0OTQgMjIxIDIyMSAyMjEgMjIxCiA1MjAgNTIwIDUyMSA1MjEgNTIxIDUyMSA1MjEgNDk4IDUyMSA1MjAgNTIwIDUyMCA1MjAgNDQxIDUyMCA0NDEKXQovRW5jb2RpbmcvV2luQW5zaUVuY29kaW5nCj4+CmVuZG9iagoxMSAwIG9iago8PC9UeXBlL0ZvbnREZXNjcmlwdG9yCi9Bc2NlbnQgNzUwCi9DYXBIZWlnaHQgNjMyCi9EZXNjZW50IC0yNTAKL0ZsYWdzIDMyCi9Gb250QkJveFstNTExIC0yNjkgMTMwOSA5NTJdCi9Gb250TmFtZS9DYWxpYnJpIzIwTGlnaHQKL0l0YWxpY0FuZ2xlIDAKL1N0ZW1WIDcxCi9YSGVpZ2h0IDQ2Mgo+PgplbmRvYmoKNyAwIG9iago8PC9UeXBlL0ZvbnQKL1N1YnR5cGUvVHJ1ZVR5cGUKL0Jhc2VGb250L1ZlcmRhbmEKL0ZvbnREZXNjcmlwdG9yIDEyIDAgUgovRmlyc3RDaGFyIDAKL0xhc3RDaGFyIDI1NQovV2lkdGhzWwogMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMAogMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMAogMzUyIDM5NCA0NTkgODE4IDYzNiAxMDc2IDcyNyAyNjkgNDU0IDQ1NCA2MzYgODE4IDM2NCA0NTQgMzY0IDQ1NAogNjM2IDYzNiA2MzYgNjM2IDYzNiA2MzYgNjM2IDYzNiA2MzYgNjM2IDQ1NCA0NTQgODE4IDgxOCA4MTggNTQ1CiAxMDAwIDY4NCA2ODYgNjk4IDc3MSA2MzIgNTc1IDc3NSA3NTEgNDIxIDQ1NSA2OTMgNTU3IDg0MyA3NDggNzg3CiA2MDMgNzg3IDY5NSA2ODQgNjE2IDczMiA2ODQgOTg5IDY4NSA2MTUgNjg1IDQ1NCA0NTQgNDU0IDgxOCA2MzYKIDYzNiA2MDEgNjIzIDUyMSA2MjMgNTk2IDM1MiA2MjMgNjMzIDI3NCAzNDQgNTkyIDI3NCA5NzMgNjMzIDYwNwogNjIzIDYyMyA0MjcgNTIxIDM5NCA2MzMgNTkyIDgxOCA1OTIgNTkyIDUyNSA2MzUgNDU0IDYzNSA4MTggNTQ1CiA2MzYgNTQ1IDI2OSA2MzYgNDU5IDgxOCA2MzYgNjM2IDYzNiAxNTIxIDY4NCA0NTQgMTA3MCA1NDUgNjg1IDU0NQogNTQ1IDI2OSAyNjkgNDU5IDQ1OSA1NDUgNjM2IDEwMDAgNjM2IDk3NyA1MjEgNDU0IDk4MSA1NDUgNTI1IDYxNQogMzUyIDM5NCA2MzYgNjM2IDYzNiA2MzYgNDU0IDYzNiA2MzYgMTAwMCA1NDUgNjQ1IDgxOCA0NTQgMTAwMCA2MzYKIDU0MiA4MTggNTQyIDU0MiA2MzYgNjQwIDYzNiAzNjQgNjM2IDU0MiA1NDUgNjQ1IDEwMDAgMTAwMCAxMDAwIDU0NQogNjg0IDY4NCA2ODQgNjg0IDY4NCA2ODQgOTg0IDY5OCA2MzIgNjMyIDYzMiA2MzIgNDIxIDQyMSA0MjEgNDIxCiA3NzUgNzQ4IDc4NyA3ODcgNzg3IDc4NyA3ODcgODE4IDc4NyA3MzIgNzMyIDczMiA3MzIgNjE1IDYwNSA2MjAKIDYwMSA2MDEgNjAxIDYwMSA2MDEgNjAxIDk1NSA1MjEgNTk2IDU5NiA1OTYgNTk2IDI3NCAyNzQgMjc0IDI3NAogNjEyIDYzMyA2MDcgNjA3IDYwNyA2MDcgNjA3IDgxOCA2MDcgNjMzIDYzMyA2MzMgNjMzIDU5MiA2MjMgNTkyCl0KL0VuY29kaW5nL1dpbkFuc2lFbmNvZGluZwo+PgplbmRvYmoKMTIgMCBvYmoKPDwvVHlwZS9Gb250RGVzY3JpcHRvcgovQXNjZW50IDc2NQovQ2FwSGVpZ2h0IDcyNwovRGVzY2VudCAtMjA3Ci9GbGFncyAzMgovRm9udEJCb3hbLTU2MCAtMzAzIDE1MjMgMTA1MV0KL0ZvbnROYW1lL1ZlcmRhbmEKL0l0YWxpY0FuZ2xlIDAKL1N0ZW1WIDg3Ci9YSGVpZ2h0IDU0NQo+PgplbmRvYmoKMSAwIG9iago8PC9UeXBlL1BhZ2VzCi9Db3VudCAxCi9LaWRzWzIgMCBSCl0+PgplbmRvYmoKMTMgMCBvYmoKPDwvVHlwZS9DYXRhbG9nCi9QYWdlcyAxIDAgUgo+PgplbmRvYmoKeHJlZgowIDE0CjAwMDAwMDAwMDAgNjU1MzUgZiAKMDAwMDAwNTI5OCAwMDAwMCBuIAowMDAwMDAwNjQyIDAwMDAwIG4gCjAwMDAwMDAwMTUgMDAwMDAgbiAKMDAwMDAwMDYyMyAwMDAwMCBuIAowMDAwMDAxMDU4IDAwMDAwIG4gCjAwMDAwMDI0OTQgMDAwMDAgbiAKMDAwMDAwMzg4MiAwMDAwMCBuIAowMDAwMDAwNzUwIDAwMDAwIG4gCjAwMDAwMDA4NTEgMDAwMDAgbiAKMDAwMDAwMjMwMiAwMDAwMCBuIAowMDAwMDAzUjk1IDAwMDAwIG4gCjAwMDAwMDUxMTggMDAwMDAgbiAKMDAwMDAwNTM1MiAwMDAwMCBuIAp0cmFpbGVyCjw8L1NpemUgMTQKL1Jvb3QgMTMgMCBSCi9JbmZvIDkgMCBSCi9JRFs8RjIwNENBMUE5Nzg1ODdDRjE2QUFDQkNGQ0M4ODg5QkT+PEYyMDRDQTFBOTc4NTg3Q0YxNkFBQ0JDRkNDODg4OUJEPl0KPj4Kc3RhcnR4cmVmCjU0MDAKJSVFT0YL",
        "pre_alert_rows": [
            {
              "parcel_id": "WBDEM100073974019U",
              "package_barcode": "226003462045", 
              "seller_name": "Wildberries LLC",
              "seller_ioss_nr": "IM2760006126",
              "seller_street": "Koledino village 6 building 1",
              "seller_zipcode": "108823",
              "seller_city": "Podolsk",
              "seller_country_code": "RU",
              "transaction_type": "B2C",
              "buyer_name": "Marco Polo",
              "buyer_eori": null,
              "buyer_street": "Engelbertring 1",
              "buyer_zipcode": "59755",
              "buyer_city": "Berlin",
              "buyer_country_code": "DE",
              "quantity": "1",
              "weight": "2.29",
              "item_hs_code": "950300",
              "goods_description": "Book",
              "invoice_currency": "EUR",
              "invoice_amount": "7.23",
              "charges_currency": null,
              "other_charges": null
            },
            {"..."},
            {"..."}
        ],
      }'
```

> The above command returns JSON structured like this:

```
HTTP/1.1 200 Created
Content-Type:application/json;charset=UTF-8
```

```json
{
  "id": 3263,
  "number": "784-65428961",
  "reference": 71583,
  "total_weight": null,
  "total_bags": null,
  "status": "pre_upload",
  "status_changed": "2021-06-29T11:41:18.000000Z",
  "status_changed_human": "1 second ago",
  "inbound": 0,
  "outbound": 0,
  "job_state": "uploading",
  "date_received": "2021-06-29T11:41:18.000000Z",
  "updated_at": "2021-06-29T11:41:18.000000Z",
  "customer": "Global Freight System",
  "bags": [],
  "in_container": 0,
  "total": 1,
  "container_count": 0,
  "airline": {
    "id": 196,
    "prefix": "784",
    "code": "CZ",
    "name": "China Southern Airlines "
  }
}
```

This endpoint creates a new Waybill pre alert in OMNISHIP cross border. 

### HTTP Request

<span class="http-verb post">POST</span> `https://crossborder.omniship.eu/api/v2/waybills`

### Arguments

Attribute | Type                                    | Description
--------- |-----------------------------------------| ----------
customer_code | <span class="type">string</span>        | <span class="required">required</span> The unique customer code. This code should reflect a customer code in the database.
waybill_type | <span class="type">string</span>        | <span class="required">required</span> The type of waybill. Valid values are `air`, `road`, `train`, `other`
waybill_number | <span class="type">string</span>        | <span class="required">required</span> Unique number of the waybill. This number cannot already exist in the database for the same customer.
reference | <span class="type">string</span>        | <span class="required">required</span> Unique reference usually the ID of the external system where shipment is uploaded from.
customs_declaration | <span class="type">boolean</span>       | <span class="optional">optional</span> Indicates if OmniShip should process the customs declaration for this shipment. Default is `true`.
weight_unit | <span class="type">string</span>        | <span class="optional">optional</span> The weight unit used for the weights in the pre-alert. Valid values are `grams`, `kilograms`. When omitted or empty the default customer weight unit will be used.
waybill_document | <span class="type">base64_string</span> | <span class="required_if">Required If</span> `waybill_type` is `air` base64 encoded pdf file of the Waybill Document associated with the shipment.
pre_alert_rows | <span class="type">array</span>         | <span class="required">required</span> Line with details of the specific shipment. Each line must contain `parcel_id`, `package_barcode`, `seller_name`, `seller_ioss_nr`, `seller_street`, `seller_city`, `seller_country_code`, `transaction_type`, `buyer_name`, `buyer_street`, `buyer_city`, `buyer_country_code`, `item_hs_code`, `quantity`, `weight`, `item_hs_code`, `goods_description`, `invoice_currency`, `invoice_amount`.

### Pre Alert Row Parameters

Attribute | Type | Description
--------- | ------- | ---------
`parcel_id` | <span class="type">string</span> | <span class="required">required</span> Barcode of the package. Usually the final mile carrier barcode. Maximum 35 characters.
`package_barcode` | <span class="type">string</span> | <span class="required">required</span> Package Barcode for the shipment line.
`seller_name` | <span class="type">string</span> | <span class="required">required</span> (Company) name of the company of the seller. Maximum 70 characters.
`seller_ioss_nr` | <span class="type">string</span> | <span class="required">required</span> IOSS number of the seller. 12 Characters and must start with IM.
`seller_street` | <span class="type">number</span> | <span class="required">required</span> Street address of the of the seller. Maximum 70 characters.
`seller_zipcode` | <span class="type">number</span> | <span class="optional">optional</span> Zip code of the of the seller.
`seller_city` | <span class="type">string</span> | <span class="required">required</span> City or town of the of the seller. Maximum 35 characters
`seller_country_code` | <span class="type">string</span> | <span class="required">required</span> Country code of the of the seller. (needs to be ISO 3166 2-char code).
`transaction_type` | <span class="type">string</span> | <span class="required">required</span> Transaction type (B2C or C2C) of the package.
`buyer_name` | <span class="type">string</span> | <span class="required">required</span> Name of the of the package consignee. Maximum 70 characters.
`buyer_eori` | <span class="type">string</span> | <span class="optional">optional</span> Eori is the European Union registration and identification number used in all customs procedures performed by economic operators. Maximum 17 characters
`buyer_zipcode` | <span class="type">string</span> | <span class="optional">optional</span> Zip code of the of the package consignee.
`buyer_street` | <span class="type">string</span> | <span class="required">required</span> Street address of the package consignee. Maximum 70 characters.
`buyer_city` | <span class="type">string</span> | <span class="required">required</span> City or town of the of the package consignee. Maximum 35 characters
`buyer_country_code` | <span class="type">string</span> | <span class="required">required</span> Country code of the package consignee. (needs to be ISO 3166 2-char code).
`item_hs_code` | <span class="type">string</span> | <span class="required">required</span> HS code of the of the item(s) in the package. Must be included on the [152 GS-Code list](https://www.belastingdienst.nl/codeboek_sagitta/huidig/html/tabel-codeboek%2C%20onderdeel%20e-commerce-152.html) and not prohibited.
`quantity` | <span class="type">string</span> | <span class="required">required</span> Quantity of the of the item(s) in the package.
`weight` | <span class="type">string</span> | <span class="required">required</span> Weight of the of the item(s) in the package.
`goods_description` | <span class="type">string</span> | <span class="required">required</span> Description of the of the item(s) in the package. Maximum 512 characters.
`invoice_currency` | <span class="type">string</span> | <span class="required">required</span> Currency of the value of the item(s) in the package. 3 letter currency code.
`invoice_amount` | <span class="type">string</span> | <span class="required">required</span> Amount of the value of the item(s) in the package.
`charges_currency` | <span class="type">number</span> | <span class="optional">optional</span> Charges Currency of the value of the item(s) in the package.
`other_charges` | <span class="type">string</span> | <span class="optional">optional</span> Other charges of the value of the item(s) in the package.

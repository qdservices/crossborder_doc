## Create a Waybill

```shell
curl "https://cbe.vdhelm.com/api/v3/waybills"
  -X POST
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
  -d '{
        "masterWaybillNumber": "112-60318215",
        "transportType": "air",
        "grossWeight": 13.25,
        "parcelCount": 1,
        "bigBagCount": 1,
        "destinationFlightNumber": "CK210",
        "eta": "2024-05-26",
        "declarationType": "full",
        "waybillDocument": "JVBERi0xLjQKJeTjz9IKMyAwIG9iago8PC9MZW5ndGggNCAwIFIKL0ZpbHRlci9GbGF0ZURlY29kZQo+PgpzdHJlYW0KeJydlM1ymzAQx+96ij22B9uSAAnl5sbG02k+WpvJTE8dgmUPHQOJgHjch+ozdkUc18aQ4sIwArT72/9+AAOKJ8PLU+5QehCnhNXvBq8LPn8KyYBRCuEvMg0JtVZ253BTu9jTrMkzYS4w4QGjnkCGAqPJinwjtYe1oENfucg+WU48FW91RBmjwOriEK72r+czvAm3e8moQQHzFIQpqc1uyIdJHlepzkrIqvRRm4/hz1ePLhmY4TPhVFwk5UgBZ6wp4XZ+1y+so/w6rOO0l+6dsC51mmFDEy21QchKG53Fup8G6ey74LqXapDOefV1EZvkqUzyrF94X/r/G973z0qwKKOyKg6RRwFDTzoUQshzd44ZSLXftIw3QwR9zbdYxCU87mAWlXob7X4fUXk31Q6kI9uhwffre7h/0eYl0VsYwG2UJStdlCB9dyBQC/UUhSDZaFCMc0EZ9VUj7HkZbEQs4nETOB/9BfzA0grHY/8E1ZN8SuL87oaNAyG+TNnEV9N5Q44aOni0D6f09puIe7NDJKUeZkmldKiSnEoulNsLWk9bB3SdmE0BRZWUvVD15HSgoHefucvb+zyZYp/rZo9NmcQbXfRnem47czxbHGiwMnkK14sH+Jw+5absTxeinb6o0jQyO1jqeBOZyH6+PTXboeksRHPm3mN0JU4vYHSlF+zi/AqN5nqdFKX9sPGJ++KAxl/RH05bj5MKZW5kc3RyZWFtCmVuZG9iago0IDAgb2JqCjUzNgplbmRvYmoKMiAwIG9iago8PC9UeXBlL1BhZ2UKL1BhcmVudCAxIDAgUgovUmVzb3VyY2VzIDggMCBSCi9NZWRpYUJveFswIDAgODQxLjUgNTk0Ljc1XQovQ29udGVudHNbMyAwIFIgXQo+PgplbmRvYmoKOCAwIG9iago8PC9Qcm9jU2V0Wy9QREYvSW1hZ2VCL0ltYWdlQy9JbWFnZUkvVGV4dF0KL0ZvbnQ8PC9GMCA1IDAgUgovRjEgNiAwIFIKL0YyIDcgMCBSCj4+Cj4+CmVuZG9iago5IDAgb2JqCjw8L1N1YmplY3QgKEdXX0RFQ09fRllDT19PVkVSVklFVy5SRDEpCi9UaXRsZSAoR1dfREVDT19GWUNPX09WRVJWSUVXLlJEMSkKL0NyZWF0b3IgKEdhdGV3YXkgVjIpCi9BdXRob3IgKGVob2x0KQovQ3JlYXRpb25EYXRlIChEOjIwMjIwMTE3MTIwMTU1KzAxJzAwJykKL1Byb2R1Y2VyIChHV1BkZiAyLjIxIFwoQysrL1dpbjMyXCkpCj4+CmVuZG9iago1IDAgb2JqCjw8L1R5cGUvRm9udAovU3VidHlwZS9UcnVlVHlwZQovQmFzZUZvbnQvVmVyZGFuYS1Cb2xkCi9Gb250RGVzY3JpcHRvciAxMCAwIFIKL0ZpcnN0Q2hhciAwCi9MYXN0Q2hhciAyNTUKL1dpZHRoc1sKIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAKIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAKIDM0MiA0MDIgNTg3IDg2NyA3MTEgMTI3MiA4NjIgMzMyIDU0MyA1NDMgNzExIDg2NyAzNjEgNDgwIDM2MSA2ODkKIDcxMSA3MTEgNzExIDcxMSA3MTEgNzExIDcxMSA3MTEgNzExIDcxMSA0MDIgNDAyIDg2NyA4NjcgODY3IDYxNwogOTY0IDc3NiA3NjIgNzI0IDgzMCA2ODMgNjUwIDgxMSA4MzcgNTQ2IDU1NSA3NzEgNjM3IDk0OCA4NDcgODUwCiA3MzMgODUwIDc4MiA3MTAgNjgyIDgxMiA3NjQgMTEyOCA3NjQgNzM3IDY5MiA1NDMgNjg5IDU0MyA4NjcgNzExCiA3MTEgNjY4IDY5OSA1ODggNjk5IDY2NCA0MjIgNjk5IDcxMiAzNDIgNDAzIDY3MSAzNDIgMTA1OCA3MTIgNjg3CiA2OTkgNjk5IDQ5NyA1OTMgNDU2IDcxMiA2NTAgOTc5IDY2OSA2NTEgNTk3IDcxMSA1NDMgNzExIDg2NyA3MTEKIDcxMSA3MTEgMzMyIDcxMSA1ODcgMTA0OSA3MTEgNzExIDcxMSAxNzc3IDcxMCA1NDMgMTEzNSA3MTEgNjkyIDcxMQogNzExIDMzMiAzMzIgNTg3IDU4NyA3MTEgNzExIDEwMDAgNzExIDk2NCA1OTMgNTQzIDEwNjggNzExIDU5NyA3MzcKIDM0MiA0MDIgNzExIDcxMSA3MTEgNzExIDU0MyA3MTEgNzExIDk2NCA1OTggODUwIDg2NyA0ODAgOTY0IDcxMQogNTg3IDg2NyA1OTggNTk4IDcxMSA3MjEgNzExIDM2MSA3MTEgNTk4IDU5OCA4NTAgMTE4MiAxMTgyIDExODIgNjE3CiA3NzYgNzc2IDc3NiA3NzYgNzc2IDc3NiAxMDk0IDcyNCA2ODMgNjgzIDY4MyA2ODMgNTQ2IDU0NiA1NDYgNTQ2CiA4MzAgODQ3IDg1MCA4NTAgODUwIDg1MCA4NTAgODY3IDg1MCA4MTIgODEyIDgxMiA4MTIgNzM3IDczNSA3MTMKIDY2OCA2NjggNjY4IDY2OCA2NjggNjY4IDEwMTggNTg4IDY2NCA2NjQgNjY0IDY2NCAzNDIgMzQyIDM0MiAzNDIKIDY3OSA3MTIgNjg3IDY4NyA2ODcgNjg3IDY4NyA4NjcgNjg3IDcxMiA3MTIgNzEyIDcxMiA2NTEgNjk5IDY1MQpdCi9FbmNvZGluZy9XaW5BbnNpRW5jb2RpbmcKPj4KZW5kb2JqCjEwIDAgb2JqCjw8L1R5cGUvRm9udERlc2NyaXB0b3IKL0FzY2VudCA3NjUKL0NhcEhlaWdodCA3MjcKL0Rlc2NlbnQgLTIwNwovRmxhZ3MgMjYyMTc2Ci9Gb250QkJveFstNTUwIC0zMDMgMTcwNyAxMDcyXQovRm9udE5hbWUvVmVyZGFuYSMyMEJvbGQKL0l0YWxpY0FuZ2xlIDAKL1N0ZW1WIDE2NQovWEhlaWdodCA1NDgKPj4KZW5kb2JqCjYgMCBvYmoKPDwvVHlwZS9Gb250Ci9TdWJ0eXBlL1RydWVUeXBlCi9CYXNlRm9udC9DYWxpYnJpLUxpZ2h0Ci9Gb250RGVzY3JpcHRvciAxMSAwIFIKL0ZpcnN0Q2hhciAwCi9MYXN0Q2hhciAyNTUKL1dpZHRoc1sKIDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNwogNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3CiAyMjYgMzI2IDM4MCA0OTggNTA3IDcwNyA2NzAgMjE0IDI5OSAyOTkgNDk4IDQ5OCAyNDUgMzA2IDI0NSAzNjIKIDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyA1MDcgNTA3IDUwNyAyNjMgMjYzIDQ5OCA0OTggNDk4IDQ2MwogODkyIDU2MyA1MzUgNTM1IDYwNyA0ODkgNDYwIDYyNyA2MTkgNiA1NTQgODgxIDUwMSA0NjkgNDYzIDI5NyAzNjIgMjk3IDQ5OCA0OTgKIDI4NiA0NzEgNTIwIDQyNSA1MjAgNDk0IDI5OSA0NjkgNTIwIDIyMSAyMzAgNDQxIDIyMSA3OTEgNTIwIDUyMQogNTIwIDUyMCAzNDUgMzg3IDMyOSA1MjAgNDQwIDY5OSA0MTggNDQxIDM5NCAyOTkgNDUzIDI5OSA0OTggNDk4CiA1MDcgNDk4IDI0NSAyOTkgNDA5IDY3OSA0OTggNDk4IDM5MSAxMDI1IDQ1MyAzMzYgODYzIDQ5OCA0NjMgNDk4CiA0OTggMjQ1IDI0NSA0MDkgNDA5IDQ5OCA0OTggOTA1IDQ1NCA2OTcgMzg3IDMzNiA4NTQgNDk4IDM5NCA0NjkKIDIyNiAzMjYgNDk4IDUwNyA0OTggNTA3IDQ5OCA0OTggMzgwIDgzNCAzOTUgNDk4IDQ5OCAzMDYgNTA3IDM5NgogMzM3IDQ5OCAzMzUgMzM0IDI4NyA1NDIgNTgwIDI0NSAzMTAgMjQzIDQxNiA0OTggNjI1IDY2MSA2NjEgNDYzCiA1NjMgNTYzIDU2MyA1NjMgNTYzIDU2MyA3NTcgNTM1IDQ4OSA0ODkgNDg5IDQ4OSAyNDQgMjQ0IDI0NCAyNDQKIDYxNiA2MzggNjU0IDY1NCA2NTQgNjU0IDY1NCA0OTggNjU0IDYzNiA2MzYgNjM2IDYzNiA0NjkgNTA4IDUxMgogNDcxIDQ3MSA0NzEgNDcxIDQ3MSA0NzEgNzcyIDQyNSA0OTQgNDk0IDQ5NCA0OTQgMjIxIDIyMSAyMjEgMjIxCiA1MjAgNTIwIDUyMSA1MjEgNTIxIDUyMSA1MjEgNDk4IDUyMSA1MjAgNTIwIDUyMCA1MjAgNDQxIDUyMCA0NDEKXQovRW5jb2RpbmcvV2luQW5zaUVuY29kaW5nCj4+CmVuZG9iagoxMSAwIG9iago8PC9UeXBlL0ZvbnREZXNjcmlwdG9yCi9Bc2NlbnQgNzUwCi9DYXBIZWlnaHQgNjMyCi9EZXNjZW50IC0yNTAKL0ZsYWdzIDMyCi9Gb250QkJveFstNTExIC0yNjkgMTMwOSA5NTJdCi9Gb250TmFtZS9DYWxpYnJpIzIwTGlnaHQKL0l0YWxpY0FuZ2xlIDAKL1N0ZW1WIDcxCi9YSGVpZ2h0IDQ2Mgo+PgplbmRvYmoKNyAwIG9iago8PC9UeXBlL0ZvbnQKL1N1YnR5cGUvVHJ1ZVR5cGUKL0Jhc2VGb250L1ZlcmRhbmEKL0ZvbnREZXNjcmlwdG9yIDEyIDAgUgovRmlyc3RDaGFyIDAKL0xhc3RDaGFyIDI1NQovV2lkdGhzWwogMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMAogMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMCAxMDAwIDEwMDAgMTAwMAogMzUyIDM5NCA0NTkgODE4IDYzNiAxMDc2IDcyNyAyNjkgNDU0IDQ1NCA2MzYgODE4IDM2NCA0NTQgMzY0IDQ1NAogNjM2IDYzNiA2MzYgNjM2IDYzNiA2MzYgNjM2IDYzNiA2MzYgNjM2IDQ1NCA0NTQgODE4IDgxOCA4MTggNTQ1CiAxMDAwIDY4NCA2ODYgNjk4IDc3MSA2MzIgNTc1IDc3NSA3NTEgNDIxIDQ1NSA2OTMgNTU3IDg0MyA3NDggNzg3CiA2MDMgNzg3IDY5NSA2ODQgNjE2IDczMiA2ODQgOTg5IDY4NSA2MTUgNjg1IDQ1NCA0NTQgNDU0IDgxOCA2MzYKIDYzNiA2MDEgNjIzIDUyMSA2MjMgNTk2IDM1MiA2MjMgNjMzIDI3NCAzNDQgNTkyIDI3NCA5NzMgNjMzIDYwNwogNjIzIDYyMyA0MjcgNTIxIDM5NCA2MzMgNTkyIDgxOCA1OTIgNTkyIDUyNSA2MzUgNDU0IDYzNSA4MTggNTQ1CiA2MzYgNTQ1IDI2OSA2MzYgNDU5IDgxOCA2MzYgNjM2IDYzNiAxNTIxIDY4NCA0NTQgMTA3MCA1NDUgNjg1IDU0NQogNTQ1IDI2OSAyNjkgNDU5IDQ1OSA1NDUgNjM2IDEwMDAgNjM2IDk3NyA1MjEgNDU0IDk4MSA1NDUgNTI1IDYxNQogMzUyIDM5NCA2MzYgNjM2IDYzNiA2MzYgNDU0IDYzNiA2MzYgMTAwMCA1NDUgNjQ1IDgxOCA0NTQgMTAwMCA2MzYKIDU0MiA4MTggNTQyIDU0MiA2MzYgNjQwIDYzNiAzNjQgNjM2IDU0MiA1NDUgNjQ1IDEwMDAgMTAwMCAxMDAwIDU0NQogNjg0IDY4NCA2ODQgNjg0IDY4NCA2ODQgOTg0IDY5OCA2MzIgNjMyIDYzMiA2MzIgNDIxIDQyMSA0MjEgNDIxCiA3NzUgNzQ4IDc4NyA3ODcgNzg3IDc4NyA3ODcgODE4IDc4NyA3MzIgNzMyIDczMiA3MzIgNjE1IDYwNSA2MjAKIDYwMSA2MDEgNjAxIDYwMSA2MDEgNjAxIDk1NSA1MjEgNTk2IDU5NiA1OTYgNTk2IDI3NCAyNzQgMjc0IDI3NAogNjEyIDYzMyA2MDcgNjA3IDYwNyA2MDcgNjA3IDgxOCA2MDcgNjMzIDYzMyA2MzMgNjMzIDU5MiA2MjMgNTkyCl0KL0VuY29kaW5nL1dpbkFuc2lFbmNvZGluZwo+PgplbmRvYmoKMTIgMCBvYmoKPDwvVHlwZS9Gb250RGVzY3JpcHRvcgovQXNjZW50IDc2NQovQ2FwSGVpZ2h0IDcyNwovRGVzY2VudCAtMjA3Ci9GbGFncyAzMgovRm9udEJCb3hbLTU2MCAtMzAzIDE1MjMgMTA1MV0KL0ZvbnROYW1lL1ZlcmRhbmEKL0l0YWxpY0FuZ2xlIDAKL1N0ZW1WIDg3Ci9YSGVpZ2h0IDU0NQo+PgplbmRvYmoKMSAwIG9iago8PC9UeXBlL1BhZ2VzCi9Db3VudCAxCi9LaWRzWzIgMCBSCl0+PgplbmRvYmoKMTMgMCBvYmoKPDwvVHlwZS9DYXRhbG9nCi9QYWdlcyAxIDAgUgo+PgplbmRvYmoKeHJlZgowIDE0CjAwMDAwMDAwMDAgNjU1MzUgZiAKMDAwMDAwNTI5OCAwMDAwMCBuIAowMDAwMDAwNjQyIDAwMDAwIG4gCjAwMDAwMDAwMTUgMDAwMDAgbiAKMDAwMDAwMDYyMyAwMDAwMCBuIAowMDAwMDAxMDU4IDAwMDAwIG4gCjAwMDAwMDI0OTQgMDAwMDAgbiAKMDAwMDAwMzg4MiAwMDAwMCBuIAowMDAwMDAwNzUwIDAwMDAwIG4gCjAwMDAwMDA4NTEgMDAwMDAgbiAKMDAwMDAwMjMwMiAwMDAwMCBuIAowMDAwMDAzUjk1IDAwMDAwIG4gCjAwMDAwMDUxMTggMDAwMDAgbiAKMDAwMDAwNTM1MiAwMDAwMCBuIAp0cmFpbGVyCjw8L1NpemUgMTQKL1Jvb3QgMTMgMCBSCi9JbmZvIDkgMCBSCi9JRFs8RjIwNENBMUE5Nzg1ODdDRjE2QUFDQkNGQ0M4ODg5QkT+PEYyMDRDQTFBOTc4NTg3Q0YxNkFBQ0JDRkNDODg4OUJEPl0KPj4Kc3RhcnR4cmVmCjU0MDAKJSVFT0YL"
      }'
```

> The above command returns JSON structured like this:

```
HTTP/1.1 201 Created
Content-Type:application/json;charset=UTF-8
```

```json
{
  "data": {
    "id": "1cb3480a-86d3-44f2-a36d-f082e501fd37",
    "masterWaybillNumber": "112-60318215",
    "transportType": "air",
    "customer": "Acme",
    "customer_code": "ACE",
    "status": "pre_upload",
    "statusChangeUtc": "2024-04-24T07:03:54+00:00",
    "statusChangeLocalTime": "2024-04-24T09:03:54+02:00",
    "statusChangedHuman": "1 second ago",
    "bigBagCount": 1,
    "grossWeight": 13.25,
    "airline": {
      "trackingLink": "https:\/\/www.skyteam.com\/en\/cargo\/track-shipment\/",
      "name": "China Cargo Airlines",
      "prefix": "112",
      "code": "MU",
      "copyNumber": "60318215"
    },
    "destinationFlightNumber": "KE0925",
    "eta": "2024-05-25T22:00:00.000000Z",
    "declarationType": "full",
    "parcels": []
  }
}
```

This endpoint creates a new Waybill pre alert in <span style="font-weight:bold">ALL<span style="color: #d83636;">IN</span>E</span> cross border. 

### HTTP Request

<span class="http-verb post">POST</span> `https://cbe.vdhelm.com/api/v3/waybills`

### Arguments

| Attribute               | Type                                    | Description                                                                                                                                                                                                                                                        |
|-------------------------|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| masterWaybillNumber     | <span class="type">string</span>        | <span class="required">required</span> Unique number of the waybill. This number cannot already exist in the database for the same customer.                                                                                                                       |
| reference               | <span class="type">string</span>        | <span class="optional">optional</span> Unique reference/id of the waybill. The reference cannot already exist in the database for the same customer. If set the reference will be the ID to reference the Waybill in all requests further in the Waybill lifecycle |
| customerCode            | <span class="type">string</span>        | The unique customer code. This code should reflect a customer code in the database. Only <span class="required_if">required if</span> account has sub-customers.                                                                                                   | 
| transportType           | <span class="type">string</span>        | <span class="required">required</span> The type of waybill. Valid values are `air`, `road`, `train`, `other`                                                                                                                                                       |
| grossWeight             | <span class="type">float</span>         | <span class="required">required</span> The given gross weight for the shipment. Should be the same as the gross weight on the Air Waybill copy.                                                                                                                    |
| parcelCount             | <span class="type">integer</span>       | <span class="required">required</span> The number of parcels contained in the shipment.                                                                                                                                                                            |
| bigBagCount             | <span class="type">integer</span>       | <span class="required">required</span> The number of bigBags/Boxes/Units contained in the shipment.                                                                                                                                                                |
| destinationFlightNumber | <span class="type">string</span>        | <span class="optional">optional</span> The incoming flight number to the destination airport. For the VDH warehouse the destination airport is Schiphol (AMS).                                                                                                     |
| eta                     | <span class="type">date</span>          | <span class="optional">optional</span> The estimated arrival date at the destination airport. The date should be in the timezone of the destination in format `yyyy-mm-dd`.                                                                                        |
| declarationType         | <span class="type">string</span>        | <span class="optional">optional</span> Indicates if VDH should process the customs declaration for this shipment. Valid values are `full`, `partial`, `none`  Default is `full`.                                                                                   | 
| waybillDocument         | <span class="type">base64_string</span> | <span class="required_if">Required If</span> `waybill_type` is `air` base64 encoded pdf file of the Waybill Document associated with the shipment.                                                                                                                 |


## Retrieve a Specific Waybill

```shell
curl "https://crossborder.omniship.eu/api/v2/waybills/85"
  -H "Authorization: FkihCtzyXWvutSRUaaEupN8hvABcDefgHI6lJKvv"
  -H "Content-Type: application/json"
```

> The above command returns JSON structured like this:

```
HTTP/1.1 200 OK
Content-Type:application/json;charset=UTF-8
```
```json
{
  "id": 85,
  "type": "air",
  "number": "784-65428955",
  "reference": null,
  "total_weight": 3410,
  "status": "part_out",
  "status_changed": "2022-02-21T00:29:07.000000Z",
  "status_changed_human": "11 hours ago",
  "inbound_complete": true,
  "total_parcels": 13,
  "parcels_inbound": 4,
  "parcels_inbound_percentage": "30.77%",
  "parcels_released": 13,
  "parcels_released_percentage": "100%",
  "parcels_outbound": 9,
  "parcels_outbound_percentage": "69.23%",
  "date_received": "2022-02-21T00:03:00.000000Z",
  "updated_at": "2022-02-21T00:29:07.000000Z",
  "customer": "Global Freight Services",
  "parcels": [
    {
      "id": 35322300,
      "bag_grade_id": 4454090,
      "bag_reference": "IHB4202093070",
      "parcel_barcode": "IHB4202093070",
      "country": "Spain",
      "country_code": "ES",
      "shipping_method": "CORREOSEXPRESS",
      "inbound": false,
      "outbound": true,
      "weight": 400,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:25:42.000000Z",
      "status_changed_human": "11 hours ago",
      "container_barcode": "C2022-0000248",
      "items": 2
    },
    {
      "id": 35322301,
      "bag_grade_id": 4454091,
      "bag_reference": "IHB4202094040",
      "parcel_barcode": "IHB4202094040",
      "country": "Netherlands",
      "country_code": "NL",
      "shipping_method": "MONDIAL RELAY",
      "inbound": false,
      "outbound": true,
      "weight": 130,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:25:49.000000Z",
      "status_changed_human": "11 hours ago",
      "container_barcode": "C2022-0000246",
      "items": 1
    },
    {
      "id": 35322302,
      "bag_grade_id": 4454092,
      "bag_reference": "IHB4202102130",
      "parcel_barcode": "IHB4202102130",
      "country": "Spain",
      "country_code": "ES",
      "shipping_method": "CORREOSEXPRESS",
      "inbound": false,
      "outbound": true,
      "weight": 90,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:25:42.000000Z",
      "status_changed_human": "11 hours ago",
      "container_barcode": "C2022-0000248",
      "items": 1
    },
    {
      "id": 35322303,
      "bag_grade_id": 4454093,
      "bag_reference": "IHB4202102280",
      "parcel_barcode": "IHB4202102280",
      "country": "France",
      "country_code": "FR",
      "shipping_method": "Colisprive",
      "inbound": false,
      "outbound": true,
      "weight": 120,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:25:52.000000Z",
      "status_changed_human": "11 hours ago",
      "container_barcode": "C2022-0000247",
      "items": 1
    },
    {
      "id": 35322304,
      "bag_grade_id": 4454094,
      "bag_reference": "IHB4202102550",
      "parcel_barcode": "IHB4202102550",
      "country": "France",
      "country_code": "FR",
      "shipping_method": "Colisprive",
      "inbound": false,
      "outbound": true,
      "weight": 540,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:25:52.000000Z",
      "status_changed_human": "11 hours ago",
      "container_barcode": "C2022-0000247",
      "items": 2
    },
    {
      "id": 35322305,
      "bag_grade_id": 4454095,
      "bag_reference": "IHB4202102770",
      "parcel_barcode": "IHB4202102770",
      "country": "Estonia",
      "country_code": "EE",
      "shipping_method": "VENIPAK",
      "inbound": true,
      "outbound": false,
      "weight": 250,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:11:28.000000Z",
      "status_changed_human": "12 hours ago",
      "container_barcode": "C2022-0000243",
      "items": 2
    },
    {
      "id": 35322306,
      "bag_grade_id": 4454096,
      "bag_reference": "IHB4202102950",
      "parcel_barcode": "IHB4202102950",
      "country": "Estonia",
      "country_code": "EE",
      "shipping_method": "VENIPAK",
      "inbound": true,
      "outbound": false,
      "weight": 160,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:11:28.000000Z",
      "status_changed_human": "12 hours ago",
      "container_barcode": "C2022-0000243",
      "items": 2
    },
    {
      "id": 35322307,
      "bag_grade_id": 4454097,
      "bag_reference": "IHB4202103120",
      "parcel_barcode": "IHB4202103120",
      "country": "Latvia",
      "country_code": "LV",
      "shipping_method": "VENIPAK",
      "inbound": true,
      "outbound": false,
      "weight": 250,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:11:28.000000Z",
      "status_changed_human": "12 hours ago",
      "container_barcode": "C2022-0000243",
      "items": 2
    },
    {
      "id": 35322308,
      "bag_grade_id": 4454098,
      "bag_reference": "IHB4202103380",
      "parcel_barcode": "IHB4202103380",
      "country": "Latvia",
      "country_code": "LV",
      "shipping_method": "VENIPAK",
      "inbound": true,
      "outbound": false,
      "weight": 430,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:11:28.000000Z",
      "status_changed_human": "12 hours ago",
      "container_barcode": "C2022-0000243",
      "items": 2
    },
    {
      "id": 35322309,
      "bag_grade_id": 4454099,
      "bag_reference": "IHB4202103970",
      "parcel_barcode": "IHB4202103970",
      "country": "Croatia",
      "country_code": "HR",
      "shipping_method": "Meest Hungary",
      "inbound": false,
      "outbound": true,
      "weight": 290,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:28:32.000000Z",
      "status_changed_human": "11 hours ago",
      "container_barcode": "C2022-0000244",
      "items": 2
    },
    {
      "id": 35322310,
      "bag_grade_id": 4454100,
      "bag_reference": "IHB4202104260",
      "parcel_barcode": "IHB4202104260",
      "country": "Croatia",
      "country_code": "HR",
      "shipping_method": "Meest Hungary",
      "inbound": false,
      "outbound": true,
      "weight": 250,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:28:32.000000Z",
      "status_changed_human": "11 hours ago",
      "container_barcode": "C2022-0000244",
      "items": 2
    },
    {
      "id": 35322311,
      "bag_grade_id": 4454101,
      "bag_reference": "IHB4202106550",
      "parcel_barcode": "IHB4202106550",
      "country": "Germany",
      "country_code": "DE",
      "shipping_method": "HERMES",
      "inbound": false,
      "outbound": true,
      "weight": 300,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:24:05.000000Z",
      "status_changed_human": "11 hours ago",
      "container_barcode": "C2022-0000245",
      "items": 1
    },
    {
      "id": 35322312,
      "bag_grade_id": 4454102,
      "bag_reference": "IHB4202106680",
      "parcel_barcode": "IHB4202106680",
      "country": "Germany",
      "country_code": "DE",
      "shipping_method": "HERMES",
      "inbound": false,
      "outbound": true,
      "weight": 200,
      "customs_status": "released",
      "status_changed": "2022-02-21T00:24:05.000000Z",
      "status_changed_human": "11 hours ago",
      "container_barcode": "C2022-0000245",
      "items": 2
    }
  ],
  "total_bags": 13,
  "container_count": 6,
  "airline": {
    "id": 1,
    "prefix": "074",
    "code": "CZ",
    "name": "China Southern",
    "ground_handler_code": "Dnata"
  }
}
```

This endpoint retrieves a specific Waybill.

### HTTP Request

<span class="http-verb get">GET</span> `https://crossborder.omniship.eu/api/v2/waybills/<ID>`

### URL Parameters

| Parameter | Description           |
|-----------|-----------------------|
| ID        | The ID of the Waybill |

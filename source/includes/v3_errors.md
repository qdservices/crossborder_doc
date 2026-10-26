# Errors

The Cross Border API uses the following error codes:


| Error Code | Meaning                                                                                                                          |
|------------|----------------------------------------------------------------------------------------------------------------------------------|
| 401        | Unauthorized -- Your API token is missing or wrong.                                                                              |
| 402        | Payment Required -- Your clearance balance is depleted. Top up your balance to resume pre-alert uploads.                         |
| 403        | Forbidden -- The waybill is not yours, or its current state does not allow the action (for example deleting a confirmed waybill). |
| 404        | Not Found -- The specified resource could not be found.                                                                          |
| 405        | Method Not Allowed -- The endpoint does not accept this HTTP method.                                                             |
| 422        | Unprocessable Entity -- The request contains invalid data. The response lists the errors per field.                              |
| 429        | Too Many Requests -- More than 10,000 requests per minute.                                                                       |
| 500        | Internal Server Error -- We had a problem with our server. Try again later.                                                      |
| 503        | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.                                        |

> A 422 response looks like this:

```json
{
  "message": "The items.0.invoice currency XYZ is invalid. (and 1 more error)",
  "errors": {
    "items.0.invoiceCurrency": ["The items.0.invoice currency XYZ is invalid."],
    "sellerDetails.iossNumber": ["The seller details.ioss number field is required."]
  }
}
```

A `422` response holds a `message` and an `errors` object. Each key of `errors` is the path of the field in your request (for example `items.0.hsCode` for the HS code of the first item) and its value is a list of messages.

A `402` or `403` response holds an `error` object with a `message`:

```json
{
  "error": {
    "message": "The current state of the waybill does not allow api deletion of the waybill."
  }
}
```

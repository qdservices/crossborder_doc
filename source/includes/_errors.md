# Errors

The Cross Border API uses the following error codes:


| Error Code | Meaning                                                                                                |
|------------|--------------------------------------------------------------------------------------------------------|
| 400        | Bad Request -- Your request is invalid.                                                                |
| 401        | Unauthorized -- Your API key is wrong.                                                                 |
| 403        | Forbidden -- The resource requested is hidden for administrators only.                                 |
| 404        | Not Found -- The specified resource could not be found.                                                |
| 405        | Method Not Allowed -- You tried to access a kitten with an invalid method.                             |
| 406        | Not Acceptable -- You requested a format that isn't json.                                              |
| 410        | Gone -- The resource requested has been removed from our servers.                                      |
| 422        | Unprocessable Entity -- The server was unable to process the request because it contains invalid data. |
| 429        | Too Many Requests -- You're requesting too many resources.                                             |
| 500        | Internal Server Error -- We had a problem with our server. Try again later.                            |
| 503        | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.              |

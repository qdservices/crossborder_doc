# Webhooks

<span style="font-weight: bold">ALL<span style="color: #d83636;">IN</span>E</span> can send webhook events to notify your application when a waybill or parcel changes status, so you do not need to poll our API. Your account representative sets up the URL that receives the events.

Each event is sent as an HTTP `POST` with a JSON body. Your endpoint should answer with a `2xx` status within 3 seconds; otherwise the event is sent again, up to 3 attempts in total, with an increasing delay between them.

### Verifying the signature

Every event carries the header `X-ALLINE-SIGNATURE`: the HMAC-SHA256 of the raw request body, hex encoded, with your signing key as the key. You get the signing key from your account representative. Compute the same HMAC over the body you received and compare it with the header to check that the event comes from <span style="font-weight: bold">ALL<span style="color: #d83636;">IN</span>E</span> and was not changed.

```shell
# PHP example
$expected = hash_hmac('sha256', $rawBody, $signingKey);
$valid = hash_equals($expected, $request->header('X-ALLINE-SIGNATURE'));
```

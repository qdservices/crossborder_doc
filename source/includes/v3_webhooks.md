# Webhooks

This guide will walk you through the webhooks functionality to obtain messages about shipment events. Messages are sent on triggering the following events:

The CBE tool can send webhook events to notify your application when a particular event has occurred. 
If you subscribe to the webhook to receive shipment status updates, you will be notified about the new status without polling our API.

The payload for each webhook event will include information about the related API response. Your provided endpoint should be set up to receive an HTTP POST request and must always return a 200 HTTP response.|

To prevent your application against a replay attack, we recommend that you verify all incoming webhook events by validating our unique signature, X-VDH-SIGNATURE, in the headers.

The signature is a token that can be decoded with the value of your secret_key. You can get it from your account representative. It will always be a hash string starting with webh_.


 






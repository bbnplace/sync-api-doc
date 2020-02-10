# Setting Up WebHooks

Webhooks are URLs where sms, calls logs and sms reports for your dedicated number will be sent. After you setup webhooks incoming resources for that number will be forwarded to the appropriate webhooks.

Although there are API endpoints for fetching Sent SMS Status Report, Inbound SMS, Inbound Call Reports and Outbound Call Reports - it is by far more efficient to provide a webhook where Cecula Sync will forward resources as they become available.

To setup webhooks, Login to the Sync Platform and click the ` webhook ` Menu.

> For comprehensive guide (with examples and code snippets for your programming language) on How to Send SMS, Send Calls and other API Features, Refer to the [API Reference](https://documenter.getpostman.com/view/3869433/SWTHaaiY?version=latest#4e330491-b13e-473f-9173-36ff1a3796d4).

### Data Format For Each WebHook

All resources are sent as Input Streams in JSON format.


#### Inbound SMS Format

```json
{
    "originator":"+2348183172770",
    "receiver":"08176470634",
    "message":"One love",
    "timeReceived":"2020/02/01 07:37"
}
```

#### Sent SMS Report Format

```json
{
    "messageId":"16276",
    "originator":"08176470634",
    "receiver":"2348183172770",
    "status":"DELIVERED",
    "sendTime":"2020/02/01 07:37",
    "doneTime":"2020/02/01 07:37"
}
```

#### Inbound Call Notification Format

```json
{
    "originator":"08183172770",
    "receiver":"08176470634",
    "callDuration":"0",
    "callTime":"2020/02/02 01:08"
}
```

#### Outbound Call Status Format

```json
{
    "callId":"2020012445",
    "originator":"08176470634",
    "receiver":"+2348183172770",
    "status": "ANSWERED",
    "callTime":"2020/02/01 08:01"
}
```

### JSON Keys Definition

Key | Meaning
---------|----------
 originator | The mobile number number a call of message originated from 
 receiver | The mobile number that received the call of message 
 messageId | A tracking number or identifier for a sent message 
 message | The message content in case of outbound or inbound sms 
 callId | A tracking number or identifier for an initiated call 
 callDuration | The length of the call. 
 callTime | The time when call was initiated (in an outbound call) or received (in an inbound call) 
 sendTime | The time when an SMS broadcast was made 
 doneTime | Time when an SMS broadcast received it's final status report
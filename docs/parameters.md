# Parameters

The table below defines the fields that are used on Cecula Sync API.

#### Request Properties

Field | Data Type | Meaning
---------|----------|---------
 receiver | String | The destination mobile number a call of sms will be terminated to
 recipients | String | The destination of mobile numbers a message will be terminated to. Multiple numbers should be seperated with comma (,) **Note:** Currently, multiple receivers only applies for sms.
 text | String | The body of the message to be sent or set in auto-responders. Text supports up to a maximum of 1530 characters.

 #### Response Properties

 Field | Data Type | Meaning
---------|----------|---------
 receiver | String | The destination mobile number a call of sms will be terminated to
 recipient | String | The destination mobile number an sms will be (or was) terminated to
 message | String | The details of a returned statusCode
 reports | Array | An array of message recipients objects. Each object has two properties **recipient** and **trackingId**
 trackingId | Integer | A unique identifier assigned to a receiver for delivery tracking and reporting purpose
 originator | String | The number a call of message is sent from. Your dedicated number in the case of Outbound Call or SMS. The other party's number in the case of an Inbound Call or SMS.
 status | String | The state of a sent SMS or Call. See full list of statuses in the **Statuses** section
 statusCode | String | Some request like Message Sending return a code which notifies you of the issue with broadcast or if message was successfully sent
 callId | Integer | A unique identifier (similar to trackingId) assigned to a call **receiver** for tracking and reporting purpose.
 callTime | DateTime | The time when a call was initiated (for outbound call) or number received call request (For Inbound Call)
 duration | Integer | The length (in seconds) of an outbound or inbound call
 sendTime | DateTime | The time when a message was broadcasted
 doneTime | DateTime | The time when the final delivery report for message was received.
 timeReceived | DateTime | The time when an Inbound SMS is received
 balance | Double | Your Cecula Credit balance
 subscriptionStatus | String | The status of your subscription
 subscriptionPlan | String | The plan a your have subscribed to
 expiryDate | DateTime | The date when your subscription will expire
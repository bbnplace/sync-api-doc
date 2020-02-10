# Call Based Two-Factor Authentication

Call 2FA is a 2FA method where your app / server initiates a call to the mobile number you have received through on a web or mobile app and intend to verify. When the call is answered a feedback is sent to your webhook.

### Outbound Call Method

In practice, you would want to use this to verify that the mobile number supplied to you is installed on same device where your app has been installed. So you follow the these steps:


1. Receive number supplied by user on your server
2. Initiate a phone call from the server-side script
3. Answer the phone call with your app (and end the call within 2 seconds if call is not automatically ended)
4. When you answer call, an acknowledgement will be sent to your **Outbound Call Status** webhook.
5. The mobile number on device where you app is installed has been verified. You may (optionally) send a receipt from your app to your server

> **PRE-REQUISITE:**
> 
> You must have programmed your app to:
> 1. Llisten for and answer calls from your dedicated number
> 2. Check your device call log for call from your dedicated number within the minute (There's a slim chance that the app user might answer the call before your app)

- [See API Reference for Sample Code for Making Calls](url)
- [Setup Webhook for receiving Outbound Call Status](url)
- [See JSON Format for Outbound Call Status Webhook](url)

### Inbound Call Method

As an alternative to dialing a user's number to Verify, you could setup a count down on your website and ask user to (for free) call your dedicated number (while the number is being displayed on the website).

Steps:
1. Start a countdown on the website with a note requesting your app user to call your dedicated number;
2. When your app user calls your dedicated number, the message is sent to your webhook;
3. Your server could notify the user over WebSocket or your client-side app can query server for the call;
4. Once client submits the number when call is received, a success message is returned to the client.

> **PRE-REQUISITE:**
>
> You must have programmed the client-side (web app) to submit the number at intervals while the countdown is ongoing until a success or failure message is received. Then the countdown stops.

- [Setup WebHook For Receiving Inbound Calls](url)
- [See JSON Format Data for Inbound Call](url)

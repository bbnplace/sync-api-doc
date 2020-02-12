# Authentication

Every request to Cecula Sync Cloud API requires Authentication. The first steps to take will be to login to the Cecula Sync Platform and Generate your API Key.

An API Key encapsulates your credentials and your Dedicated number. Therefore, there will be no need to specify **originator** when sending a message, making a call or any other request.

Each dedicated number you host on Cecula Sync Cloud requires a sperate API Key.

An API Key looks like this:
>**CCL.BvDwEv6oQyq7-wT.390JYJYz8Y6NftIAgjLTPppW**

To use the API Key you set the Authorization headers like this:
>**Authorization: Bearer CCL.BvDwEv6oQyq7-wT.390JYJYz8Y6NftIAgjLTPppW**

An attempt to make a request to a resource without providing authorization header or providing an invalid API Key will return HTTP **401 Unauthorized** error.

An API Key should be stored secretly within your application. If at any time you feel your API Key has been compromised, you should immediately login to the Cecula Sync Platform and generate a new API Key.
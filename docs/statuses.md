# Statuses

Status Codes are codes returned when you query a Sync endpoint for Message or Call Status


### SMS Statuses

Response | Interpretation 
---------|----------
 DELIVERED | Message has been delivered to receiver's device 
 FAILED | Message could not be delivered to receiver's device 
 EXPIRED | Message could not be delivered to receiver after 24 hours 
 SENT | Message has been sent to telecoms network. Awaiting delivery confirmation 
 QUEUED | Message has not been sent to Operator


 ### Call Statuses


Response | Interpretation
---------|----------
 ANSWERED | Call was answered by the receiver 
 NO ANSWERED | Call was not answered by receiver
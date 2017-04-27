# WebHooks

Incoming campaigns allow WebHooks to be added. If a WebHook is enabled for an incoming campaign, our server will send a POST request to your server at the time of receipt:

## POST Parameters

Parameter | Description
--------- | -----------
from | Contains the phone number this message came from
message | Contains the message the user has sent


## Use Cases

1. Generate coupons using a POS system or eCommerce API. 
2. Send different responses depending on time of day, number of messages recieved, or number of times a specific user has sent you a message.

##Response
The entire body of the response will be used to respond to the text message.

```php
header('Content-Type: application/json');
date_default_timezone_set('America/New_York');

$from = $_POST['from'];
$message = $_POST['message'];

echo "Hey ".$from." here's a dynamic message! You sent me a message saying '".$message."' and the current date is ".date("h:i:sa");
```

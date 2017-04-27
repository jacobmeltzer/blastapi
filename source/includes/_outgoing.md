# Outgoing Campaigns

The Blast API allows developers to get and send outgoing campaigns. Outgoing campaigns can be used to send targeted text messages to different lists and demographics. We currently support filtering by state, income range, age range, and contact list.

## List All Outgoing Campaigns

```shell
curl "http://24b3f761.ngrok.io/api/outgoing"
  -u username:key
```

> The above command returns JSON structured like this:

```json
{
   "campaigns":[
      {
         "id":4,
         "date":{
            "year":2017,
            "month":3,
            "dayOfMonth":26,
            "hourOfDay":20,
            "minute":5,
            "second":4
         },
         "name":"Some Outgoing Campaign",
         "message":"Enjoy another outgoing campaign!",
         "lists":[

         ],
         "states":[

         ],
         "ageRange":{
            "lowerBound":{
               "endpoint":30
            },
            "upperBound":{
               "endpoint":50
            }
         },
         "incomeRange":{
            "lowerBound":{
               "endpoint":35458
            },
            "upperBound":{
               "endpoint":75853
            }
         },
         "contacts":[

         ]
      }
   ]
}
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve


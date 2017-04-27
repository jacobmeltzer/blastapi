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

This gets all outgoing campaigns in the account.

### HTTP Request

`GET http://24b3f761.ngrok.io/api/outgoing`

### Query Parameters
No query parameters are required for this API call.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Outgoing Campaign


```shell
curl "http://24b3f761.ngrok.io/api/outgoing/<ID>"
  -u username:key
```

> The above command returns JSON structured like this:

```json
{  
   "error":"",
   "message":"",
   "campaign":{  
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
         {  
            "id":5,
            "name":"Yet Another Contact List",
            "date":{  
               "year":2017,
               "month":3,
               "dayOfMonth":26,
               "hourOfDay":19,
               "minute":59,
               "second":58
            },
            "contacts":[  
               {  
                  "id":1,
                  "name":"John Smith",
                  "phoneNumber":{  
                     "rawNumber":"+14435401295"
                  },
                  "date":{  
                     "year":2017,
                     "month":3,
                     "dayOfMonth":26,
                     "hourOfDay":20,
                     "minute":0,
                     "second":11
                  },
                  "address":{  
                     "street":"Willowcrest Cir",
                     "city":"Baltimore",
                     "state":"MD",
                     "postalCode":"21209",
                     "country":"United States"
                  },
                  "gender":"",
                  "ageRange":{  
                     "lowerBound":{  
                        "endpoint":0
                     },
                     "upperBound":{  
                        "endpoint":0
                     }
                  },
                  "incomeRange":{  
                     "lowerBound":{  
                        "endpoint":60000
                     },
                     "upperBound":{  
                        "endpoint":80000
                     }
                  }
               }
            ]
         }
      ],
      "states":[  
         "RI"
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
}
```

This code retrieves a specific outgoing campaign.

### HTTP Request

`POST http://24b3f761.ngrok.io/api/outgoing/delete`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the outgoing campaign to retrieve.

## Delete Outgoing Campaigns

```shell
curl "http://24b3f761.ngrok.io/api/outgoing"
  -u username:key
  -d "id=1"
```

> The above command returns JSON structured like this:

```json
{  
   "error":"",
   "message":"Your campaign has been deleted."
}
```

This gets all outgoing campaigns in the account.

### HTTP Request

`GET http://24b3f761.ngrok.io/api/outgoing`

### Query Parameters

Parameter | Description
--------- | -----------
id | Contains the ID of the outgoing campaign to delete.


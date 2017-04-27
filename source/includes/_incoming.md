# Incoming Campaigns

The Blast API allows developers to create, manage, and delete incoming campaigns. Incoming campaigns can be used to allow customers to text keywords to a phone number. Incoming campaigns support WebHooks to allow for dynamically generated content.

## List All Incoming Campaigns


```shell
curl "http://24b3f761.ngrok.io/api/incoming"
  -u username:key
```

> The above command returns JSON structured like this:

```json
{  
   "campaigns":[  
      {  
         "id":2,
         "accountId":1,
         "date":{  
            "year":2017,
            "month":3,
            "dayOfMonth":26,
            "hourOfDay":22,
            "minute":49,
            "second":56
         },
         "keyword":"TEST",
         "list":{  
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
         },
         "response":"Just a sample response",
         "phoneNumber":{  
            "rawNumber":"+15103067053"
         },
         "webHook":""
      }
   ]
}
```


This gets all incoming campaigns in the account.

### HTTP Request

`GET http://24b3f761.ngrok.io/api/incoming`

### URL Parameters
No query parameters are required for this API call.


## Get A Incoming Campaign


```shell
curl "http://24b3f761.ngrok.io/api/incoming/<ID>"
  -u username:key
```

> The above command returns JSON structured like this:

```json
{  
   "error":"",
   "message":"",
   "campaign":{  
      "id":2,
      "accountId":1,
      "date":{  
         "year":2017,
         "month":3,
         "dayOfMonth":26,
         "hourOfDay":22,
         "minute":49,
         "second":56
      },
      "keyword":"TEST",
      "list":{  
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
      },
      "response":"Just a sample response",
      "phoneNumber":{  
         "rawNumber":"+15103067053"
      },
      "webHook":""
   }
}
```



This gets all an incoming campaign from the account.

### HTTP Request

`GET http://24b3f761.ngrok.io/api/incoming/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
id | Contains the ID of the outgoing campaign to delete.


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
id | Contains the ID of the incoming campaign to delete.



## Create Incoming Campaign


```shell
curl "http://24b3f761.ngrok.io/api/incoming/create" 
	-u username:key 
	--data-urlencode "phone=+15103067053" 
	--data-urlencode "keyword=TEST5" 
	--data-urlencode "response=I am sending a response" 
	--data-urlencode "list=5"
```

> The above command returns JSON structured like this:

```json
{  
   "error":"",
   "message":"Your campaign has been created!",
   "campaign":{  
      "id":7,
      "accountId":1,
      "date":{  
         "year":2017,
         "month":3,
         "dayOfMonth":26,
         "hourOfDay":23,
         "minute":58,
         "second":42
      },
      "keyword":"TEST5",
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
      "response":"I am sending a response",
      "phoneNumber":{  
         "rawNumber":"+15103067053"
      },
      "webHook":""
   }
}
```
### HTTP Request

`POST http://24b3f761.ngrok.io/api/incoming/create`

### Query Parameters

Parameter | Description
--------- | -----------
phone | The phone number the incoming campaign should work on, including international code.
keyword | The keyword to use for the incoming campaign.
response | The response to send when no WebHook exists, or when the WebHook fails
webhook | The URL WebHook to use.


## Delete Incoming Campaign


```shell
curl "http://24b3f761.ngrok.io/api/incoming/delete"
  -u username:key
  -d "id=1"
```

> The above command returns JSON structured like this:

```json
{  
   "error":"",
   "message":"You have succesfully deleted a campaign."
}
```

This deletes an incoming campaign within an account.

### HTTP Request

`POST http://24b3f761.ngrok.io/api/incoming/delete`

### Query Parameters

Parameter | Description
--------- | -----------
id | Contains the ID of the incoming campaign to delete.


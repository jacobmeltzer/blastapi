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
         "id":30,
         "date":{  
            "year":2017,
            "month":3,
            "dayOfMonth":26,
            "hourOfDay":22,
            "minute":39,
            "second":18
         },
         "name":"New campaign",
         "message":"new message",
         "states":[  
            "",
            "MD"
         ],
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
               "endpoint":0
            },
            "upperBound":{  
               "endpoint":0
            }
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
   ]
}
```

This gets all outgoing campaigns in the account.

### HTTP Request

`GET http://24b3f761.ngrok.io/api/outgoing`

### URL Parameters
No query parameters are required for this API call.

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
      "id":30,
      "date":{  
         "year":2017,
         "month":3,
         "dayOfMonth":26,
         "hourOfDay":22,
         "minute":39,
         "second":18
      },
      "name":"New campaign",
      "message":"new message",
      "states":[  
         "",
         "MD"
      ],
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
            "endpoint":0
         },
         "upperBound":{  
            "endpoint":0
         }
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
}
```

This code retrieves a specific outgoing campaign.

### HTTP Request

`GET http://24b3f761.ngrok.io/api/outgoing/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the outgoing campaign to retrieve.


## Create Outgoing Campaigns

```shell
curl "http://24b3f761.ngrok.io/api/outgoing/create" 
  -u username:key 
  -d "name=Campaign Name&
      message=Just a test message&
      states[]=CA&
      ageFilter=true&
      ageMin=20&
      ageMax=40&
      incomeFilter=true&
      incomeMin=0&
      incomeMax=50000&
      lists[]=5&
      sms=true&
      timestamp=0"
```

> The above command returns JSON structured like this:

```json
{  
   "error":"",
   "id":33,
   "campaign":{  
      "id":33,
      "date":{  
         "year":2017,
         "month":3,
         "dayOfMonth":26,
         "hourOfDay":22,
         "minute":57,
         "second":9
      },
      "name":"Campaign Name",
      "message":"Just a test message",
      "states":[  
         "CA"
      ],
      "ageRange":{  
         "lowerBound":{  
            "endpoint":20
         },
         "upperBound":{  
            "endpoint":40
         }
      },
      "incomeRange":{  
         "lowerBound":{  
            "endpoint":0
         },
         "upperBound":{  
            "endpoint":50000
         }
      },
      "contacts":[  

      ]
   }
}
```

This creates an outgoing campaign within an account.

### HTTP Request

`POST http://24b3f761.ngrok.io/api/outgoing/create`

### Query Parameters

Parameter | Description
--------- | -----------
name | The name of the outgoing campaign.
message | The message to send.
states[] | Array of state codes to send to.
ageFilter | Boolean value, true if should filter contacts by age.
ageMin | Minimum age to send to. Ignored if filtering is false.
ageMax | Maximum age to send to. Ignored if filtering is false.
incomeFilter | Boolean value, true if should filter contacts by income.
incomeMin | Minimum income to send to. Ignored if filtering is false.
incomeMax | Maximum income to send to. Ignored if filtering is false.
lists[] | Array of list IDs to send to
sms | True if should send SMS blast, false for phone call blast.
timestamp | UNIX timestamp representing time to send the campaign at, or 0 for now.

## Delete Outgoing Campaigns

```shell
curl "http://24b3f761.ngrok.io/api/outgoing/delete"
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

This deletes an outgoing campaign within an account.

### HTTP Request

`POST http://24b3f761.ngrok.io/api/outgoing/delete`

### Query Parameters

Parameter | Description
--------- | -----------
id | Contains the ID of the outgoing campaign to delete.


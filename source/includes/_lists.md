# Lists

The Blast API allows developers to create, access, and delete their existing lists. 

## Get All Lists

```shell
curl "http://24b3f761.ngrok.io/api/lists"
  -u username:key
```

> The above command returns JSON structured like this:

```json
{  
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

         ]
      }
   ]
}
```

This gets all lists in the account, but does not list the individual contacts in the lists.

### HTTP Request

`GET http://24b3f761.ngrok.io/api/lists`

### URL Parameters
No query parameters are required for this API call.


## Get A List


```shell
curl "http://24b3f761.ngrok.io/api/lists/<ID>"
  -u username:key
```

> The above command returns JSON structured like this:

```json
{  
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
   }
}
```

This gets a specific contact list in the account, and lists the individual contacts in the lists.

### HTTP Request

`GET http://24b3f761.ngrok.io/api/lists/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the contacts list to retrieve.


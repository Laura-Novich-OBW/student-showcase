# Get Bill Documentation

## GET/tableNo

This GET command is used to process the bill, and consists of a GET request and a GET response. 

The GET response can be printed and given to the patron to obtain payment. 

### Elements

Elements of the GET request and GET response:

| Name      	| Data Type 	| Description                                          |
|------------	|-----------	|------------------------------------------------------|
| tableNo    	| Integer      |Table number. Table 99 is reserved for takeout orders.|
| orderNum   	| Integer      |Takeout order number.                                 |
| timestamp  	| Timestamp   	| Date and time of order.                              |
| Item1	      | String   	   | First order item.                                    |
| ItemOrdered  | String     	| Item ordered.                                        |
| type         | String       | Meal type.                                           |
| Cost         | Float        | Cost of item.                                        |                                                                  
| Item2	      | String     	| Second order item.                                   |

### GET Request

```none
HTTP curl -X GET "http://URL/tableNo?id=99"
```

### GET Response

The order number, table number, and costs are included in the GET response. 

```json
{
   "orderNum":123,
   "timestamp":"2020-01-21T07:44:45-05:00",
   "Item1":{
      "ItemOrdered":{
         "type":"burgerMeal",
         "Cost":10.99
      }
   },
   "Item2":{
      "ItemOrdered":{
         "type":"salad",
         "Cost":9.50
      }
   }
}
```



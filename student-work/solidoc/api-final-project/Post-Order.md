# Post Order Documentation

## POST/lunch 

This POST command is used to process the patron's order, and consists of a POST request and a POST response.

The POST request sends the order to the kitchen and the Post response confirms receipt of the request.
The POST request can be printed and given to the kitchen  to obtain payment.

### Elements

| Object Name   | Data Type     | Values         | Description    |
| ------------- | ------------- | -------------- | ------------- |
| mealType     | String         |``lunch``       | Meal type. | 
| mealCat      | String         |"..."           |  Description. |
| main         | String         |``burgerMeal``  | Bun, burger, sides, condiments, and drink.|
| burger       | String         |``?``           | Description |
| pattyType    | String         | ``beef``, ``lamb``, ``chicken``, ``vegetarian`` | Type of patty. | 
| pattyQty     | Integer        | ``1``, ``2``   |  Patty quantity. Limit of 2. 
| pattyWeightG | Integer      	| ``250``, ``300``| Patty weight, in grams.  	|
| pattyCook    | String       	| ``R``, ``MR`` , ``M`` , ``MW``  , ``WD``| Cook of patty: rare, medium rare, medium, medium-well, and well-done.|
| bunType      | String        	| ``white``, ``wholeWheat``, ``glutenFree``| Bun tyoe.|
| condiment    | String         | ``ketchup``, ``mayo``,``spicy mayo``,``chimichurri``,``BBQsauce``,``hot sauce``	| Limit of 3 condiments.        
| topping      | String         | ``tomato``, ``lettuce``, ``onion``, ``pickles``, ``cheddarCheese``, ``blueCheese``, ``potatoWedges``, ``friedEgg``| Limit of 4 toppings. 
| sides        | String         | "..."           | Description|
| type         | String         | ``frenchFries``, ``garlicFries``, ``onionRings``, ``sideSalad``, ``coleslaw``	| Limit of 2 sides.|
| size 	       | String        	| ``regular``, ``large`` | Size of sides.            	|
| drink        | String         |"..."             | Description|
| type         | String       	| ``Coke``, ``SodaWater``, ``Pepsi``,  ``7-Up``, | Drink type. |
| size         | String       	| ``small``, ``medium``, ``large``  	| Drink size.  	|
| ice          | Boolean      	| ``yes``, ``no`` 	| Ice option.	|


### POST Request

The POST request specifies the patron's meal choices.

``` JSON
  {
     "mealType":"lunch",
     "mealCat":{
  	  "main":"burgerMeal",
  	  "burger":{
        "pattyType":"”beef”",
        "pattyQty":1,
     	  "pattyWeightG":220,
     	  "pattyCook":"MR",
     	  "bunType":"wholeWheat",
     	  "condiment1":"ketchup",
     	  "condiment2":"barbecueSauce",
          "condiment3":"spicyMayo",
          "condiment4":"none",
     	  "topping1":"lettuce",
          "topping2":"tomato",
     	  "topping3":"onion",
          "topping4":"pickles",
     	  "topping5":"None"
  	  },
  	  "sides":{
     	  "side1":{
        	  "type":"frenchFries",
        	  "size":"large"
     	  },
     	  "side2":{
        	  "type":"none",
        	  "size":""
     	  }
  	  },
  	  "drink":{
     	  "type":"Coke",
     	  "size":"large",
     	  "ice":"yes"
  	  },
     },
  }
  
```

### POST Response

The POST response confirms receipt of POST request.

```HTTP
200 OK
```

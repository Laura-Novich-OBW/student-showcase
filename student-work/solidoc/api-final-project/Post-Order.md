# Post Order Documentation

## POST/lunch 

This POST command is used to process the patron's order, and consists of a POST request and a POST response.

The POST request sends the order to the kitchen and the Post response confirms receipt of the request.
The POST request can be printed and given to the kitchen  to obtain payment.

### Elements

Below are some elements of the POST request and POST response:


| Object Name  | Data Type    | Values     | Description  | Default Choice
| ------------ | ------------- | ---------- | -------------|----------------|
| mealType     | String   |``lunch``  | Meal type. |
| mealCat      | String   | |  |
| main         | String  |``burgerMeal``|Bun, burger, sides, condiments, andve
| pattyType    | String  | ``beef``, ``lamb``, ``chicken``, ``vegetarian`` | Type of patty. | 
| pattyQty   	| Integer  | ``1``, ``2``|  Patty quantity. Limit of 2. 
| pattyWeightG | Integer	| ``250``, ``150``| Patty weight in grams.  	|
| pattyCook   | String 	| ``R``, ``MR`` , ``M`` , ``MW``  , ``WD``| Cook of patty: rare, medium rare, medium, medium-well, and well-done.|
| bunType  	| String 	| ``white``, ``wholeWheat``, ``glutenFree``| Choice of bun type.|
| condiment | String  | ``ketchup``, ``mayo``,``spicy mayo``,``chimichurri``,``BBQsauce``,``hot sauce``	| Choice of up to 3 condiments.        
| topping  	| String | ``tomato``, ``lettuce``, ``onion``, ``pickles``, ``cheddarCheese``, ``blueCheese``, ``potatoWedges``, ``friedEgg``| Choice of up to 4 toppings. 
|sides|
| type  | String  | ``frenchFries``, ``garlicFries``, `onionRings``, `sideSalad``, `coleslaw``, `sideSalad``	| Choice of up to 2 sides.|
| size 	| String 	| ``regular``, ``large``  	| Size of sides.            	|
|drink|
| type   | String    	| ``Coke``, ``SodaWater``, ``Pepsi``,  ``7-Up``, | Choice of drink type. |
| size  | String    	| ``small``, ``medium``, ``large``  	| Choice of drink size.  	|
| ice   | Boolean    	| ``yes``, ``no`` 	| Choice of adding ice to the drink.	|


### POST Request


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




## POST Response 

```HTTP
200 OK
```

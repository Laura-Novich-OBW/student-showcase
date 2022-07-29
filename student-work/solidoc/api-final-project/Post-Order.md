# Post Order Documentation

## POST/lunch 

This POST command is used to process the patron's order, and consists of a POST request and a POST response.

The POST request sends the order and the Post response confirms receipt of the request.

The POST request can be printed and given to the kitchen staff.

### Elements

Below are some elements of the POST request and POST response:

| Object Name   | Data Type     | Values         | Description    | Default Value  |
| ------------- | ------------- | -------------- | ------------- | ----------------|
| mealType     | String         |``lunch``       | Meal type. | 
| mealCat      | String         |                |  Meal category. |
| main         | String         |``burgerMeal``  | Bun, burger, sides, condiments, and drink.|
| burger       | String         |                | Burger portion of ``burgerMeal``. |
| pattyType    | String         | ``beef``, ``lamb``, ``chicken``, ``vegetarian`` | Type of patty. | ``beef``|
| pattyQty     | Integer        | ``1``, ``2``   |  Patty quantity, l limit of 2. | ``1``|
| pattyWeightG | Integer      	| ``220``, ``300``| Patty weight, in grams. | ``220``|
| pattyCook    | String       	| ``R``, ``MR`` , ``M`` , ``MW``  , ``WD``| Cook of patty: rare, medium rare, medium, medium-well, and well-done.|``M``|
| bunType      | String        	| ``white``, ``wholeWheat``, ``glutenFree``, ``multiGrain``| Bun type.| ``white``|
| condiment    | String         | ``ketchup``, ``mayo``,``spicy mayo``,``chimichurri``,``barbequeSauce``,``hot sauce``, ``none``	| Condiments, limit of 3. | ``none``|      
| topping      | String         | ``lettuce``, ``tomato``, ``onion``, ``pickles``, ``cheddarCheese``, ``blueCheese``, ``potatoWedges``, ``friedEgg``, ``none``| Toppings, limit of 4. |``none``|
| sides        | String         |                     | Side(s) portion of ``burgerMeal``.|
| type         | String         | ``frenchFries``, ``garlicFries``, ``onionRings``, ``sideSalad``, ``coleslaw``, ``none``	| Sides, limit of 2.| ``none``|
| size 	       | String        	| ``small``, ``medium``, ``large`` | Size of sides.     |   ``medium``|
| drink        | String         |                     | Drink portion of ``burgerMeal``.|
| type         | String       	| ``Coke``, ``SodaWater``, ``Pepsi``,  ``7-Up``, ``none``| Drink type. | ``none``|
| size         | String       	| ``small``, ``medium``, ``large``  	| Drink size.  	| ``medium``|
| ice          | Boolean      	| ``yes``, ``no`` 	| Ice option.	| ``no``

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

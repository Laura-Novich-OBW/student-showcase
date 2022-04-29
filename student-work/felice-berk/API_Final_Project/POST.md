## POST/lunch 

Below is a POST/lunch request &mdash; this is an example of how it would appear when the customer has placed their order.
The POST will send the customer's order to the kitchen once the order is completed and confirmed. 
The order will be printed in the kitchen where the cook will prepare the customer's requested meal. 
Beneath the code snippet is a table explaining the components of the POST.


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

### Burger Meal

| Object Name   | Data Type     | Values     | Description    |
| ------------- | ------------- | ---------- | ------------- |
| mealType      | string        | "lunch" (in the future will include other options) | The type of meal ordered. |
| main          | string        | "burgerMeal" |Burger with bun, condiments/sauces, toppings, a choice of up to 2 sides, and a drink. |
| pattyType     | string    	| "beef", "Angus" "ground turkey" "black bean" | Choice of different burger types including beef, Angus, ground turkey, black bean. |   
| pattyQty      	| int       	| 1 or 2                            | The quantity of patties on the burger. Limit of 2. 	|
| pattyWeightG  	| int       	| 160, 220, 330                         	| This indicates the weight of the patty in grams. The limit is 330 grams.             	|
| pattyCook     	| string    	| ``MR``, ``M``, ``MW`` , ``WD``                | The doneness of the patty. MR-medium rare, M-medium, MW-medium well, WD-well done.                    	|
| bunType       	| string    	| "white", "wholeWheat", "glutenFree"               	| Choice of bun types including white, whole wheat, and gluten free.        	|
| condiment``x`` 	| string    	| "ketchup", "barbecueSauce", "spicyMayo", "none"  	| Choice of up to three condiments. A choice of none means no condiments.              	|
| topping``x``   	| string    	| "lettuce", "tomato", "onion", "pickles", "none" 	| Choice of up to four toppings. A choice of none means no topping.                 	|

### Sides

| Object Name   | Data Type     | Values     | Description    |
| ------------- | ------------- | ---------- | ------------- |
| type       	| string    	| "frenchFries", "sweetPotatoFries", "onionRings", "none" 	| Choice of different sides. Limit of 2. A choice of none means no side.	|
| size       	| string    	| "small", "medium", "large"                        	| Choice of portion size.            	|

### Drink

| Object Name   | Data Type     | Values     | Description    |
| ------------- | ------------- | ---------- | ------------- |
| type       	| string    	| "Coke", "Zero", "Fanta", "Seltzer", "Water", "Iced Tea", "none" 	| Choice of drink type. Limit of 1. A choice of none means no drink.        	|
| size       	| string    	| "small", "medium", "large"                    	| Choice of drink size.              	|
| ice        	| string    	| "yes", "none"                                 	| Choice of adding ice to the drink. Choice of none means no ice.	|


## POST Response Example 

When a correct order is placed, the server replies to the app with an acknowledgment. 
This is not displayed to the user.  

```HTTP
200 OK
```

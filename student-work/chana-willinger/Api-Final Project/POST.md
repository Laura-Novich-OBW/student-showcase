POST/lunch

This is a post order for lunch, to send to the kitchen. When an OK response is received, the order is printed in the kitchen so the cook can start cooking.

**Example Response

```curl 

-H "Content-Type: application/json" -X POST -d'{

```JSON

   "mealType":"lunch",
   "mealCat":{
  	"main":"burgerMeal",
  	"burger":{
     	"pattyType":"beef",
     	"pattyQty":1,
     	"pattyWeightG":300,
     	"pattyCook":"MR",
     	"bunType":"wholeWheat",
     	"condiment1":"ketchup",
     	"condiment2":"secretSauce",
     	"topping1":"lettuce",
     	"topping2":"pickles",
     	"topping3":"None",
     	"topping4":"None",
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
     	"ice":true
  	}
   }
},
http://URL/
```
**BurgerMeal Guide

| **Name**    | **Data Type** | **Value**                            | **Description**                                                                                           |
|-------------|---------------|--------------------------------------|-----------------------------------------------------------------------------------------------------------|
| mealType    | int           | lunch                                | the type of meal it is. At the moment, this is the only option. In the future, there will be more options |
| main        | string        | burgerMeal                           | the type of meal served                                                                                   |
| pattyType   | string        | beef                                 | the substance of the patty                                                                                |
| pattyQty    | int           | 1, 2                                 | the amount of patties on the burger. The customer can select one.                                         |
| pattyWeight | int/string    | 150, 200, 300                        | the size of the patties per weight. The customer can select one.                                          |
| pattyCook   | string        | MR, M, MW                            | how much the patty is cooked. The customer can pick one.                                                  |
| condiment   | string        | ketchup, mustard, mayo, none         | sauces to put on top. The customer can pick as many as they want                                          |
| topping     | string        | lettuce, tomato, onion, pickle, none | toppings to put in the burger. The customer can pick as many as they want                                 |
| side1 | string | side                                                     | side dishes to the burgerMeal. The customer will be able to select up to 2 dishes.                                        |
| type  | string | frenchFries, onionRings, mashedPotatoes, sideSalad, none | choices of sides. The customer can select one of these here.                                                              |
| size  | string | small, large                                             | the size of the side dish. The customer can select one here.                                                              |
| side2 | string | side                                                     | the second side dish in this meal.                                                                                        |
| type  | string | frenchFries, onionRings, mashedPotatoes, sideSalad, none | choices of sides. The customer can select one of these here. They can select the same thing here as they select in side1. |
| drink | string  | drink                                     | a drink for the meal                                                  |
| type  | string  | coke, sprite, fanta, icedTea, water, none | choice of drinks. The customer can select one.                        |
| size  | string  | small, large                              | size of the drink. The customer can select one.                       |
| ice   | boolean | true, false                               | the customer can choose if they want ice or not. They can select one. |

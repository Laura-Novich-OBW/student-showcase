# Menu Items

This file contains a list of all the items on the Putnam Diner menu that you can [order](POST-order-meal.md) using the app. Each menu item is represented in the API by a [meal object](#meal-objects) that contains several smaller [meal component objects](#meal-component-objects). Meal objects define the components included in a meal, as well the limits of the numbers and sizes of the meal components.

>Note<br>
>Currently, the API only supports the `burgerMeal` meal object.

## Meal Objects

These are the meal objects that you can use when [placing orders](POST-order-meal.md) with the app.

Name | Description
---- | -----------
burgerMeal | An object representing a burger meal, containing the following menu items: <ul><li>[`burger`](#burger) (required, limit: 1, added price for more than 1 patty)</li><li>[`sides`](#sides) (optional, limit: 2 small dishes)</li><li>[`drink`](#drink) (optional, limit: 1 small drink)</li></ul>

Meal objects are formatted in JSON. They have a single key which corresponds to the name of the meal object. The value of this key is an object containing the components included in the meal.

Example meal object:

```JSON
{
    "burgerMeal" : {
        "burger": {
            "pattyType": "beef",
            "pattyQuantity": 1,
            "pattyWeight": 300,
            "pattyCook": "mediumRare",
            "bunType": "wholeWheat",
            "condiments": [
                "ketchup",
                "secretSauce"
            ],
            "toppings": [
                "lettuce",
                "pickles",
                "friedEgg"
            ]
        },
        "sides": [
            {
                "type": "frenchFries",
                "size": "large" 
            }
        ],
        "drink": {
            "type": "coke",
            "size": "large",
            "ice": true
        }
    }
}
````

## Meal Component Objects

Meal component objects are used to construct meal objects for orders.

### Index
[burger](#burger)<br>
[drink](#drink)<br>
[sides](#sides)<br>

#### burger
An object representing a burger, containing the following properties:

Name | type | Req. | Description
-----| -----| ---- | -----------
pattyType | string | Y | The type of patty in the burger. <br>Options: `"beef"`, `"chicken"`, `"veggie"`
pattyWeight | int | Y | The weight of the patty, in grams. <br>Options: `100`, `200`, `300`
pattyCook | string | Y | How cooked the patty is. <br>Options: `"rare"`, `"mediumRare"`, `"wellDone"`
pattyQuantity | int | Y | The number of patties in the burger. The maximum value is `3`. The values for `pattyType`, `pattyWeight`, and `pattyCook` are the same for all patties.
bunType | string | Y | The type of bun for the burger. <br>Options: `"white"`, `"wholeWheat"`, `"glutenFree"`
condiments | Array\<string\> | N | The condiments for the burger. You can only add 2 condiments to a burger. If the `condiments` array includes more than 2 items, only the first 2 are included in the order. <br>Options: `"ketchup"`, `"mustard"`, `"chimichurri"`, `"mayo"`
toppings | Array\<string\> | N | The toppings for the burger. You can only add 3 toppings to a burger. If the `toppings` array includes more than 3 items, only the first 3 are included in the order. <br>Options: `"lettuce"`, `"pickles"`, `"tomatoes"`, `"friedEgg"`

#### drink
An object representing the drink included in a meal, containing the following properties:

Name | type | Req.| Description
---- | ---- | --- | -----------
type | string | Y | The type of drink. <br>Options: `"coke"`, `"dietCoke"`, `"sprite"`, `"water"`
size | string | Y | The size of the side drink. <br>Options: `"small"`, `"medium"`, `"large"`
ice | boolean | N | A boolean representing whether a drink comes with ice. Defaults to `true`.


#### sides
An array of objects representing side dishes included in a meal. Each side dish object contains the following properties:

Name | type | Req.| Description
---- | ---- | --- | -----------
type | string | Y | The type of side dish. <br>Options: `"frenchFries"`, `"mashedPotatoes"`, `"onionRings"`, `"coleslaw"`
size | string | Y | The size of the side dish. <br>Options: `"small"` or `"large"`.

**Introduction**

The owners of General Putnam Motel Diner are creating an app for patrons to use to order take-out. In the future, they want to add the app to tablets, so patrons can order from their seats in the restaurant. I am creating a hamburger API, so that the developers can create a POC. At this time, it is only for lunch orders, but in the future, it will be expanded to other meals as well, such as dinner, breakfast, and events. 

```mermaid
flowchart TD
    A[Order Burger Meal] --> B(Choose patty type);
    B --> C[Choose patty quantity and weight];
    C --> D(Choose patty cook and bun type);
    D --> E{Condiments};
    E -- Yes --> F[Choose Condiments];
    E -- No --> G{Toppings};
    F --> G{Toppings};
    G -- Yes --> H(Choose toppings);
    G -- No --> I{Sides};
    H --> I{Sides};
    I -- Yes --> J[Choose sides];
    I -- No --> L{Drink};
    J --> K[Chooses size];
    K --> L{Drink};
    L -- Yes --> M(Chooses drink);
    M --> N{Ice};
    N -- Yes --> O{Send to kitchen};
    N -- No --> O{Send to kitchen};
    L -- No --> O{Send to kitchen};
```

These are examples of response codes

| Codes  | Responses                           |
|--------|-------------------------------------|
| 200 OK | The order has been placed correctly |
| 404    | Not Found                           |
| 429    | Too many requests                   |
| 500    | Internal service error              |

Acknowledgments: 

This exercise was borrowed and adapted by Alex Fiedler.

This exercise was borrowed and adapted by Good Docs Project Templates.

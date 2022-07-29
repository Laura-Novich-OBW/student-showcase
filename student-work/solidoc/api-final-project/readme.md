# General Putnam Motel Diner API - POC

## Overview

The General Putnam Motel Diner API POC illustrates two of many basic functions required for the Diner's operations:

* Takeout order placement
* Bill processing

The API POC will allow patrons to place a takeout order and get the bill. 

The API may be further developed to include features such digital orders for in-house patrons.

## Documentation

For details, refer to:

- [Takeout Order Documentation](https://github.com/solidoc365/student-showcase/blob/main/student-work/solidoc/api-final-project/Post-Order)
- [Bill Documentation](https://github.com/solidoc365/student-showcase/blob/main/student-work/solidoc/api-final-project/Get-Bill)

## General Response Codes

Code | Description
----- | ----------
100 | Request Received
200 | Request Successful
401 | Unauthorized
403 | Forbidden
404 | Page not Found
500 | Internal Server Error

## API Workflow

```mermaid
  flowchart TD;
  
     A(Place order)-->B[Choose bun type];
      B-->C[Choose patty type];
      C-->D[Choose patty weight];
      D-->E[Choose patty amount];
      E-->F[Choose patty cook];
      F-->G{Topping?};
      G--Yes-->H[Choose topping];
      H-->J{Another topping?}
      J--yes-->H;
      J--No-->K{Condiment?};
      K--Yes-->L[Choose condiment];
      L-->W{Another condiment?}
      W--yes-->L;
      W--no-->M;
      K--No-->M{Side dish?};
      M--Yes-->O[Choose side type];
      O-->P[Choose side size];
      P-->X{Another side?};
      X--yes-->O;
      X--no-->Q;
      M--No-->Q{Drink?};
      Q--Yes-->R[Choose drink];
      Q--No-->V;
      R-->S[Choose drink size];
      S-->T{Ice?}
      T--yes-->U[ice];
      U-->V;        
      T--no-->V(Order Completed);
```

## References 
[The Good Docs Project](https://github.com/thegooddocsproject/templates)

[Mermaid Live Editor](http://mermaid-js.github.io/mermaid/)

[Laura Novich, Instructor Extraordinaire at OBW](https://github.com/Laura-Novich-OBW)

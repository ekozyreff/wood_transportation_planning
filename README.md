# Wood Transportation Planning

The aim of this project was to create a tool to plan the logistics of wood transportation in the production chain of a paper manufacturing company.

Paper is made from wood, which has to be transported from the forest to the factories (sometimes going through intermediate yards).

![wood transportation scheme](transportation.png)

This process is complext because it involves crucial (and costly) aspects, such as:

- Current stock levels on the forest, intermediate years and factories
- Specificities of the demand on the factories (e.g. type of product, wood density and wood age)
- Accessability to roads, depending on wheather conditions
- Desired stock levels (minimum and maximum) on intermediate years and factories
- Desired transportation amounts (minimum and maximum) for specific origin-destination pairs

Once a transportation plan is ready, a large number of trucks must be designated to pick up and drop its loads. This is done on a daily basis and is a procedure that is revised and refined on the go.

To assist the planning of this process, a tool was created using with the follwing structure:

- An Excel file containing all input bases (stocks and demands).
- Another Excel file, which provides an interface for the user to analyze the inputs and make adjustments to the constraints of the plan.
- A transportation linear programming model that balances stocks in all locations and all periods of the plan.
- A final Excel file, with the output bases (transportation plan and projected stocks).

The pre-processing of the input bases and post-processing of the output bases are done using VBA. The optimization model was written in Python using Pyomo and [COIN-OR](https://www.coin-or.org/)'s free solver CBC. (No comercial solver was necesssary because the solve time is very short, usually less than 5 seconds.)





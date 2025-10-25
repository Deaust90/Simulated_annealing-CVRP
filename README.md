# VRP Solver with Simulated Annealing

## Project Overview

This project implements a **Simulated Annealing (SA) metaheuristic** to solve the **Capacitated Vehicle Routing Problem (CVRP)**. The goal is to find optimal or near-optimal routes for a fleet of vehicles to serve a set of customers, respecting vehicle capacity constraints and minimizing the total travel distance.

The code is structured as a Jupyter Notebook (`SA code.ipynb`) and provides a complete pipeline from reading standard VRP instance files to visualizing the final solution.

## Features

*   **Problem Data Handling**: Reads standard `.vrp` file formats (e.g., from the CMT dataset).
*   **Multiple Initial Solution Heuristics**:
    *   Nearest Neighbor
    *   Sequential Insertion
    *   **Clarke & Wright Savings** (Used as the primary method in the SA)
*   **Advanced Simulated Annealing Core**:
    *   **Tournament Selection**: Evaluates multiple neighbors per iteration, selecting the best candidate.
    *   **Diverse Neighborhood Operators**:
        *   `swap_customers`: Swaps two customers between any routes.
        *   `two_opt_intra_route`: Improves a single route by reversing a sub-segment.
        *   `relocate_customer`: Moves a customer to a different position or route.
    *   Adaptive cooling schedule and feasibility checks.
*   **Solution Analysis & Visualization**:
    *   Calculates total route cost and vehicle loads.
    *   Plots the final solution with distinct colors for each vehicle route.

## Installation & Usage

1.  **Prerequisites**: Ensure you have Python installed with the required libraries.

2.  **Run the Solver**:
    *   Open the `SA code.ipynb` notebook.
    *   In the final cell, modify the `path` and `filename` variables to point to your VRP instance file.
    *   Execute all cells. The metaheuristic will run and display the optimized routes and a visualization upon completion.

## Sample Output

The solver outputs:
*   **Console Log**: Initial cost, iteration progress, temperature, and the final best cost.
*   **Route Details**: A list of each vehicle's route and its load.
*   **Visualization**: A matplotlib graph plotting the depot, customers, and the routes taken by each vehicle.

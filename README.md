# Improved Horse Herd Optimization with Backtracking Search Algorithm (m-HOA)

This repository contains the code and implementation for our project on improving the Horse Herd Optimization (HOA) algorithm. We improved upon the original algorithm to handle high-dimensional problems better since the standard version has a bad habit of getting stuck in local optima in such scenarios.

## The Problem and Our Solution

The original HOA mimics how horses behave in herds, and while it is decent for certain use cases, it tends to lose diversity pretty fast as iterations go on. Once the population converges prematurely, it stops searching the rest of the space efficiently.

To fix this, we decided to hybridize it with the Backtracking Search Algorithm (BSA). BSA is known for having strong global exploration skills even if it is a bit slow to converge. We integrated the mutation and crossover operators from BSA into the horse herd logic and also added a memory feature that keeps track of previous generations.

We also introduced a new idea called "neighborhoods". Instead of the whole herd just following the global best or their own personal best, we split them into smaller groups. Horses in a neighborhood follow the best horse in that specific local group. This helps balance out the exploration and exploitation so the algorithm does not just rush to the first good solution it finds.

## Code Structure

The project is written in MATLAB. Here is what is inside the folders:

* **mHOA.m**: This is the main function for our modified algorithm.
* **HOA.m**: The original algorithm is included here too so you can run comparisons.
* **main.m**: Run this script to execute the experiments and see the results.
* **BenchmarkFunctions/**: This folder holds the objective functions we tested against, like Colville, Rosenbrock, and Styblinski-Tang.

## How to Run It

You will need MATLAB installed to run these scripts. Open up `main.m` and you can adjust the parameters if you want to test different scenarios.

By default, we set it up with the parameters used in our report:
* Population size: 50 
* Iterations: 1000 
* Neighborhood size: 5 

When you run the main script, it will output the global optimum value found (Zopt) and the position of that solution (ZMopt).

## Results

We tested this modified version against the original HOA on a mix of fixed-dimensional and multi-dimensional benchmark functions.The results were honestly much better for the modified version. It generally showed better accuracy and managed to avoid those local optima traps that the original struggled with.

## References

If you want to read the original papers we based this work on, you can check them out here:

* **Horse Herd Optimization (HOA):** F. MiarNaeimi, G. Azizyan, and M. Rashki, "Horse herd optimization algorithm: A nature-inspired algorithm for high-dimensional optimization problems," *Knowledge-Based Systems*, vol. 213, 2021.
* **Backtracking Search Algorithm (BSA):** P. Civicioglu, "Backtracking Search Optimization Algorithm for numerical optimization problems," *Applied Mathematics and Computation*, vol. 219, pp. 8121-8144, 2013.

## Authors
* Tanmay Shreshth
* Aryan Verma

Department of Electronics and Electrical Engineering, Indian Institute of Technology Guwahati.

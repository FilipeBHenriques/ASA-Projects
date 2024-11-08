# Process Assignment and Cost Minimization

Given a system with two processors X and Y, `n` processes, and costs associated both between the processes themselves and between processes and processors. The cost between processes running on the same processor is always 0. The task is to find the lowest possible cost to run all processes by assigning them to each of the processors.

## Example

### Execution Costs of Each Process \( p_i \):

| i  | 1  | 2  | 3  | 4  |
|----|----|----|----|----|
| X_i| 6  | 5  | 10 | 4  |
| Y_i| 4  | 10 | 3  | 8  |

### Communication Costs \( c_{ij} \) Between Two Processes \( p_i \) and \( p_j \):

| c   | 1  | 2  | 3  | 4  | i  |
|-----|----|----|----|----|----|
| 1   | 0  | 5  | 0  | 0  |    |
| 2   | 5  | 0  | 6  | 2  |    |
| 3   | 0  | 6  | 0  | 1  |    |
| 4   | 0  | 2  | 1  | 0  |    |
| j   |    |    |    |    |    |

### Solution

- Assign processes as follows:
  - **AX** = {p4} (Processes assigned to Processor X)
  - **AY** = {p1, p2, p3} (Processes assigned to Processor Y)

The cost calculation is as follows:


Cost = Σi∈AX Xi +Σi∈AY Yi +Σ(i, j)∈AX×AYcij
= X4 +Y1 +Y2 +Y3 +c24 +c34
= 4+4+10+3+2+1
= 24

## Input Format

- The first line contains two integers:
  - `n` (number of processes, `n ≥ 2`)
  - `k` (number of non-zero entries in the communication cost matrix, `k ≥ 0`), only upper triangular entries since the matrix is symmetric.
  
- The next `n` lines contain two integers, representing the execution costs of process \( p_i \) on processors X and Y, respectively.

- The following `k` lines each contain three integers:
  - `i` (process identifier for \( p_i \), where \( i ≤ n \))
  - `j` (process identifier for \( p_j \), where \( j ≤ n \))
  - `c_{ij}` (the communication cost between processes \( p_i \) and \( p_j \)). Since the matrix is symmetric, \( c_{ij} = c_{ji} \).

## Output Format

- An integer representing the minimum cost to run all the processes.

## Example

input 1
4 4
6 4
5 10
10 3
4 8
1 2 5
2 3 6
2 4 2
3 4 1
output 1
24

### Compilation
 ```bash
 g++ -std=c++11 -O3 -Wall file.cpp -lm

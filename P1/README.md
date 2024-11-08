# Longest Path and Minimum Vertices in a DAG

Given a Directed Acyclic Graph (DAG), the task is to return the longest path and the minimum number of vertices needed to reach all elements in the given graph.

## Input

The input file is defined as follows:

- The first line contains two integers:
  - `n` (number of vertices, `n ≥ 2`)
  - `m` (number of dependencies, `m ≥ 0`)

- The following `m` lines each contain two integers `x` and `y`, indicating that there is an edge from vertex `x` to vertex `y`.

Any integers on a line are separated by at most one white space, and no line contains any characters other than the end of line.

## Output

The output should be:

 - <min> <longest> where <min> corresponds to the minimum amount of vertices to reach all elements and  <longest> corresponds to the longest path.

Example
Input
7 8
3 4
3 2
4 6
4 5
6 2
6 5
5 7
2 7
Output
2 5

### Compilation
 ```bash
 g++ -std=c++11 -O3 -Wall file.cpp -lm

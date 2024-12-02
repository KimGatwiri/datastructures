# Dynamic Programming (DP)

Dynamic Programming (DP) is a method for solving complex problems by breaking them down into simpler subproblems. It is commonly used in optimization problems where overlapping subproblems and optimal substructure properties exist.

---

## Key Concepts

### 1. Overlapping Subproblems
- DP solves problems that can be divided into subproblems that are reused multiple times.
- Instead of solving the same subproblem repeatedly, DP stores the results of solved subproblems to avoid redundant computations.
- Example: In Fibonacci calculation, the result of \( F(n-1) \) is reused to calculate \( F(n) \).

### 2. Optimal Substructure
- A problem exhibits optimal substructure if an optimal solution can be constructed from the optimal solutions of its subproblems.
- Example: In the shortest path problem, the shortest path from \( A \) to \( C \) via \( B \) can be found by combining the shortest paths \( A \to B \) and \( B \to C \).

---

## Steps to Solve a Problem Using DP

1. **Define the State**:
   Identify the state that represents the solution to the problem. This is usually a function of the variables of interest.
   - Example: In the Fibonacci problem, the state is \( dp[i] \), which represents the \( i \)-th Fibonacci number.

2. **Define the Recurrence Relation**:
   Formulate the relationship between the state and its subproblems.
   - Example: \( dp[i] = dp[i-1] + dp[i-2] \).

3. **Base Cases**:
   Establish the base cases to initialize the solution process.
   - Example: \( dp[0] = 0 \), \( dp[1] = 1 \).

4. **Compute the Solution**:
   Use iteration or recursion with memoization to compute the value of the required state.

---

## DP Techniques

### 1. **Memoization (Top-Down Approach)**
- Solve the problem recursively, storing the results of subproblems in a data structure like an array or hash map to avoid re-computation.
- Example: 
    ```python
    def fibonacci(n, memo={}):
        if n <= 1:
            return n
        if n not in memo:
            memo[n] = fibonacci(n-1, memo) + fibonacci(n-2, memo)
        return memo[n]
    ```

### 2. **Tabulation (Bottom-Up Approach)**
- Solve the problem iteratively by building a table (array) from base cases up to the desired result.
- Example:
    ```python
    def fibonacci(n):
        if n <= 1:
            return n
        dp = [0] * (n + 1)
        dp[1] = 1
        for i in range(2, n + 1):
            dp[i] = dp[i-1] + dp[i-2]
        return dp[n]
    ```

---

## Example Problems

### 1. Fibonacci Numbers
Find the \( n \)-th Fibonacci number:
- **Recurrence Relation**: \( F(n) = F(n-1) + F(n-2) \)
- **Base Cases**: \( F(0) = 0 \), \( F(1) = 1 \)

### 2. Knapsack Problem
Given weights and values of items, maximize the total value without exceeding the weight capacity.
- **State**: \( dp[i][w] \) represents the maximum value for the first \( i \) items and weight \( w \).
- **Recurrence Relation**:
    - If item \( i \) is excluded: \( dp[i][w] = dp[i-1][w] \)
    - If item \( i \) is included: \( dp[i][w] = dp[i-1][w-wt[i]] + val[i] \)

### 3. Longest Common Subsequence (LCS)
Find the length of the longest subsequence common to two sequences.
- **State**: \( dp[i][j] \) represents the LCS of the first \( i \) characters of string \( X \) and the first \( j \) characters of string \( Y \).
- **Recurrence Relation**:
    - If \( X[i-1] == Y[j-1] \): \( dp[i][j] = dp[i-1][j-1] + 1 \)
    - Otherwise: \( dp[i][j] = \max(dp[i-1][j], dp[i][j-1]) \)

---

## Applications of DP
1. **Optimization Problems**:
   - Shortest Path (Dijkstra’s, Bellman-Ford)
   - Knapsack Problem
2. **Combinatorics**:
   - Counting ways (e.g., number of ways to climb stairs)
3. **String Problems**:
   - Longest Palindromic Subsequence
   - Edit Distance
4. **Game Theory**:
   - Nim Game
   - Optimal Game Strategies

---

## Advantages and Limitations

### Advantages:
- Efficiently solves problems with overlapping subproblems.
- Reduces time complexity compared to naive recursive solutions.

### Limitations:
- Requires additional memory for storing intermediate results.
- May not work efficiently for problems without overlapping subproblems.

---

Dynamic Programming is a powerful tool for solving a wide range of computational problems. Mastering it requires practice and a solid understanding of its principles.

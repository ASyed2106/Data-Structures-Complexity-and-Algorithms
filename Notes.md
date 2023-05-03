# Data Structures

## Run Time 
  - When we are creating a solution for a problem we can be hindered by the efficency of our solution
  - A more efficient and well optimized code will run and solve the problem much faster than a less efficient code
  
### Example -  Starting a timer() and ending a timer()
  - We are taking a function from the timeit module called a default_timer and called it timer.
  - When we are about the test the runtime of our code. We are going to section off the execution portion of the code.
  - At the beginning, we will ‘start’ the timer … timestamp of when the code started
  - At the end, we will ‘end’ the timer .. timestamp of when the code ended
      - We can calculate the run time by subtracting the end time and start time
 ## Refactoring 
  - Unit: A segment of a program that handles a problem’s specific requirement.
  - Refactoring: The act of improving the performance and efficiency of the unit (section of a program) without affecting input and the output of the unit.
  - If a program is simplified to its Input → Processing → Output
        - then we are trying to optimize the “Processing” section of the program by Refactoring.
        
## Behavioural Analysis 

### Big-o-Notation
  - a mathematical notation that describes the limiting behaviour of a function as its input/parameter/argument approaches infinity
      - The Big-O to tell us the “Worst case scenario performance” of our algorithm
      - There are multiple notations when analyzing the complexity of an algorithm: Big Omega, Big Theta, and Big O
#### Example
Consider the function: f(x)
  - To analyze the worst-case scenario / behaviour of f(x) we need to find the Big-O notation for f(x)
      → O(f(x))
  - Then it can be classified with one of its Big-O Notation

#### When do we use?
  1. **Algorithm Proof:** To prove that our algorithm A is better than algorithm B, we must have a proof that our Big-O notation is better
  2. **Measure Performance, Run-time, or Disk Usage:** Our algorithms are designed to solve problems; however, reaching the solutions must not be feasible due to time or disk-space constraints
  3. **Mathematically Formalizing our Algorithms:** Different hardware will output different runtimes; therefore, we needed a formal mathematical analysis
 
 ### Common Big-o-Notation
 List from best to worst performance:
   **O(1) → Constant Complexity**
        Constant Time Algorithms: Completes the execution in the same amount of time regardless of its input.
            Examples:
              - Accessing a data point in a list with a known index 
              - Given two numbers, report the sum
    **O(log n) → Logarithmic Complexity**
        If N was the size of the input, the algorithm will take log(n) steps to solve a problem.
        Most cases will use a log with a base of 2 → log2 
        When the input set is continuously divided by two, it is usually a logarithmic complexity algorithm
          Example:
              - Binary Search 

    **O(n) → Linear Complexity**
        The completion of the algorithm is directly proportional to the size of the input.
          Example:
              - Search for an item in a list
              - Searching a queue
              - Adding two n-bit integers

   **O(n log n) → Linearithmic Complexity**
        The completion of the computation grows in a linear pattern with a rate of change of a logarithm
            Examples:
              - Heapsort
              - Mergesort

   **O(n2) → Quadratic Complexity**
          Quadratic Complex Algorithms: performance is directly proportional to the square of the size of the input data set.
            Examples:
              - Multiply two-n-digit numbers
              - Bubble, Insertion, Selection Sort

 

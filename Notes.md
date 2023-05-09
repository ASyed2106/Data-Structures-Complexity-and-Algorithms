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

  - is used to measure how running time or space requirement for your program grows as input size grows 
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
        - Where an algorithm's execution time is not based on the input size n
        - Whatever be the input size n, the runtime doesn’t change.
            Examples:
              - Accessing a data point in a list with a known index 
              - Given two numbers, report the sum
              
    **O(log n) → Logarithmic Complexity**
        If N was the size of the input, the algorithm will take log(n) steps to solve a problem.
         will use a log with a base of 2 → log2 
          - When the input set is continuously divided by two, it is usually a logarithmic complexity algorithm
          - When an algorithm decreases the magnitude of the input data in each step
          - Means that the number of operations is not proportionate to the size of the input.
          - O (log2 n) basically implies that time increases linearly while the value of 'n' increases exponentially.
          - So, if computing 10 elements take 1 second, computing 100 elements takes 2 seconds, 1000 elements take 3 seconds, and so on.
              - Example:
                  -  Binary Search 
                  
    **O(n) → Linear Complexity**
        The completion of the algorithm is directly proportional to the size of the input.
        When the running time of an algorithm increases linearly with the length of the input
              -  i.e. when a function checks all of the values in an input data set (or needs to iterate once through every value in the input), it is said to have a Time complexity of order O (n).
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
          When the running time of an algorithm increases non-linearly O(n^2) with the length of the input
          In general, nested loops fall into the O(n)*O(n) = O(n^2) time complexity order, where one loop takes O(n) and if the function includes loops inside loops, it takes O(n)*O(n) = O(n^2)
          Similarly, if the function has ‘m' loops inside the O(n) loop, the order is given by O (n*m), which is referred to as polynomial time complexity function.
            Examples:
              - Multiply two-n-digit numbers
              - Bubble, Insertion, Selection Sort

 
 ### Stack
 --> think of washing dishes --> you start from most top dish to most below --> you wash the last dish added first
 
 - Last-In first -out structure
 - Attributes: a container that holds multuple dat

--> pop remove last added
--> push adss value

--> see it the most in "undo feauture" --> every time we click undo we are "popping" last thing added 
--> we use this as every operation is O(1) operator

### Queue
--> first in first out (FIFO) sturcture --> whatever is first gets served first --> opposite of stack
Methods
  - enqueue --> adds elements
  - dequeue --> removes and returns the first/ealirest added element

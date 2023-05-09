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
 
   O(1) → Constant Complexity
        Constant Time Algorithms: Completes the execution in the same amount of time regardless of its input.
        - Where an algorithm's execution time is not based on the input size n
        - Whatever be the input size n, the runtime doesn’t change.
            Examples:
              - Accessing a data point in a list with a known index 
              - Given two numbers, report the sum
              
    O(log n) → Logarithmic Complexity
        If N was the size of the input, the algorithm will take log(n) steps to solve a problem.
         will use a log with a base of 2 → log2 
          - When the input set is continuously divided by two, it is usually a logarithmic complexity algorithm
          - When an algorithm decreases the magnitude of the input data in each step
          - Means that the number of operations is not proportionate to the size of the input.
          - O (log2 n) basically implies that time increases linearly while the value of 'n' increases exponentially.
          - So, if computing 10 elements take 1 second, computing 100 elements takes 2 seconds, 1000 elements take 3 seconds
              - Example:
                  -  Binary Search 
                  
    O(n) → Linear Complexity
        The completion of the algorithm is directly proportional to the size of the input.
        When the running time of an algorithm increases linearly with the length of the input
              -  i.e. when a function checks all of the values in an input data set 
                  (or needs to iterate once through every value in the input), it is said to have a Time complexity of order O (n).
              - Search for an item in a list
              - Searching a queue
              - Adding two n-bit integers
              
   O(n log n) → Linearithmic Complexity
        The completion of the computation grows in a linear pattern with a rate of change of a logarithm
            Examples:
              - Heapsort
              - Mergesort
              
   O(n2) → Quadratic Complexity
          Quadratic Complex Algorithms: performance is directly proportional to the square of the size of the input data set.
          When the running time of an algorithm increases non-linearly O(n^2) with the length of the input
          In general, nested loops fall into the O(n)*O(n) = O(n^2) time complexity order, where one loop takes O(n) and if the function includes loops inside loops, it takes O(n)*O(n) = O(n^2)
          Similarly, if the function has ‘m' loops inside the O(n) loop, the order is given by O (n*m), which is referred to as polynomial time complexity function.
            Examples:
              - Multiply two-n-digit numbers
              - Bubble, Insertion, Selection Sort

## Recursion 
  - a method to solve computational problem by relying on smaller instances of a solution to a given problem. 
  - The logic is that if we have a base case that helps to solves the smaller instance, then the base case solution helps to solve the bigger version of the solution.
  - calls itself again and again until we hit a base case
  -  “defining something in terms of itself”
 
 ### Basic idea
Let P be a problem:
    Divide P into two or more subproblems (smaller instances)
    Divide until the subproblems are simple enough to be solved
    All the subproblem solutions are then combined to give a solution to the original problem
    This is a basic program solving approach called: 
        “Divide and Conquer Algorithm”
    This also leads to the basis of “Dynamic Programming”
    
 ### Recursion formula
1. Base Case (i.e., when to stop)
2. Work toward Base Case
    where we make the problem simpler
3. Recursive Call (i.e., call ourselves)

**HOW DOES IT WORK THOUGH???**
  - In a recursive algorithm, the computer "remembers" every previous state of the problem
  - This information is "held" by the computer on the "activation stack" (i.e., inside of each functions workspace).
  - Every function has its own workspace PER CALL of the function.

#### Developing a base case
  - The base case should hold the simplest solution for the simplest, smallest instance of the problem
  - In a recursion algorithm, the problem is broken down to subproblem until we reach the base case
  - Recursion Algorithms can have **multiple** base cases
  - Base cases are considered “end conditions”
 
 ### Ex - “From N, add all the numbers below it until 0”
 ``` python
 r_sum(n):
	if n is 0, return 0
if n is 1, return 1
	else: return n + r_sum(n-1)
  ```
 Visual of how it works^^^
 r_sum(5) → 5 + r_sum(4)    
  r_sum(4) → 4 + r_sum(3)
    r_sum(3) → 3 + r_sum(2)
      r_sum(2) → 2 + r_sum(1)
        r_sum(1) → 1
r_sum(5) → 5 + 10
  r_sum(4) → 4 + 6
    r_sum(3) → 3 + 3
      r_sum(2) → 2 + 1
        r_sum(1) → 1
thereforeeeee ans = 15

### Single vs Multiple 
Single → It only calls itself once … only invokes one recursion to occur
(Adding up all numbers in a list)

Multiple → It can invoke multiple recursion to solve the answer
(Fibonacci → Fib(n) = Fib(n-2) + Fib(n-1)

### Direct vs Indirect 
Let f and g be functions.
  Direct → f only calls f
  Indirect → f calls g in which g calls f (can create longer chains)
    --> Indirect recursion can be also referred to as “mutual recursions”
    
### Tail vs Non tail
  Tail Recursion → The function call is the last thing that a function does.
  Tail Recursion is more efficient in terms of memory because it only does calculations at the very last recursive call.
  
#### Example: Adding all values from N to 1
``` python

def f(n): # non-tail
	if n == 1:
		return n
	else:
		return n + f(n-1)
def g(n, track=0): # tail
	if n == 0:
		return track
	else:
		return g(n-1, track + n)
```
           
## Linear Search
  - An algorithm designed to find a target value within a list/dataset
  - Sequentially checks all the items in a list until the target is found
**Linear Search → O(n) ; Linear Complexity**
  - At worst, the last object will be the target or the target won’t exist in the list
  - Best Performance → O(1) # First Item
  - Average Performance → O(n/2) = O(n) # Somewhere in the middle of the set, still linear complexity

index() and find() are linear searches
in and not in membership for strings and lists are linear searches 

 ``` python 
 def linear_search1(sequence, target):
    i = 0
    while i < len(sequence):
        if sequence[i] == target:
            return i
        i += 1
    # end of while
    return -1 # if target NOT in sequence 
    # end of linear_search1
    
def linear_search2(sequence, target):
    # Park's way of writing this search in Python
    for i, current_value in enumerate(sequence): # enumerate -->  essentially helps us look at index value???
    
        ''' lets say L is [a,b,c] 
        enumerate([a,b,c]) --> (0, a) , (1, b), (2, c)
        in our loop ...
        i --> index
        current_value --> the value in our sequence
        '''
        
        if target == current_value:
            return i
    # end of for loop
    return -1
# end of linear_search2
```
## Binary Search
  -  A searching algorithm that is designed to search from a **sorted** list.
Idea:
  - Compare the target with the middle most value
  - If not found, eliminate the half where the target cannot exist 
  - if search value is LESS than target value --> mid becomes new upper bound ( right)
  - if search value is GREATER than target value --> mid becomes new lower bond (left)
Cons:
  - The database must be comparable and sortable

Big O Notation → O(log n)
We are splitting the dataset continuously into halves until we hit our target or not find our target
Very efficient!

``` python
def binary_search(sequence, target):
    if not sequence: # empty dataset situation
        return -1
    else:
        left = 0
        right = len(sequence) - 1
        while left <= right:
            middle = (left + right) // 2
            if sequence[middle] == target:
                return middle
            elif sequence[middle] < target:
                left = middle + 1 # since target greater than value, left is now updated and is new lower bond
            else: # sequence[middle] > target
                right = middle - 1 # since target is less than value, right is now updated and new upper bond in array
        # end of while
        return -1
```

questions
- how do you look at a question and understand if it will be recurssive or not
- 


 ### Stack
 --> think of washing dishes --> you start from most top dish to most below --> you wash the last dish added first
\

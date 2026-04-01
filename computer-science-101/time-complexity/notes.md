## Time Complexity

 * _N-notation_ - is not the analysis of how long an algorithm takes to run, but an analysis of how the algorithm will scale wit more and more input data
  * rules for N-notation 
    1. We don't care about multiples, only input -> logic -> output
    2. We take the largest in the equation
 
* _log_ - stands for logarithmic and is the inverse of exponential functions. 
* where an _exponential function_ grows over time, a _log function_ grows less and less over time

### Types of Time Complexity
  - **_*factorial* - num!_**
    * where the num would be the number that would be multiplied by each preceding value
    * factorials are the worst runtime. If your runtime is a factorial it should be recomputed with a different function/class 
      examples: 
      1. 3! would be 3 * 2 * 1  which would equal 6 
      
      2. 5! would be 5 * 4 * 3 * 2 * 1 which would equal 128 

  - **_*log* - num^num_**
    * where the number would be the value that is being multiplied by itself ^num of times

      examples
      1. 3^3 would be 3 * 3 * 3 = 27

      2. 2^3 would be 2 * 2 * 2 = 8
    
  - **_*nlog(n)_**
    * where n is the amount of data 
    * log is always to the power of 2 because computers run in 0s and 1s which is 2 places

      examples 
      1. if n=16 16log(16) would be 2^n = 16 where n = 4 so 16 * 4 = 64
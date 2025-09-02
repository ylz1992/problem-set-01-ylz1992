  # CMPS 6610 Problem Set 01
## Answers

**Name:**_________________________
**Name:**_________________________


Place all written answers from `assignment-01.md` here for easier grading.

1. **Asymptotic notation**
  - 1a
  True. \\
  There exist constant $c \geq 2$ and $n_0 = 0$, such that for all $n \geq n_0$ :
  $$2^(n+1) \leq O(2^n)$$
  - 1b    
  False.\\
  $$2^{2^n} \leq 2^{\log_{2} c} * 2^n$$
  $$2^n \leq \log_{2} c + n $$
  since $2^n$ is exponential, and $(\log_{2} c) + n$ is linear, the equation not achieve.\\
  - 1c
  False.\\
  since $n^1.01$ is polynomial (n>1), while $(\log_{2} n)^2$ grows slower than linear.\\
  So this equation not achieve. \\
  - 1d
  True. \\
  Same logic as 1c.\\
  - 1e
  False. \\
  $$\sqrt{n} \leq c* (\log n)^3 $$
  let $x = \ln n$ for n>1, then we have $e^(x/2) \leq c * (x^3)$. However, $e^(x/2)$ is exponential, while $ c* (x^3)$ is polynomial. Then the equation not achieve.\\
  - 1f
  True. \\
  same logic as 1e \\

  - 1g
  let's say $f(n) \in o(g(n))$ and $f(n) \in w(g(n))$ \\
  so for every constant c>0, there exist $n_0$ such that for all $n>n_0$ \\
  $f(n) \le c * g(n)$ and $f(n) \ge c * g(n)$ \\
  This is impossible, so the set is empty.

2. **SPARC to Python**

  - 2b
  return max(a,b)
  - 2c
  if a == 0 : O(1) \\
  return b :  0 \\
  if b == 0 : O(1) \\
  return a : 0 \\
  x,y = min(a,b), max(a,b) : O(1) \\
  return foo(y, y%x) : O(1) \\
  The recursive step should be $O(\log min(a,b))$ times, so the total work is : \\
  w(foo()) = $4 * O(\log min(a,b)) * O(\log min(a,b))+1 = O(\log min(a,b)) = O(\log n)$ \\
  Since foo() is serial, then span would be same as work:\\
  s(foo()) =  $O(\log n)$ 
  


3. **Parallelism and recursion**

  - 3b
  (1): O(1)\\
  (2): O(1)\\
  (3): O(n)\\
  (4): O(1)\\
  (5): O(1)\\
  (6): O(1)\\
  (7): O(1)\\
  (8): O(1)\\
  w(longest_run()) = O(n)\\
  s(longest_run()) = w(longest_run()) = O(n) since this is a serial process.

  - 3d
  I use tree structure with a divide of 2. So the work would be total number of nodes, and span would be length of longest path.\\
  w(longest_run_recursive()) = 2x w(n/2)+1 = O(n)\\
  s(longest_run_recursive()) = O($\log{2} n$) = O($\log n$) \\ 

  - 3e
  the work is the same, which is O(n) \\
  span would be O($\log{2}(n/2)$) +1 since we divide with two process, which is also O($\log n$)

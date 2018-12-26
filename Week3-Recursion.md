Recursion
==========

Recursion
--------

Factorial Function  
**Definition**: For a positive integer n, the factorial of n is the product of integers from 1 to n.  
  
5! = 1 * 2* 3 * 4 * 5 = 120 = 4! * 5

Recursive definition  
  n! = 1 if n = 1
  n * (n-1)! if n > 1

Termination
* One must ensure that a recursive program(or definition) terminates after a finite number of steps
* This is ususally achieved by decreasing some parameter until it reaches a base case

Coin Problem
----------

Problem:
Prove that any monetary amount starting from 8 can be paid using coins of denominations 3 and 5.  
  
How can we be sure taht it is always possible?  
  
Recursive Program
  def change(amount):
    assert(amount >= 8)
    if amount == 8:
      return [3,5]
    if amount == 9:
      return [3,3,3]
    	if amount == 10:
      	return [5,5]

	coins=change(amount-3)
	coins.append(3)
	return coins

5, 7

10 [5,5]
12 [5,7]
14 [7, 7]
15 [5,5,5]
17 [5,5,7]
19[5,7,7]
20[5,5,5,5]
21[7,7,7]
22[5,5,5,7]
24[5,5,7,7]
25[5,5,5,5,5]
26[5,7,7,7]
27[5,5,5,7,7]
28[7,7,7,7]

Hanoi Tower
----------

* We've constructed a solution for all n:
  - Base case: it is possible for n = 1
  - Hence, it is possible for n = 2
  - Hence, it is possible for n = 3
  - ...
* We'll later learn a related notion of induction

def hanoi(number)
	

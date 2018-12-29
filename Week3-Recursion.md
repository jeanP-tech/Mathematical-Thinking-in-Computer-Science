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

> Q. The number of moves required to solve the Hanoi Towers puzzle for n=1n=1 and n=2n=2 discs is equal to 1 and 3, respectively. Implement the recursive solution for the Hanoi Towers (described in the lectures) and count the number of moves for n=6n=6 discs.
	
> A. 63. In fact, it is known that the number of moves is 2^n-1. More formally, any solution makes at least 2^n-1 moves and there is a solution that makes exactly 2^n-1 moves (it was described in the videos). Thus, 2^n-1 is the optimal number of moves to solve this puzzle.
 
Induction
========

introduction, Lines and Triangles Problem
-----------
Mathematical Induction
- A very powerful proof method
- Falling dominos
- Check for 1, 2, 5, 100, 1000 dominos
- How to prove for any number of dominos?
- Many computer science algorithms are proven.

> Problem
> Several straight lines(at least three) cut a plane into pieces. Each line intersects with every other line, and all the intersection points are different. Prove that there is at least one triangular piece. 

> Proof Idea
- A triangle appears as soon as there are 3 lines
- When we add more lines one by one, each time
	- Either the same triangle remains...
	- Or a new one appears

Lines and Trinagles: Proof by Induction
-----------
3 -> 4 -> 5 - > k  
  
k : trinagle  
k +1: new triangle appears  
  
Mathematical Induction
- Prove induction base n = 3, three lines
- Prove induction step from n to n + 1 - adding one more line in the general case
- ...
- Profit

Sum of Numbers
-----------

General case
>Problem: What is the sum of integer numbers from 1 to n?
>Theorem: The sum of integers from 1 to n is n(n+1) / 2

Bernoulli's Inequality
-----------------

>Problem
>You start with $1000 and earn 2% of what you have every day. Will you ever get more than $1,000,000?

On day n, you have $1,000 * 1.02^(n-1)

>Problem
>Is there such n that 1000*1.02^n > 1000000? Or, is there such n that 1.02^n > 1000?

>Theorem
>For any n>=0 and x>0, (1+x)^n >= 1 + nx

Coins Problem
------------

>Problem
>You have an unlimited supply of 4 cents and 5 cents coins. Prove that for any n>= 12, you can give change of n cents using these coins.

Proof by Induction
>Induction base: n = 12  
Indeed, 12 = 3*4, so using just 4 cents coins is enough

Complete Induction
>Induction base: n = 12, n = 13, n = 14 and n = 15  
12 = 3*4
13 = 2*4 +1*5
14 = 2*5 +1*4
15 = 3*5

Induction step: n, n-1, n-2, n-3 -> n+1  
If we know that n-3 can be given with 4 cents and 5 cents coins n-3 = a*4 + b*5, then n+1 also can be given with tese coins:    
n +1=(n-3) + 4 = a*4 + b*5 + 4 = 



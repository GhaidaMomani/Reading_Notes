# Read Class 02
## Code 401 - Advanced Software Development
<!-- 
       Hope you'll benefit from my reads, Enjoy!
-->




By [Ghaida Al Momani] (https://github.com/GhaidaMomani).
<br/>
<hr/>
<br/>


## Description
**Reading**

In Tests We Trust - TDD with Python (https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)

If name equals main ()
Recursion



<hr/>
<br/>


## Unit tests and TDD


Unit tests are some pieces of code to exercise the input, the output and the behaviour of your code. You can write them anytime you want.
The first one is the test name. The tests can be considered as your alive documentation. We need to be descriptive about it and to say what is expected and what we are testing.
The test file name should follow the same name of module name. For instance, if our module is gender.py, our test name should be test_gender.py. It’s ideal to separate the tests folder from production code (the implementation)
Other thing to care about is the structure. A convention widely used is the AAA: Arrange, Act and Assert.



<br/>

## Other thing to care about is the structure. A convention widely used is the AAA: Arrange, Act and Assert.


Arrange: you need to organize the data needed to execute that piece of code (input);

Act: here you will execute the code being tested (exercise the behaviour);

Assert: after executing the code, you will check if the result (output) is the same as you were expecting.


<hr/>
    <p align="right">(<a href="#top">back to top</a>)</p>


   
## Recursion
**What is Recursion?**

The fundamental part of recursion is self-reference - functions calling themselves. It is used to solve problems that can be broken up into easier sub-problems of the same type.
What is base condition in recursion?
In the recursive program, the solution to the base case is provided and the solution of the bigger problem is expressed in terms of smaller problems.
<br/>



 as you can see in this example base case for n < = 1 is defined and larger value of number can be solved by converting to smaller one till base case is reached.

```

def factorial(x):
  if x == 1:
    return 1
  else: 
    return x * factorial(x-1)
    
print(factorial(5))

```
<br/>

## How memory is allocated to different function calls in recursion?

When any function is called from main(), the memory is allocated to it on the stack. A recursive function calls itself, the memory for a called function is allocated on top of memory allocated to calling function and different copy of local variables is created for each function call. When the base case is reached, the function returns its value to the function by whom it is called and memory is de-allocated and the process continues.

<hr/>
    <p align="right">(<a href="#top">back to top</a>)</p>





  <br/><br/>

<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
  <p align="right">22, 28 Feb </p>
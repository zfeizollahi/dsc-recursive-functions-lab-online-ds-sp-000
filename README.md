
# Recursive Functions - Lab

## Introduction

Now that you've seen a little preview of recursive functions, it's time to give them a try!

## Objectives
You will be able to:
* Understand and use the concept of a recursive function 
* Understand scope in the context of recursive functions
* Understand and compare depth first versus breadth first searches

## Fibonacci

The Fibonacci sequence starts off:
1,1,2,3,5,8,13,21,34,...

Each number is the sum of the two preceding. Write a recursive function that calculates the nth number of the Fibonacci sequence. For example, our sequence above would correspond to:

fib(1) = 1 #The 1st element in the sequence is 1

fib(2) = 1 #The 2nd element in the sequence is 1

fib(3) = 2 #The 3rd element in the sequence is 2

fib(4) = 3 #The 4th element in the sequence is 3

fib(5) = 5 #The 5th element in the sequence is 5

fib(6) = 8 #The 6th element in the sequence is 8

fib(7) = 13 #The 7th element in the sequence is 13

fib(8) = 21 #The 8th element in the sequence is 21

fib(9) = 34 #The 9th element in the sequence is 34


```python
#Your code here
def fib(n):
    if n < 1:
        return "Cannot do"
    elif n in [1, 2]:
        return 1
    else:
        return fib(n-1) + fib(n-2)
for i in range(1, 10):
    print(fib(i))
```

    1
    1
    2
    3
    5
    8
    13
    21
    34


## Flat List

Write a function that takes a nested list and flattens it to a list of ints, floats and strings.
For example the nested list [1,[2,3[4,5,6]], 7, [8], [9,10]] would become [1,2,3,4,5,6,7,8,9,10] or 
[1,2[3,4,[5]]] would become [1,2,3,4,5].

> **Note**: Be careful how you initialize your function! See [this link](https://docs.quantifiedcode.com/python-anti-patterns/correctness/mutable_default_value_as_argument.html) for some potential pitfalls you could encounter if you're not careful!


```python
#Your code here
def flat_list(L, flattened=None):
    if not flattened:
        flattened = []
    for i in L:
        if isinstance(i, list):
            print("{} is a list".format(i))
            flat_list(i, flattened)
        else:
            print(i)
            flattened.append(i)
    return flattened
L = [1,[2,3,[4,5,6]], 7, [8], [9,10]]
flat_list(L)
```

    1
    [2, 3, [4, 5, 6]] is a list
    2
    3
    [4, 5, 6] is a list
    4
    5
    6
    7
    [8] is a list
    8
    [9, 10] is a list
    9
    10





    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]



## Depth vs Breadth First Search

Did you use breadth or depth first recursive calls above? Explain.

Depth first - because I go down through each elements sublist before i move on to the next element in the outer list.

## Summary
Well done! Recursive functions are an advanced topic in Python and you got some good practice tackling classic problems here.

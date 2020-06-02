# Advanced Python Concepts for Researchers
Author: @mojtaba-eshghie

## Lambda Expressions
*This is a way to define anonymous functions in python.
May have any number of inputs, but just one expression as the body.* 

    def cube(x):\
        return x*x*x \
    g = lambda x: x*x*x \
    print(g(7))
    print(cube(7)) 


### Use of lambda with filter function
*The filter function receives the a function object and a list as the arguments, then, it will filter out all of the elements of the list based on which the function returns true for.*

    l = [1, 2, 3, 4]
    # you have to use a list on the object returned by filter
    result = list(filter(lambda x: x > 2, l))

### Use of lambda with map function

*Likewise the map function will receive a function and a list of arguments, and will return the sequence of all results of the given function with each and every of list elements as an argument*

    l = [1, 2, 3, 4]
    # you have to use a list on the object returned by filter
    result = list(map(lambda x: x > 2, l))

### Use of lambda with reduce function

*reduce is going to 'reduce' an interable to a single element! \
It works from left to write (iteratively). For instance:*

    l = [1, 2, 3, 4]
    result = reduce((lambda x, y: x + y), l)

*The mentioned code will calculate like ((((1+2)+3)+4)+5)*


## Choosing an item with particular probability with python
*The function np.random.choice(l, n, p) returns the element l[i] with probability p[i] (p is like a probability distribution function). The sample size will be n*

    import numpy as np
    np.random.choice([i for i in range(5)], 1, [0.2 for i in range(5)])
    # This will return 1 number (sample size is one) from a list with uniform probability
    
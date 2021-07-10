# Task for Python Day 1

## Problem 1 - Lagrange Interpolation

Lagrange interpolation is a [polynomial
interpolation](https://en.wikipedia.org/wiki/Polynomial_interpolation) method
which uses polynomials known as [Lagrange
Polynomials](https://en.wikipedia.org/wiki/Lagrange_polynomial). This method
works on a set of **uniqe** points, and results in a polynomial with degree
one less than the number of data points - which passess through all the data
points.

Your task is to write a function `lagrange_polynomial()` which takes in a list
of data points (which are two element lists themselves), and another argument,
and returns the value of the interpolating polynomial at the given argument.

```python
lagrange_polynomial(datalist, xvalue)
# datalist is a list of points, like [[1,2],[4,9],[13,27]] etc.
# xvalue is value at which we need the interpolating polynomial to be evaluated.
# example use case is:
yval = lagrange_polynomial([[8, 6], [1, 3], [3, 8]], 4)
print(yval)
```

```
out: 9.257142857142858
```

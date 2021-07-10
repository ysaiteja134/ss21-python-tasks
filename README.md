# Task for Python Day 1

### Deadline: 11/07/2021 12:00 PM

## Rules

1. Use only commands, functions, datatypes from [Python Part 1](https://github.
   com/HorizonIITM/summer-school-2021/tree/master/week-01/python) class.
2. You are free to use whatever resource to learn about the subject of task.
   Please avoid plagiarism - the task is for you to learn, not for us to evaluate
   you.
3. Refrain from using pre-existing libraries/functions/other structures. Both
   problems are completely doable using the content for Python Part 1 class.
4. **Both the problems are mandatory**.

## Problem 1 - Lagrange Interpolation

Lagrange interpolation is a [polynomial interpolation](https://en.wikipedia.org
/wiki/Polynomial_interpolation) method which uses polynomials known as [Lagrange
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

Output:

```
9.257142857142858
```

## Problem 2 - Inverted ROT-N Cipher

Cipher is an element of cryptography - which is essentially a set of rules to
encrypt (and decrypt) a message (encrypted message). One example of such cipher
is the [ROT13](http://practicalcryptography.com/ciphers/classical-era/rot13/)
cipher, which is: shift each alphabet of the message forward by 13 counts. By
this rule `a` becomes `n`, `b` becomes `o` and so on:

```
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
│ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │ │
▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼ ▼
N O P Q R S T U V W X Y Z A B C D E F G H I J K L M
```

The cipher we discuss will have the number of shifts as a variable, rather than
sticking to 13 like ROT-13 does (hence the name ROT-N).

Another simple example of cipher is the Atbash cipher, where the letters of the
alphabet are reversed. The goal of this problem is to create a two functions
`inv_rotn_encrypt()` and `inv_rotn_decrypt()` - one for encrypting, one for
decrypting. The arguments for these functions is as follows:

```python
inv_rotn_encrypt(message, shift)
# message is the message to be encrypted
# shift is the number of letters to shift
inv_rotn_decrypt(secret, shift)
# secret is the encrypted message to be decrypted to obtain original message
# shift is the number of shifts used to encrypt the original message
```

Encrypting process:

1. Shift the letters of the message by the number specified by `shift` argument.
   (note that the shift argument should always be an integer, as the concept of
   fractional shift is absurd).
2. Reverse the order of the letters obtained from previous step.
3. Return the encrypted message obtained thus.

Decrypting process:

1. Reverse the order of characters in the given encrypted message.
2. Shift backwards the string obtained from previous step by the specified
   `shift` number.
3. Return the decrypted message obtained thus.

An example workflow would be:

```python
message = 'bobody'
print("Message: ", message)
secret = inv_rotn_encrypt(message, 17)
print("Encrypted message: ", secret)
message_again = inv_rotn_decrypt(secret, 17)
print("Decrypted message: ", message_again)
```

Output:

```
Message: bobody
Encrypted message: valyly
Decrypted message: bobody
```

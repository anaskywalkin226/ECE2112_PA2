# Programming Assignment 2
## Problem 1: Normalization Problem
```py
import numpy as np
```
Step 1: Importing the NumPy library is the most important step when using Python for numerical computations. We use this whenever we'd like to call codes requiring NumPy to run.
```py
x = np.random.random((5,5))
```
Step 2: Generate a random 5 x 5 table as instructed and set it to variable x for further numerical computations

```py
xnormalization = (x - x.mean())/x.std()
```
Step 3: Using the formulas given, use the values generated from the last line of code to get the mean and the standard deviation of x; where the values are assigned. Then, set the computed normalized values of x into a variable, in my case it is "xnormalization".

```py
np.save("X_normalized.npy", xnormalization)
```
Step 4: Now that we have the values, we now saved the values that are stored in the variable "xnormalization" to a NumPy file named "X_normalized.npy".

```py
x
array([[0.64250866, 0.40890333, 0.33352226, 0.00724067, 0.58050523],
       [0.99488929, 0.92073605, 0.4089425 , 0.2963066 , 0.08472271],
       [0.45965745, 0.79769828, 0.11149664, 0.43206725, 0.07972833],
       [0.40408901, 0.88293996, 0.45962057, 0.21367582, 0.61439223],
       [0.73861986, 0.41586628, 0.0587724 , 0.11011237, 0.11815613]])

n = np.load("X_normalized.npy")
n
array([[ 0.76971793, -0.04945602, -0.31379164, -1.45794951,  0.55229311],
       [ 2.00539618,  1.74536615, -0.04931866, -0.44429422, -1.18624653],
       [ 0.12852131,  1.31391482, -1.09235951,  0.03177191, -1.20376011],
       [-0.0663382 ,  1.61282822,  0.12839196, -0.73405208,  0.67112324],
       [ 1.10674701, -0.02503935, -1.27724537, -1.09721366, -1.06900698]])
```
Step 5: Checking the values stored in variables x and X_normalized.npy to double check  
## ----------------------------------------------------------------------------------------------
## Problem 2: Divisible by 3 Problem
```py
import numpy as np
```
Step 1: Importing the NumPy library is the first and most important code to run when tackling numerical computations with Python, hence this is the first step.
```py
a = np.arange(1, 101)
```
Step 2: We generate an array that ranges from values of 1 to 100 in increments of 1 and we store those values in variable a. We made the last range 101 so that 100 can be stored as a value as well as python does not include the last value in a range.
```py
squarenumbers = a ** 2
```
Step 3: We now get the square of each of the values in the array stored in variable a, and then we set those values to another variable named "squarenumbers"
```py
squarenumbers.size
100
```
Step 4: To make sure that we got the correct values, we run syntax: "variable.size".
```py
A = squarenumbers.reshape(10, 10)
```
Step 5: We now reshape the values stored in variable "squarenumbers" into a 10x10 structure (10 rows, 10 columns)
```py
A #checking final array if process was done right
array([[    1,     4,     9,    16,    25,    36,    49,    64,    81,
          100],
       [  121,   144,   169,   196,   225,   256,   289,   324,   361,
          400],
       [  441,   484,   529,   576,   625,   676,   729,   784,   841,
          900],
       [  961,  1024,  1089,  1156,  1225,  1296,  1369,  1444,  1521,
         1600],
       [ 1681,  1764,  1849,  1936,  2025,  2116,  2209,  2304,  2401,
         2500],
       [ 2601,  2704,  2809,  2916,  3025,  3136,  3249,  3364,  3481,
         3600],
       [ 3721,  3844,  3969,  4096,  4225,  4356,  4489,  4624,  4761,
         4900],
       [ 5041,  5184,  5329,  5476,  5625,  5776,  5929,  6084,  6241,
         6400],
       [ 6561,  6724,  6889,  7056,  7225,  7396,  7569,  7744,  7921,
         8100],
       [ 8281,  8464,  8649,  8836,  9025,  9216,  9409,  9604,  9801,
        10000]])
```
Step 6: Printing the values of variable "A" so we can make sure that the process was done correctly.
```py
numbersdivby3 = A[A % 3 == 0]
```
Step 7: Now we find for the values stored in variable "A" that are divisible by 3 without remainders.
```py
numbersdivby3
array([   9,   36,   81,  144,  225,  324,  441,  576,  729,  900, 1089,
       1296, 1521, 1764, 2025, 2304, 2601, 2916, 3249, 3600, 3969, 4356,
       4761, 5184, 5625, 6084, 6561, 7056, 7569, 8100, 8649, 9216, 9801])
```
Step 8: Print the numbers stored in variable "numbersdivby3" to make sure.
```py
np.save("div_by_3.npy", numbersdivby3)
```
Step 9: We save the values stored in variable "numbersdivby3" into a numpy file named "div_by_3.npy"
```py
loaded = np.load("div_by_3.npy") #checking if saved
loaded
array([   9,   36,   81,  144,  225,  324,  441,  576,  729,  900, 1089,
       1296, 1521, 1764, 2025, 2304, 2601, 2916, 3249, 3600, 3969, 4356,
       4761, 5184, 5625, 6084, 6561, 7056, 7569, 8100, 8649, 9216, 9801])
```
Step 10: Run the saved numpy file to make sure.

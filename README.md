## <center> __University of Santo Tomas – Faculty of Engineering Electronics Engineering Department__ </center>
## <center> __ECE 2112: Advanced Computer Programming and Algorithms__ </center>
# <center> __EXPERIMENT 1: INTRODUCTION TO PYTHON PROGRAMMING__ </center> 
#### Emmanuelle D.G. Miran| 2ECE-C
## **I.** Intended Learning Outcomes
1. Create and reshape NumPy arrays using appropriate NumPy functions;
2. Perform vectorized numerical operations on an ndarray;
3. Compute array statistics and use Boolean conditions to select elements; an
4. Save computed NumPy arrays as .npy files.

## **II.** Numpy Initialization
```python
import NumPy as np
```
## **III.** Programming Problems   
>  ##  **A.** REPRODUCIBLE NORMALIZATION PROBLEM
> Create a reproducible random 5 × 5 integer ndarray named X. Use the following two statements before performing any calculation:
np.random.seed(2112)
```python
X = np.random.randint(10, 101, size=(5, 5))
```
> Normalize the complete array using:
> Z = X − ¯x / σ 
><br>where x is the mean of all 25 elements and σ is their population standard deviation as returned by NumPy’s default std() call. Store the normalized array in X_normalized.
> <br><br>
> Required checks: Display X, X normalized, its mean, and its standard deviation. Up to floating-
point rounding, the normalized mean must be 0 and the normalized standard deviation must be 1.
Save the normalized array as:<br>
> **X_normalized.npy**
> ## Explanation
>> For this programming problem, we use ***np.random.seed()*** to ensure that when we run our function, it will always produce the exact same sequence of numbers, no matter how many times we run our function. In this function's case, we use the seed **2112**, which produces a specific sequence of numbers that we want to reproduce over and over again.
>> <br><br>
>>  ***X = np.random.randint(10, 101, size=(5, 5))***, the first part of this function which is **np.random.randint()** allows us to generate an integer in its given range, which in this case would be an integer from 10 to 100, as expressed by the **(10, 100)**, the **size=(5, 5)** part of this function tells the function to make a 5x5 array when generating these random integers, lastly the **X=** basically tells the function to refer to this entire 5x5 array simply as **X**.
>> To accomplish the formula given above, we need to use ***mean_X = X.mean()*** for computing the mean of the array, and ***std_X = X.std()*** for computing the standard deviation of the array. To normalize the values of the array, we need to use ***(X - mean_X) / std_X***
>> <br><br>
>> For this problem we need to save the array as **X_normalized**, so we need to use the function ***X_normalized = (X - mean_X) / std_X***
>><br><br>
>> For the condition we need to meet with this problem, we need to be able to save this as **X_normalized.npy** by using the function **np.save()** in this problem's case we use **("X_normalized.npy", X_normalized)** to tell the function to save the file as **X_normalized.npy** and the array that we will use would be be the **X_normalized** that we saved earlier.
> ## Code & Outputs

```python
np.random.seed(2112)
X = np.random.randint(10, 101, size= (5, 5))
X
```
```
array([[48, 11, 15, 67, 21],
       [11, 41, 13, 66, 24],
       [71, 79, 53, 67, 70],
       [77, 35, 91, 19, 96],
       [35, 54, 37, 41, 17]], dtype=int32)
```
```python
mean_X = X.mean()
mean_X 
```
```
np.float64(46.36)
```
```python
std_X = X.std()
std_X 
```
```
np.float64(25.864075471588002)
```
```python
X_normalized = (X - mean_X) / std_X
X_normalized
```
```
array([[ 0.06340841, -1.36714726, -1.2124926 ,  0.79801809, -0.98051059],
       [-1.36714726, -0.20723725, -1.28981993,  0.75935442, -0.86451959],
       [ 0.95267275,  1.26198209,  0.25672675,  0.79801809,  0.91400909],
       [ 1.18465476, -0.43921926,  1.72594609, -1.05783793,  1.91926443],
       [-0.43921926,  0.29539042, -0.36189192, -0.20723725, -1.13516526]])
```
```python
np.mean(X_normalized)
```
```
np.float64(0.0)
```
```python
np.std(X_normalized)
```
```
np.float64(0.9999999999999999)
```
```python
np.save("X_normalized.npy", X_normalized)
```

>  ##  **B.** Cubes Divisible by 4 Problem
>Using NumPy, create the first 100 positive integer, cube every element, and reshape the result into a 10 × 10 ndarray named C. Thus, C begins with 1^3 and ends with 100^3.
><br><br>
>Use a Boolean condition on C to obtain every cubed value divisible by 4. Store the selected values in
div by 4. Preserve NumPy’s normal row-major selection order.
><br><br>
>**Required checks**: Display the shape of C, the array div by 4, and the number of selected elements.
A correct solution has 50 selected elements; the first is 8 and the last is 1,000,000.<br>
Save the selected array as: **div_by_4.npy**
> ## Explanation
>> For this programming problem, we use ***np.arange()*** to create a 1-dimensional array within a given range of numbers, which in this case would be 1 to 100. In the function, we use ***(1, 101)*** because in this function, the 101 is not included, therefore making the range of this array the first 100 positive integers.<br><br>
>> The next thing we need to do is to reshape this 1-dimensional array into a 10 x 10 ndarray named "C" while also raising all the first 100 positive integers by 3. To do this, we use the function "C = (np.arange(1, 101)* *3". To explain this code, we simply use ***C=*** to declare "C" is the same as "np.arange(1, 101)" and to raise all the integers by 3, we simply add "**3" into it at the end. To reshape the 1-dimensional array into a 10x10 ndarray, we just use the function ***.reshape(10,10)***.<br><br>
>> For the last condition, we need to be able to display every single integer that is divisible by 4, and for the solution to be correct, the first value selected must be 8, and the last should be 1,000,000. To accomplish this, we use the function ***div_by_4 = C[C % 4 == 0]***. This function selects all integers divisible by 4 from the function **C** this also saves the array as **div_by_4**.
>> <br><br> Lastly, we need to save this array as **div_by_4.npy** so we will use the function ***np.save()*** again as we did in the first problem.
>> <br><br> For checks, we can use ***np.size()*** to count the number of integers in the final array, which should be 50 as required by the problem. And ***np.shape()*** to show the shape of C.
> ## Code & Outputs
```python
C = (np.arange(1, 101) ** 3).reshape(10, 10)
C
```
```
array([[      1,       8,      27,      64,     125,     216,     343,
            512,     729,    1000],
       [   1331,    1728,    2197,    2744,    3375,    4096,    4913,
           5832,    6859,    8000],
       [   9261,   10648,   12167,   13824,   15625,   17576,   19683,
          21952,   24389,   27000],
       [  29791,   32768,   35937,   39304,   42875,   46656,   50653,
          54872,   59319,   64000],
       [  68921,   74088,   79507,   85184,   91125,   97336,  103823,
         110592,  117649,  125000],
       [ 132651,  140608,  148877,  157464,  166375,  175616,  185193,
         195112,  205379,  216000],
       [ 226981,  238328,  250047,  262144,  274625,  287496,  300763,
         314432,  328509,  343000],
       [ 357911,  373248,  389017,  405224,  421875,  438976,  456533,
         474552,  493039,  512000],
       [ 531441,  551368,  571787,  592704,  614125,  636056,  658503,
         681472,  704969,  729000],
       [ 753571,  778688,  804357,  830584,  857375,  884736,  912673,
         941192,  970299, 1000000]])
```
```python
np.shape(C)
```
```
(10, 10)
```
```python
div_by_4 = C[C % 4 == 0]
div_by_4
```
```
array([      8,      64,     216,     512,    1000,    1728,    2744,
          4096,    5832,    8000,   10648,   13824,   17576,   21952,
         27000,   32768,   39304,   46656,   54872,   64000,   74088,
         85184,   97336,  110592,  125000,  140608,  157464,  175616,
        195112,  216000,  238328,  262144,  287496,  314432,  343000,
        373248,  405224,  438976,  474552,  512000,  551368,  592704,
        636056,  681472,  729000,  778688,  830584,  884736,  941192,
       1000000])
```
```python
np.save("div_by_4.npy", div_by_4)
```
>  ##  **C.** Above-Mean Squares Problem
>Create a 6 × 6 ndarray named S containing the squares of the first 36 positive integers in increasing
row-major order. Compute the mean of all elements of S and store it in S mean. Then use Boolean
filtering to select only the elements strictly greater than S mean. Store these values in above mean.
><br><br>Required checks: Display S, S mean, above mean, and the number of selected elements. A correct
solution has 15 selected elements; the first is 484 and the last is 1296.<br>
Save the selected array as: above_mean.np
> ## Explanation
>> For this programming problem, we once again need to use the function ***np.arange()*** to create a 1-dimensional array, this time ranging from 1 to 36. We would indicate this by using ***(1,37)***, which in turn would give us the first 36 positive integers. We also need to transform this 1-dimensional array into a 6x6 ndarray. To  accomplish this, we need to use the function ***.reshape(6,6)***. Similarly to the last problem, we would need to square all the integers in the array. We can accomplish this by using the function "(np.arange(1, 37)**2)".
>> <br><br> Next thing we need to accomplish is to rename this array as **S** by using the function "S =(np.arange(1, 37)**2".
>> <br><br> Next, we need to get the mean of the entire array. To accomplish this, we can use the function ***S_mean =np.mean(S)***. Now that we have the mean of the entire array, we can now accomplish the other condition of the problem, which is to be able to extract and list down every single integer that is greater than the mean of the entire array. We can accomplish this by using **Boolean Filtering** with the function ***above_mean = S[S > S_mean]***. This also saves the array as **above_mean** for future use.
>> <br><br>This works because Boolean Filtering is essentially using true or false logic in the function by looking at every integer to determine if the condition of them being greater than the mean of the array is true or not.
>> <br><br> Lastly, similarly to the previous problems, we need to be able to save the selected array as **above_mean.np**, so we will use the function ***np.save()*** again as we did in the first problem.
>> <br><br> For checks, we can use ***np.size()*** to count the number of integers in the array, which should be 15 as required by the problem.
> ## Code & Outputs
```python
S = (np.arange(1, 37) ** 2).reshape(6, 6)
S
```
```
array([[   1,    4,    9,   16,   25,   36],
       [  49,   64,   81,  100,  121,  144],
       [ 169,  196,  225,  256,  289,  324],
       [ 361,  400,  441,  484,  529,  576],
       [ 625,  676,  729,  784,  841,  900],
       [ 961, 1024, 1089, 1156, 1225, 1296]])
```
```python
S_mean = np.mean(S)
S_mean
```
```
np.float64(450.1666666666667)
```
```python
above_mean = S[S > S_mean]
above_mean
```
```
array([ 484,  529,  576,  625,  676,  729,  784,  841,  900,  961, 1024,
       1089, 1156, 1225, 1296])
```
```python
np.size(above_mean)
```
```
15
```
```python
np.save("above_mean.npy", above_mean)
```
**README File Version History:**

```September 3, 2026``` - Initial README.md was uploaded

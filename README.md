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
```python
mean_X = X.mean()
mean_X 
```
```python
std_X = X.std()
std_X 
```
```python
X_normalized = (X - mean_X) / std_X
X_normalized
```
```python
np.mean(X_normalized)
```
```python
np.std(X_normalized)
```
```python
np.save("X_normalized.npy", X_normalized)
```

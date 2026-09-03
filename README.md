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

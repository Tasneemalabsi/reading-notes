# Pandas
*pandas is a software library written for the Python programming language for data manipulation and analysis. In particular, it offers data structures and operations for manipulating numerical tables and time series.*

you can import it to your program by typing:

`import pandas as pd`

### Object creation¶

*Creating a Series by passing a list of values, letting pandas create a default integer index.*

examples for code:

`s = pd.Series([1, 4, np.nan, 6, 8])`

**output**

0    1.0

1    4.0

2    NaN

3    6.0

4    8.0

dtype: float64

![data](https://www.w3resource.com/w3r_images/pandas-object-creation.svg)

`df = pd.DataFrame(np.random.randn(8, 4), index=dates, columns=list('PQRS'))`

**output**

![data2](https://www.w3resource.com/w3r_images/pandas-object-creation-1.svg)

### Viewing Data

DataFrame.to_numpy() gives a NumPy representation of the underlying data. Note that this can be an expensive operation when your DataFrame has columns with different data types, which comes down to a fundamental difference between pandas and NumPy: NumPy arrays have one dtype for the entire array, while pandas DataFrames have one dtype per column.

code examples:

`df.to_numpy()`

**output**


    array([[ 0.4691, -0.2829, -1.5091, -1.1356],

       [ 1.2121, -0.1732,  0.1192, -1.0442],
       [-0.8618, -2.1046, -0.4949,  1.0718],
       [ 0.7216, -0.7068, -1.0396,  0.2719],
       [-0.425 ,  0.567 ,  0.2762, -1.0874],
       [-0.6737,  0.1136, -1.4784,  0.525 ]])`

*Note that DataFrame.to_numpy() does not include the index or column labels in the output.*

### Selection by label¶

`df.loc[dates[0]]`

**Output**

A    0.469112

B   -0.282863

C   -1.509059

D   -1.135632

Name: 2013-01-01 00:00:00, dtype: float64

### Selection by position


Select via the position of the passed integers:

`df.iloc[3]`

**Output**

A    0.721555

B   -0.706771

C   -1.039575

D    0.271860

Name: 2013-01-04 00:00:00, dtype: float64

### Missing data¶

pandas primarily uses the value np.nan to represent missing data. It is by default not included in computations. 

## Operations

#### Stats

Operations in general exclude missing data.

#### Apply

Applying functions to the data:

`df.apply(np.cumsum)`

**output**

A         B         C   D     F

2013-01-01  0.000000  0.000000 -1.509059   5   NaN

2013-01-02  1.212112 -0.173215 -1.389850  10   1.0

2013-01-03  0.350263 -2.277784 -1.884779  15   3.0

2013-01-04  1.071818 -2.984555 -2.924354  20   6.0

2013-01-05  0.646846 -2.417535 -2.648122  25  10.0

2013-01-06 -0.026844 -2.303886 -4.126549  30  15.0

#### String methods

Series is equipped with a set of string processing methods in the str attribute that make it easy to operate on each element of the array, as in the code snippet below. Note that pattern-matching in str generally uses regular expressions by default (and in some cases always uses them). 

1. Concat
2. Join
3. Grouping, contains:
    - Splitting
    - Applying
    - Combining

### Reshaping

1. Stack, The stack() method “compresses” a level in the DataFrame’s columns.
2. Pivot tables, ex:

`pd.pivot_table(df, values="D", index=["A", "B"], columns=["C"])`

**Output**

C             bar       foo

A     B                    

one   A  2.395985 -1.202872

      B  1.395433 -1.814470
      C -0.392670 -0.055224
three A -0.595447       NaN

      B       NaN  1.928123
      C  0.166599       NaN
two   A       NaN  0.007207

      B  1.552825       NaN
      C       NaN  1.018601

## Advantages and Disadvantages of Pandas Library

### Advantages:

1. Data representation
2. Less writing and more work done
3. An extensive set of features
4. Efficiently handles large data
5. Makes data flexible and customizable
6. Made for Python

### Disadvantages:

1. Steep learning curve
2. Difficult syntax
3. Poor compatibility for 3D matrices
4. Bad documentation


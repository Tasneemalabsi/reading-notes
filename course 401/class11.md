# Data Analysis

## Jupyter Lab 
*JupyterLab is a web-based interactive development environment for Jupyter notebooks, code, and data. JupyterLab is flexible: configure and arrange the user interface to support a wide range of workflows in data science, scientific computing, and machine learning.*

### Jupyter Notebook

*The Jupyter Notebook is an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and narrative text.*

in Jupyterlab,  documents and activities integrate with each other, enabling new workflows for interactive computing, for example:

- Code Consoles provide transient scratchpads for running code interactively, with full support for rich output. 

- Kernel-backed documents enable code in any text file.

- Notebook cell outputs can be mirrored into their own tab, side by side with the notebook.

- Multiple views of documents with different editors or viewers enable live editing of documents reflected in other viewers. 

### JupyterLab Releases

- Since JupyterLab 0.32 (February 2018), the releases of JupyterLab are suitable for general daily use
- the 1.0 release , it is additionally ready for extension writers who wish to further customize the JupyterLab experience for others. 
- The extension developer API is evolving, and we also are currently iterating on UI/UX improvements. 

## NumPy

*NumPy, which stands for Numerical Python, is a library consisting of multidimensional array objects and a collection of routines for processing those arrays.*

**operations that could be done by Numpy:
- Mathematical and logical operations on arrays.
- Fourier transforms and routines for shape manipulation.
- Operations related to linear algebra. - NumPy has in-built functions for linear algebra and random number generation.

### Lists Of Lists for CSV Data using normal Python

`import csv`

`with open('winequality-red.csv', 'r') as f:`

    wines = list(csv.reader(f, delimiter=';'))

`print(wines[:3])`

csv.reader Return a reader object which will iterate over lines in the given csvfile. csvfile can be any object which supports the iterator protocol and returns a string each time its __next__() method is called 

Now,  We can find the average quality of the wines. The below code will:

- Extract the last element from each row after the header row.
- Convert each extracted element to a float.
- Assign all the extracted elements to the list qualities.
- Divide the sum of all the elements in qualities by the total number of elements in qualities to the get the mean.

`qualities =
[float(item[-1]) for item in wines[1:]]
sum(qualities) / len(qualities)`

by NumPy, we can:

- Import the NumPy package.
- Pass the list of lists wines into the array function, which converts it into a NumPy array.
- Exclude the header row with list slicing.
- Specify the keyword argument data type to make sure each element is converted to a float. 

`import csv`

`with open("winequality-red.csv", 'r') as f:`

    wines = list(csv.reader(f, 
    
    delimiter=";"))
`import numpy as np`

`wines = np.array(wines[1:], dtype=np.float)`

### Alternative NumPy Array Creation Methods

`import numpy as np`

`empty_array = np.zeros((3,4))`

`empty_array`

### Using NumPy To Read In Files

`wines = np.genfromtxt("winequality-red.csv", delimiter=";", skip_header=1)`

### NumPy Data Types

- each NumPy array can store elements of a single data type. 
- For example, wines contains only float values. 
- NumPy stores values using its own data types, which are distinct from Python types like float and str.

*You can find the data type of a NumPy array by accessing the dtype property:*

`wines.dtype`

**Important NumPy data-types:**

1. float — numeric floating point data.
2. int — integer data.
3. string — character data.
4. object — Python objects.

### NumPy Array Operations

- Single Array Math
- Multiple Array Math
- Broadcasting

### NumPy – Using Matplotlib

NumPy has a numpy.histogram() function that is a graphical representation of the frequency distribution of data. Rectangles of equal horizontal size corresponding to class interval called bin and variable height corresponding to frequency.

numpy.histogram()

The numpy.histogram() function takes the input array and bins as two parameters. The successive elements in bin array act as the boundary of each bin.



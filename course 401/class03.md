# Files And Exceptions

## Files

**what are files in general**
 
 - it's a system that consists of three parts: header, data, end of file
 - files in general have three properties in their names: path which represents where does the file exist, file name which is the actual name of it and the extension which indicates the file type .

 ### Files in Python

 *you can import files in python, you can also use it to read and write the contents of files. first of all, it has to be opened (this is an example of a text file): 

 `myfile = open("filename.txt")`

you can also close it by : 

`myfile.close()`

you can also open the file then close it when it finishes executing by using with statement, for example: 

`with open('dog_breeds.txt') as reader:`
    # Further file processing goes here

You can specify the mode used to open a file by applying a second argument to the open function.
Sending "r" means open in read mode, which is the default.
Sending "w" means write mode, for rewriting the contents of a file.
Sending "a" means append mode, for adding new content to the end of the file.

Adding "b" to a mode opens it in binary mode, which is used for non-text files (such as image and sound files).
For example:

1. write mode

`open("filename.txt", "w")`

2. read mode

`open("filename.txt", "r")`

`open("filename.txt")`

3. binary write mode

`open("filename.txt", "wb")`

### Reading and Writing Opened Files

methods used for that are :
- .read(size=-1): This reads from the file based on the number of size bytes. 
- .readline(size=-1): This reads at most size number of characters from the line. 
- .readlines(): This reads the remaining lines from the file object and returns them as a list.

## Python Exception

- *exceptions occur when something goes wrong, due to incorrect code or input. When an exception occurs, the program immediately stops.*
- **raising exception:** you can raise an exception if you want the program to execute an error for a certain condition, example:

`x = 10`

`if x > 5:`

    raise Exception('x should not exceed 5. The value of x was: {}'.format(x))

### exception handling

To handle exceptions, and to call code when an exception occurs, you can use a try/except statement.
The try block contains code that might throw an exception. If that exception occurs, the code in the try block stops being executed, and the code in the except block is run. If no error occurs, the code in the except block doesn't run. For example:

`try:`

    n1 =1
    n2 =0
    print(n1/n2)
`except:`
    print(1)

the code above will print 1 because the try block gives a division by zero error so it will executes what's inside the except block    

- try statement can have multiple except blocks
- An except statement without any exception specified will catch all errors

### The else Clause
using the else statement, you can instruct a program to execute a certain block of code only in the absence of exceptions. for example:

`try:`

    linux_interaction()
`except AssertionError as error:`

    print(error)
`else:`

    print('Executing the else clause.')


### Finally after exception

To ensure some code runs no matter what errors occur, you can use a finally statement. The finally statement is placed at the bottom of a try/except statement. Code within a finally statement always runs after execution of the code in the try. for example:

`try:`

    n1 =1
    n2 =0
    print(n1/n2)
`except:`

    print(1)

`finally:`

    print("this code will always be executed")

 



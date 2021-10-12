# Big O Notation
*Big O notation describes the performance or complexity of an algorithm. Big O specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used by an algorithm.*

**below are some common orders of growth along with descriptions and examples where possible:**

## O(1)

*O(1) describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.*

`bool IsFirstElementNull(IList<String> elements)`

`{`

    return elements[0] == null;

`}`

## O(N)

*O(N) describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set. The example below also demonstrates how Big O favours the worst-case performance scenario*

`bool ContainsValue(IEnumerable<string> elements, string value)`

`{`
    
    foreach (var element in elements)
    {
        if (element == value) return true; 
    }     
    return false; 
`}`

## O(N²)

*O(N²) represents an algorithm whose performance is directly proportional to the square of the size of the input data set. This is common with algorithms that involve nested iterations over the data set.*

`bool ContainsDuplicates(IList<string> elements)`

`{`
    
    for (var outer = 0; outer < elements.Count; outer++) 
    {
        for (var inner = 0; inner < elements.Count; inner++) 
        { 
            // Don't compare with self 
            if (outer == inner) continue;             
            
            if (elements[outer] == elements[inner]) return true; 
        }
    }    
    return false;
`}`

## O(2^N)

*O(2^N) denotes an algorithm whose growth doubles with each addition to the input data set. An example of an O(2^N) function is the recursive calculation of Fibonacci numbers:*

`int Fibonacci(int number)`

`{`

    if (number <= 1) return number;
       
    return Fibonacci(number - 2) + Fibonacci(number - 1); 
`}`

## Logarithms

- *Binary search is a technique used to search sorted data sets. It works by selecting the middle element of the data set, essentially the median, and compares it against a target value. If the values match, it will return success. If the target value is higher than the value of the probe element, it will take the upper half of the data set and perform the same operation against it.*

- *This type of algorithm is described as O(log N). The iterative halving of data sets described in the binary search example produces a growth curve that peaks at the beginning and slowly flattens out as the size of the data sets increase, for example:*

 **an input data set containing 10 items takes one second to complete, a data set containing 100 items takes two seconds, and a data set containing 1,000 items will take three seconds. Doubling the size of the input data set has little effect on its growth as after a single iteration of the algorithm the data set will be halved and therefore on a par with an input data set half the size. This makes algorithms like binary search extremely efficient when dealing with large data sets.**


 ## Pain vs. Suffering

*the article talks about the efforts that 401 students have to do in order to get the 
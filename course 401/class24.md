# Hash Tables

*Hashtables are a data structure that utilize key value pairs. This means every Node or Bucket has both a key, and a value.*

*The basic idea of a hashtable is the ability to store the key into this data structure, and quickly retrieve the value.*

*A hash is the ability to encode the key that will eventually map to a specific location in the data structure that we can look at directly to retrieve the value.*

## Hash tables contents/terminology:
1. Hash - A hash is the result of some algorithm taking an incoming string and converting it into a value that could be used for either security or some other purpose. In the case of a hashtable, it is used to determine the index of the array.
2. Buckets - A bucket is what is contained in each index of the array of the hashtable. Each index is a bucket. An index could potentially contain multiple key/value pairs if a collision occurs.
3. Collisions - A collision is what happens when more than one key gets hashed to the same location of the hashtable.

### Hash tables are useful for:

- Hold unique values
- Dictionary
- Library

## Structure

### Creating a Hash

1. Add or multiply all the ASCII values together.
2. Multiply it by a prime number such as 599.
3. Use modulo to get the remainder of the result, when divided by the total size of the array.
4. Insert into the array at that index.

**Example:**

```
Key = "Cat"
Value = "Josie"

67 + 97 + 116 = 280

280 * 599 = 69648

69648 % 1024 = 16

Key gets placed in index of 16. 
```

**Collisions**

*A collision occurs when more than one key hashes to the same index in an array. As mentioned earlier, a “perfect hash” will never have any collisions.*

*Collisions are solved by changing the initial state of the buckets. Instead of starting them all as null we can initialize a LinkedList in each one*

### Storing value in Hash maps

- accept a key
- calculate the hash of the key
- use modulus to convert the hash into an array index
- store the key with the value by appending both to the end of a linked list.

### Bucket sizes

Hash Maps can have any number of buckets. If a hash map has only a few buckets it will be densely full and have many collisions.

It’s possible to compute the “load factor” of a hash table. The load factor tells us something about how full the hash table is.

## Internal Methods

**Add()**

- send the key to the GetHash method.
- Once you determine the index of where it should be placed, go to that index
- Check if something exists at that index already, if it doesn’t, add it with the key/value pair.
- If something does exist, add the new key/value pair to the data structure within that bucket.

**Find()**

The Find takes in a key, gets the Hash, and goes to the index location specified. Once at the index location is found in the array, it is then the responsibility of the algorithm the iterate through the bucket and see if the key exists and return the value.

**contains()**

The Contains method will accept a key, and return a bool on if that key exists inside the hashtable. 

**GetHash()**

The GetHash will accept a key as a string, conduct the hash, and then return the index of the array where the key/value should be placed.


**To achieve a good hashing mechanism, It is important to have a good hash function with the following basic requirements:**

1. Easy to compute: It should be easy to compute and must not become an algorithm in itself.

2. Uniform distribution: It should provide a uniform distribution across the hash table and should not result in clustering.

3. Less collisions: Collisions occur when pairs of elements are mapped to the same hash value. These should be avoided.


## Implementation

```
class HashTable:
	def __init__(self):
		self.capacity = INITIAL_CAPACITY
		self.size = 0
		self.buckets = [None] * self.capacity
```

**Node class**

```
class Node:
    def __init__(self, key, value):
        self.key = key
        self.value = value
        self.next = None
```

**Find method**

```
def find(self, key):
	index = self.hash(key)
	node = self.buckets[index]
	while node is not None and node.key != key:
		node = node.next
	if node is None:
        return None
	else:
		return node.value
```        








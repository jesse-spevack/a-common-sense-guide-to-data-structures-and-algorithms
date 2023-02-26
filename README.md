# A Common-Sense Guide to Data Structures and Algorithms, Second Eddition
Work and notes related to A Common-Sense Guide to Data Structures and Algorithms, Second Edition
## Chapter 1: Why Data Structures Matter
### Exercises
### For an array containing 100 elements, provide the number of steps the following operations would take:
#### Reading: 
Reading from an array is an efficient operation, since the computer can read any index by jumping to any memory address in one step.
#### Searching for a value not contained within the array: 
For N cells in an array, linear search takes a maximum of N steps. For an array of 100 elements, the maximum number of steps linear search would take is 100.
#### Insertion at the beginning of the array:
Inserting data at the beginning of an array is the worst-case scenario for insertion into an array. It can take N + 1 steps for an array containing N elements. In this case it will 100 + 1, 101 steps. This is because we need to shift all N elements over (100 steps) and then finally execute the actual insertion step (1 step).
#### Insertion at the end of the array:
Once the computer calculates which memory address to insert the new value into, it can do so in one step.
#### Deletion at the beginning of the array
The worst-case scenario of deleting an element is deleting the very first element of the array. 
#### Deletion at the end of the array


1. For an array-based set containing 100 elements, provide the number of
steps the following operations would take:
  - Reading
  - Searching for a value not contained within the array
  - Insertion of a new value at the beginning of the set
  - Insertion of a new value at the end of the set
  - Deletion at the beginning of the set
  - Deletion at the end of the set

1. Normally the search operation in an array looks for the first instance of
a given value. But sometimes we may want to look for every instance of
a given value. For example, say we want to count how many times the
value “apple” is found inside an array. How many steps would it take to
find all the “apples”? Give your answer in terms of N.

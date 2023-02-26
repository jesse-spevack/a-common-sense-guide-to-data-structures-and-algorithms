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
Since there is no shifting required when we delete from the end of an array, deletion at the end of the array takes one step.


### For an array-based set containing 100 elements, provide the number of
steps the following operations would take:
#### Reading
Reading from a set is exactly the same as reading from an array - it takes just one step for the computer to look up what's contained within a particular index.

#### Searching for a value not contained within the array
Searching a set also is no different than searching an array - it takes up to N steps to search for a value within a set.

#### Insertion of a new value at the beginning of the set
Insertion is where arrays and sets diverge. With a set the computer first needs to determine that this value doesn't already exist in this set. Therefore, the computer will first need to search the set to see whether the value we want to insert is already there. Only if the set does not yet contain our new value will the computer allow the insertion to take place.

Insertion of a new value at the beginning fo the set is the worst case scenario. The computer needs to search N (100) cells to ensure that the set doesn't already contain that value, another N (100) steps to shift all the data to the right, and another final step to insert the new value. That's a total of 2N + 1 or 201 steps.

#### Insertion of a new value at the end of the set
Insertion into the end of a set will take up to N + 1 steps for N elements. This is because there are N steps of search to ensure that the value doesn't already exist in the set, and then one step for the actual insertion.

#### Deletion at the beginning of the set
Deletion is also identical between a set and an array - it takes up to N steps to delete a value and move data to the left to close the gap. In this case 101 steps.
#### Deletion at the end of the set
Since there is no shifting required when we delete from the end of an array, deletion at the end of the array takes one step.
### How many steps would it take to find all the “apples”?
*Normally the search operation in an array looks for the first instance ofa given value. But sometimes we may want to look for every instance of a given value. For example, say we want to count how many times the value “apple” is found inside an array. How many steps would it take to find all the “apples”? Give your answer in terms of N.*
To count how many times the value "apple" is found inside an array, we would need to search the entire array. This would take N steps where N is the number of elements in the array.

```ruby
def count_apples(array)
  count = 0
  array.each do |element|
    count += 1 if element == 'apples'
  end
  return count
end

array = ['apples', 'not apples', 'apples', 'not apples', 'apples']
count_apples(array)
=> 3
```
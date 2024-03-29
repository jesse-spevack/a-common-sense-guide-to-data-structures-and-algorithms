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

## Chapter 2: Why Algorithms Matter
### Exercises
1. How many steps would it take to perform a linear search for the number 8 in the ordered array, `[2, 4, 6, 8, 10, 12, 13]`?

    It would take 4 steps. Linear search must inspect each element in the array until it stopping at the number 8.

2. How many steps would binary search take for the previous example?

    It would take 1 step. The first step in a binary search would be to inspect the middle element, `8`, which is the value we are searching for.

3. What is the maximum number of steps it would take to perform a binary search on an array of size 100,000?

   It would take 17 steps to search an array of size 100,000.

   | Array Length  | Binary Search Steps  |
   |---|---|
   | 100 | 7 |
   | 200 | 8 |
   | 400 | 9 |
   | 800 | 10 |
   | 1600 | 11 |
   | 3200 | 12 |
   | 6400 | 13 |
   | 12800 | 14 |
   | 25600 | 15 |
   | 51200 | 16 |
   | 102400 | 17 |

## Chapter 3: O Yes! Big O Notation
### Exercises
1. Use Big O Notation to describe the time complexity of the following function that determines whether a given year is a leap year:
   ```javascript
   function isLeapYear(year) {
     return (year % 100 === 0) ? (year % 400 === 0) : (year % 4 === 0);
   }
   ```

   This complexity of this function is O - it runs in contsant time.
2. Use Big O Notation to describe the time complexity of the following function that sums up all the numbers from a given array:

   ```javascript
   function arraySum(array) {
     let sum = 0;
     for(let i = 0; i < array.length; i++) {
       sum += array[i];
     }

     return sum; 
   }
   ```
   The complexity of this function is O(N), Oh of N - it will take N steps. However long the `array` is (N), that's how many steps this algorithm will take to complete

3. The following function is based on the age-old analogy used to describe the power of compounding interest:

    Imagine you have a chessboard and put a single grain of rice on one square. On the second square, you put two grains of rice, since that is double the amount of rice on the previous square. On the third square you put 4 grains, on the fourth square, you put 8 grains, and on the fifth square, you put 16 grains, and so on.

    The following function calculates which square you'll need to place a certain number of rice grains. For example, for 16 grains, the function will return 5, since you will place the 16 grains on the fifth square.

    Use Big O Notation to describe the time complexity of this function, which is below:

    ```javascript
    function chessboardSpace(numberOfGrains) {
      let chessboardSpaces = 1;
      let placedGrains = 1;
      while (placedGrains < numberOfGrains) {
        placedGrains *= 2;
        chessboardSpaces += 1;
      }
      return chessboardSpaces;
     }
     ```

    The complexity of this function is O Log N, everytime we double the `numberOfGrains` we increase the number of steps required by 1.

4. The following function accepts an array of strings and returns a new array that only contains the strings that start with the character "a". Use Big O Notation to describe the time complexity of the function:
    ```javascript
    function selectAStrings(array) { 
      let newArray = [];
      for(let i = 0; i < array.length; i++) { 
        if (array[i].startsWith("a")) {
          newArray.push(array[i]);
        }
      }
      return newArray; 
    }
    ```

    The complexity of this function is O of N. Everytime we increase the length of the array, we increase the number of steps needed to complete the function.

5. The following function calculates the median from an ordered array. Describe its time complexity in terms of Big O Notation:

   ```javascript
   function median(array) {
     const middle = Math.floor(array.length / 2);
     // If array has even amount of numbers:
     if (array.length % 2 === 0) {
       return (array[middle - 1] + array[middle]) / 2;
     } else { 
       // If array has odd amount of numbers:
       return array[middle];
     } 
   }
   ```

   The time complexity of this function is O, constant time. Reading from an array happens in constant time. No matter how long the array is, this function takes the same number of steps.
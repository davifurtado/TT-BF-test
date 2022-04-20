# Java Script
## 1 - Non-Constructible Change

  Given an array of positive integers representing the values of coins in your possession, write a function that returns the minimum amount of change (the  minimum sum of money) that you  CANNOT create. The given coins can have
  any positive integer value and aren't necessarily unique (i.e., you can have multiple coins of the same value).
  
### Sample Input
```
  coins = [5, 7, 1, 1, 2, 3, 22]
```
  
### Sample Output
```
 20
```

#### Test Case 1
```
{
  "coins": [5, 7, 1, 1, 2, 3, 22]
}
```
##### Output
```
20
```
#### Test Case 2
```
{
  "coins": [1, 1, 1, 1, 1]
}
```
##### Output
```
6
```
#### Test Case 3
```
{
   "coins": [1, 5, 1, 1, 1, 10, 15, 20, 100]
}
```
##### Output
```
55
```

------------------------------------------------------------------------------------------------------------------------------------------------
SOLUTION

const coins = [5, 7, 1, 1, 2, 3, 22]
//const coins = [1, 1, 1, 1, 1]
const a = (changes) => {
    if (!changes) return false
	let change = null
    
	if (Array.isArray(changes)) {
    	change = changes
    } else if (typeof changes === object && Array.isArray(changes["coin"])) {
    	change = changes["coin"]
    } else {
    	return false
    }
		
   // if no coins return 1
    changes.sort((a,b) => a - b);
    let currentValue = 0;
    for (let coin of coins) {
        if (coin > currentValue + 1) return currentValue + 1
        currentValue += coin;
    }
    return currentValue + 1;
}

console.log(a(coins))


------------------------------------------------------------------------------------------------------------------------------------------------

## 2 - Sorted Squared Array
  Write a function that takes in a non-empty array of integers that are sorted  in ascending order and returns a new array of the same length with the squares  of the original integers also sorted in ascending order.
  
### Sample Input
```
  array = [1, 2, 3, 5, 6, 8, 9]
```
  
### Sample Output
```
    [1, 4, 9, 25, 36, 64, 81]
```

#### Test Case 1
```
{
  "array": [1, 2, 3, 5, 6, 8, 9]
}
```
##### Output
```
    [1, 4, 9, 25, 36, 64, 81]
```
#### Test Case 2
```
{
    "array": [-2, -1]
}
```
##### Output
```
    [1, 4]
```
#### Test Case 3
```
  "array": [-10, -5, 0, 5, 10]
```
##### Output
```
    [0, 25, 25, 100, 100]
```

------------------------------------------------------------------------------------------------------------------------------------------------

SOLUTION

const originalArray = [1, 2, 3, 5, 6, 8, 9]

// since it's already sorted, no need to sort
const squaredSortedArray = (array) => { 
    // if to check if it's an array and if it has a length
    if (!Array.isArray(array) || !array.length) return false

    return array.map(o => o * o)
}

console.log(squaredSortedArray(originalArray))


------------------------------------------------------------------------------------------------------------------------------------------------

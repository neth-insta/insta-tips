# Useful JavaScript One-Liners

## ``` 1) Find the max value in an array: ```
```javascript
Math.max(...array)
```

## ``` 2) Remove duplicates from an array: ```
```javascript
[...new Set(array)]
```

## ``` 3) Generate a random number between 1 and 100: ```
```javascript
Math.floor(Math.random() * 100) + 1
```

## ``` 4) Check if a string is a valid number: ```
```javascript
!isNaN(parseFloat(string))
```

## ``` 5) Get the current date and time: ```
```javascript
new Date().toString()
```

## ``` 6) Check if a variable is an array: ```
```javascript
Array.isArray(variable)
```

## ``` 7) Check if a variable is an object: ```
```javascript
typeof variable === "object"
```

## ``` 8) Convert an array to a string: ```
```javascript
array.join(",")
```

## ``` 9) Check if a variable is a function: ```
```javascript
typeof variable === "function"
```


## ``` 10) Convert an object to an array: ```
```javascript
Object.values(object)
```

## ``` 11) Count the occurrences of an element in an array: ```
```javascript
array.filter(x => x === element).length
```

## ``` 12) Create a new object with a dynamic key and value: ```
```javascript
{ [key]: value }
```

## ``` 13) Check if a string is a palindrome: ```
```javascript
string === string.split("").reverse().join("")
```

## ``` 14) Get the the sum of all the numbers in an array: ```
```javascript
array.reduce((a, b) => a + b, 0);
```

## ``` 15) Get the current timestamp: ```
```javascript
Date.now()
```

## ``` 16) Check if a variable is null: ```
```javascript
variable === null
```

## ``` 17) Check if a variable is undefined: ```
```javascript
typeof variable === "undefined"
```

## ``` 18) Find the minimum value in an array: ```
```javascript
Math.min(...array)
```

## ``` 19) Check if an array is empty: ```
```javascript
array.length === 0
```

## ``` 20) Create a new array with a specified range of numbers: ```
```javascript
Array.from({ length: n }, (_, i) => i)
```
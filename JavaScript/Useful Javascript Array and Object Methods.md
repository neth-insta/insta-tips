# Useful Javascript Array and Object Methods

## ``` .filter() ```
```javascript
const studentsAge = [17, 16, 18, 19, 21, 17];
const ableToDrink = studentsAge.filter( age => age > 18 );
// ableToDrink will be equal to [19, 21]
```

## ``` .map() ```
```javascript
const numbers = [2, 3, 4, 5];
const dollars = numbers.map( number => '$' + number);
// dollars will be equal to ['$2', '$3', '$4', '$5']
```

## ``` .reduce() ```
```javascript
const numbers = [5, 10, 15];
const total = numbers.reduce( (accumulator, currentValue) => accumulator + currentValue);
// total will be equal to 30
```

## ``` .forEach() ```
```javascript
const emotions = ['happy', 'sad', 'angry'];
emotions.forEach( emotion => console.log(emotion) );
// Will log the following:
// 'happy'
// 'sad'
// 'angry'
```


## ``` .some() ```
```javascript
const userPrivileges = ['user', 'user', 'user', 'admin'];
const containsAdmin = userPrivileges.some( element => element === 'admin');
// containsAdmin will be equal to true
```

## ``` .every() ```
```javascript
const ratings = [3, 5, 4, 3, 5];
const goodOverallRating = ratings.every( rating => rating >= 3 );
// goodOverallRating will be equal to true
```

## ``` .includes() ```
```javascript
const names = ['sophie', 'george', 'waldo', 'stephen', 'henry'];
const includesWaldo = names.includes('waldo');
// includesWaldo will be equal to true
```

## ``` Array.from() ```
```javascript
const newArray = Array.from('hello');
// newArray will be equal to ['h', 'e', 'l', 'l', 'o']

const doubledValues = Array.from([2, 4, 6], number => number * 2);
// doubleValues will be equal to [4, 8, 12]
```

## ``` Object.values() ```
```javascript
const icecreamColors = {
    chocolate: 'brown',
    vanilla: 'white',
    strawberry: 'red',
}

const colors = Object.values(icecreamColors);
// colors will be equal to ["brown", "white", "red"]
```

## ``` Object.keys() ```
```javascript
const icecreamColors = {
  chocolate: 'brown',
  vanilla: 'white',
  strawberry: 'red',
}

const types = Object.keys(icecreamColors);
// types will be equal to ["chocolate", "vanilla", "strawberry"]
```

## ``` Object.entries() ```
```javascript
const weather = {
  rain: 0,
  temperature: 24,
  humidity: 33,
}

const entries = Object.entries(weather);
// entries will be equal to
// [['rain', 0], ['temperature', 24], ['humidity', 33]]
```

## ``` Array spread ```
```javascript
const spreadableOne = [1, 2, 3, 4];
const spreadableTwo = [5, 6, 7, 8];

const combined = [...spreadableOne, ...spreadableTwo];
// combined will be equal to [1, 2, 3, 4, 5, 6, 7, 8]

const animals = ['squirrel', 'bear', 'deer', 'salmon', 'rat'];
const mammals = [...animals.slice(0,3), ...animals.slice(4)];
// mammals will be equal to ['squirrel', 'bear', 'deer', 'rat']
```

## ``` Object spread ```
```javascript
const spreadableObject = {
  name: 'Robert',
  phone: 'iPhone'
};

const newObject = {
  ...spreadableObject,
  carModel: 'Volkswagen'
}
// newObject will be equal to
// { carModel: 'Volkswagen', name: 'Robert', phone: 'iPhone' }
```

## ``` Function Rest ```
```javascript
function displayArgumentsArray(...theArguments) {
  console.log(theArguments);
}

displayArgumentsArray('hi', 'there', 'bud');
// Will print ['hi', 'there', 'bud']
```

## ``` Object.freeze() ```
```javascript
const frozenObject = {
  name: 'Robert'
}

Object.freeze(frozenObject);

frozenObject.name = 'Henry';
// frozenObject will be equal to { name: 'Robert' }
```

## ``` Object.seal() ```
```javascript
const sealedObject = {
  name: 'Robert'
}

Object.seal(sealedObject);

sealedObject.name = 'Bob';
sealedObject.wearsWatch = true;
// sealedObject will be equal to { name: 'Bob' }
```

## ``` Object.assign() ```
```javascript
const firstObject = {
  firstName: 'Robert'
}

const secondObject = {
  lastName: 'Cooper'
}

const combinedObject = Object.assign(firstObject, secondObject);
// combinedObject will be equal to { firstName: 'Robert', lastName: 'Cooper' }
```

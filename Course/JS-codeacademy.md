# Краткая выжимка курса JavaScript с codeacademy. 

Пропущены уроки с 1 по 5

## Циклы

### for 

Цикл *for* принимает три выражения, разделенные ';', в круглых скобках. 

```javascipt
for (initialization, stopping condition, iteration statement) { }
```

* initialization - начинает цикл и также может быть использован для объявления переменной-итератора
* stopping condition - выражение; если выполняется - код в цикле эвалуейтится
* iteration statement - используется для обновления итератора каждый проход цикла

*Пример*: 
```javascript
for (let counter = 0; counter < 4; counter++) {
	console.log(counter)
}
```

### reverse for 

Если хотим вывод в обратную сторону:
```javascript
for (let counter = highest; counter >= minimum; counter--) {}
```

### Looping throug array 

```javascript 
const animals = ['Bear', 'Cat', 'Dog'];

for (let i = 0; i < animals.lenght; i++) {
	console.log(animals[i])
}
```

### while loop 

```javascript
while (condition) {
	dosomething
}
```

### do ... while 

Такая конструкция говорит о том, что нужно сделать таск и продолжать делать его до тех пор, пока указанное условие не перестанет выполняться.


```javascript
let countString = '';
let i = 0; 

do {
	countString = countString + i; 
	i++;
} while (i < 5); 

console.log(countString);
```

### Метод forEach()

Исполняет один и тот жже код касательно всех элементов в итерируемой последовательности. 

```javascript
const groceries = ['brown sugsr', 'salt', 'cranberries', 'walnuts'];

groceries.forEach(function(groceryItem) {
console.log(' - ' + groceryItem); })
```

или 

```javascript
groceries.forEach(groceryItem => console.log(groceryItem));
```

Мы можешь определить функцию, которая будет использоваться в качестве коллбэка

```javascript
function printGrocery(element) {
console.log(element);
}

groceries.forEach(printGrocery);
```

### Метод .map()
Когда метод вызывается на массив, он принимает аргументом функцию и возвращает новый массив. 

```javascript
const number = [1,2,3,4,5];
const bigNumber = numbers.map(number => {return number * 10;});
```

### Метод .filter()

Как и map, возвращает новый список, отфильтрованный. 

```javascript
const words = ['chair', 'music', 'pillow', 'brick', 'pen', 'door'];

const shortWords = words.filter(word => {
return word.length < 6;
});
```

### Метод .findIndex()
```javascript
const Nums = [123, 25,78, 5,9];

const lessThenTen - Nums.findIndex(num => {return num <10});
```

### Метод .reduce()

Возвращает единственное значение после итерирования элементов списка.

```javascript
const numbers = [1, 2, 4, 10];

const summedNums = numbers.reduce((accumulator, currentValue) => { return accumulator + currentValue})

console.log(summedNums) //output: 17
```

## Объекты 

В JS 7 фундаментальных типов данных: 
* string
* number
* boolean
* null
* undefined
* symbol
* objects

Для объявления объекта: 

```javascript
let spaceship = {};
```

Мы наполняем объект неупорядоченными данными. Эти данные - набор пар ключ-значение. 

```javascript
let spaceship = {
    'Fuel Type': diesel,
    'Color': 'silver'
};
```

Классически, атрибуты можно достать через точку.

Еще один способ - через скообки. 

```javascript
spaceship['Color']
```

### Методы объектов

Как создать: 

```javascript
const alienShip = {
   invade: function () {
      console.log('Hello! .... ') }};
```

ES6 версия 

```javascript 
const alienShip = {
   invade () {
      console.log('Hello....')}};
```

### Вложенные объекты 

Объект может иметь другой объект в качестве свойства.


### Looping Through Objects

**for ... in** исполняет данный блок кода для каждого свойства объекта

```javascript
for (let crewMember in spaceship.crew) {
   console.log(`%{crewMember}: ${spaceship.crew[crewMember].name`);
}
```

## Advancrd objects

### Ключевое слово this

this - это как self в Python. 

```javascript
const goat = {
  dietType: 'herbivore',
  makeSound() {
    console.log('baaa');
  },
  diet() {
    console.log(this.dietType);
  }
};

goat.diet(); 
```

Не подойдет в использовании с Arrow Function

### Приватность 

С _ все то же самое, что и в python

### Getters 

Геттер - это метод который получает и возврашает внутренний атрибут объекта.


```javascript
const person = {
  _firstName: 'John',
  _lastName: 'Doe',
  get fullName() {
    if (this._firstName && this._lastName){
      return `${this._firstName} ${this._lastName}`;
    } else {
      return 'Missing a first name or a last name.';
    }
  }
}
 
// To call the getter method: 
person.fullName; // 'John Doe'
```

* Getters can perform an action on the data when getting a property.
* Getters can return different values using conditionals.
* In a getter, we can access the properties of the calling object using this. 

### Setters

Переназначает существующее свойство объекта

```javascript
const person = {
  _age: 37,
  set age(newAge){
    if (typeof newAge === 'number'){
      this._age = newAge;
    } else {
      console.log('You must assign a number to age');
    }
  }
};
```

```javascript
person.age = 40;
console.log(person._age); // Logs: 40
person.age = '40'; // Logs: You must assign a number to age
```

### Factory Functions

Когда мы хотим создать множество похожих объектов 

```javascript
const monsterFactory = (name, age, energySource, catchPhrase) => {
  return { 
    name: name,
    age: age, 
    energySource: energySource,
    scare() {
      console.log(catchPhrase);
    } 
  }
};
```

```javascript
const ghost = monsterFactory('Ghouly', 251, 'ectoplasm', 'BOO!');
ghost.scare(); // 'BOO!'
```

### Property Value Shorthand

ES6 привнесло новый стандарт в создание пар ключей и значений  (destructuring)
Если много параметров, проще сделать так

```javascript
const monsterFactory = (name, age) => {
  return { 
    name,
    age 
  }
};
```

### destructured assignment

```javascript 
const vampire = {
  name: 'Dracula',
  residence: 'Transylvania',
  preferences: {
    day: 'stay inside',
    night: 'satisfy appetite'
  }
};
```


```javascript
const residence = vampire.residence; 
console.log(residence); // Prints 'Transylvania' 
```
=

```javascript 
const { residence } = vampire; 
console.log(residence); // Prints 'Transylvania'
```

## Классы 

```javascript
class Dog {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }

  get name() {
    return this._name;
  }
  get behavior() {
    return this._behavior;
  }   

  incrementBehavior() {
    this._behavior ++;
  }
}
```

```javascript
const halley = new Dog('Halley'); // Create new Dog instance
console.log(halley.name); // Log the name value saved to halley
// Output: 'Halley'
```

### Наследование 

```javascript
class Animal {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }
 
  get name() {
    return this._name;
  }
 
  get behavior() {
    return this._behavior;
  }   
 
  incrementBehavior() {
    this._behavior++;
  }
} 
```

```javascript
class Cat extends Animal {
  constructor(name, usesLitter) {
    super(name);
    this._usesLitter = usesLitter;
  }
}
```

### Static Methods

Иногда нужно, чтобы отдельные методы не были доступны отдельным объектам класса, но могли быть вызваны именно через класс.

```javascript
class Animal {
  constructor(name) {
    this._name = name;
    this._behavior = 0;
  }
 
  static generateName() {
    const names = ['Angel', 'Spike', 'Buffy', 'Willow', 'Tara'];
    const randomNumber = Math.floor(Math.random()*5);
    return names[randomNumber];
  }
} 
```

```javascript
console.log(Animal.generateName()); // returns a name
```

```javascript
const tyson = new Animal('Tyson'); 
tyson.generateName(); // TypeError
```

## Совместимость браузеров и транспайлеры

Babel - библиотека для транспиляции (перевода) JS ES6 к JS ES5.

```bash
npm install babel-cli

npm install babel-preset-env

npm run build
```

## Модули 

### module.exports
 
 Это для ноды 

 ```javascript
 let Menu = {};
Menu.specialty = "Roasted Beet Burger with Mint Sauce";
 
module.exports = Menu; 
```

### require()

Это импорт 

```javascript 
const Menu = require('./menu.js');
 
function placeOrder() {
  console.log('My order is: ' + Menu.specialty);
}
 
placeOrder();
```


We can also wrap any collection of data and functions in an object, and export the object using module.exports. In menu.js, we could write:

```javascript
module.exports = {
  specialty: "Roasted Beet Burger with Mint Sauce",
  getSpecialty: function() {
    return this.specialty;
  } 
}; 
```

### export default

Это не про ноду, про ES6 

```javascript
let Menu = {};
 
export default Menu;
```

### import 

```javascript 
import Menu from './menu';
```


### Named Exports

```javascript
let specialty = '';
function isVegetarian() {
}; 
function isLowSodium() {
}; 
 
export { specialty, isVegetarian };
```

* Мы не устанавливаем свойства объекту

### Named Imports

```javascript
import { specialty, isVegetarian } from './menu';
 
console.log(specialty);
```


### Export Named Exports

Также можно указать ключевое слово export отдельно 

```javascript 

export let specialty = '';
export function isVegetarian() {
}; 
function isLowSodium() {
};
```
### Export as


```javascript 
let specialty = '';
let isVegetarian = function() {
}; 
let isLowSodium = function() {
}; 
 
export { specialty as chefsSpecial, isVegetarian as isVeg, isLowSodium };
```

```javascript 
import { chefsSpecial, isVeg } from './menu';
```

**Можно использовать оба варианта импорта и экспорта одновременно**. 

```javascript 
export let Menu = {};
 
export let specialty = '';
export let isVegetarian = function() {
}; 
export let isLowSodium = function() {
}; 
let isGlutenFree = function() {
};
 
export default isGlutenFree;


...

import { specialty, isVegetarian, isLowSodium } from './menu';
 
import GlutenFree from './menu';
```




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
 

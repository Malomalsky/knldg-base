# Краткая вижимка курса JavaScript с codeacademy. 

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

### Функции высшего порядка. 

В JS функции - объекты высшего порядка. 

Даже писать нечего, все и так ясно. 


### Итераторы 



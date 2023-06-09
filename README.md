# lect-array
# lecture-array

# Что такое array n JS
> Массив (array) в JavaScript - это структура данных, которая представляет собой упорядоченный набор элементов одного или разных типов данных, хранящихся под одним именем. Элементы массива могут быть доступны по индексу, который начинается с 0. В JavaScript массивы динамические, то есть их размер может изменяться в процессе выполнения программы. Для создания массива в JavaScript используется литерал массива, который представляет собой набор элементов, разделенных запятыми и заключенных в квадратные скобки. Например:

```javascript
let myArray = [1, 2, "three", true];
```

> В этом примере создается массив `myArray`, который содержит четыре элемента: число 1, число 2, строку "three" и логическое значение true. Каждый элемент массива имеет свой индекс: 0, 1, 2 и 3 соответственно. Чтобы получить доступ к элементу массива, можно использовать его индекс, например:

```javascript
console.log(myArray[2]); // "three"
```
# Change elements в массиве
> Чтобы изменить элемент массива в JavaScript, нужно обратиться к нему по индексу и присвоить ему новое значение. Например, чтобы изменить второй элемент массива `myArray` на число 3, можно сделать следующее:

```javascript
myArray[1] = 3;
```

> Теперь элемент массива с индексом 1 (второй элемент) будет равен 3. Если вывести массив в консоль, то увидим следующий результат:

```javascript
console.log(myArray); // [1, 3, "three", true]
```

> Также можно изменять несколько элементов массива с помощью метода `splice()`. Например, чтобы заменить первые два элемента массива на другие значения, можно использовать следующий код:

```javascript
myArray.splice(0, 2, "new", "values");
```

> Этот код удалит первые два элемента массива (`myArray.splice(0, 2)`) и заменит их на новые значения ("new" и "values"). Теперь массив `myArray` будет содержать следующие элементы:

```javascript
console.log(myArray); // ["new", "values", "three", true]
```

# Array methods
![](./Screenshot_1.png)
## В JavaScript есть множество методов для работы с массивами. Некоторые из них:

### 1. push() - добавляет один или несколько элементов в конец массива и возвращает новую длину массива.
```javascript
let arr = [1, 2, 3];
arr.push(4, 5);
console.log(arr); // [1, 2, 3, 4, 5]
```

### 2. pop() - удаляет последний элемент из массива и возвращает его значение.
```javascript
let arr = [1, 2, 3];
let lastElement = arr.pop();
console.log(lastElement); // 3
console.log(arr); // [1, 2]
```

### 3. shift() - удаляет первый элемент из массива и возвращает его значение.
```javascript
let arr = [1, 2, 3];
let firstElement = arr.shift();
console.log(firstElement); // 1
console.log(arr); // [2, 3]
```

### 4. unshift() - добавляет один или несколько элементов в начало массива и возвращает новую длину массива.
```javascript
let arr = [1, 2, 3];
arr.unshift(0, -1);
console.log(arr); // [-1, 0, 1, 2, 3]
```

### 5. slice() - возвращает новый массив, содержащий копию части исходного массива.
```javascript
let arr = [1, 2, 3, 4, 5];
let slicedArr = arr.slice(1, 4);
console.log(slicedArr); // [2, 3, 4]
```

### 6. splice() - изменяет исходный массив, удаляя или заменяя элементы и возвращая массив удаленных элементов.
```javascript
let arr = [1, 2, 3, 4, 5];
let removedElements = arr.splice(1, 2, 'a', 'b');
console.log(removedElements); // [2, 3]
console.log(arr); // [1, 'a', 'b', 4, 5]
```

### 7. concat() - объединяет два или более массивов и возвращает новый массив.
```javascript
let arr1 = [1, 2, 3];
let arr2 = [4, 5];
let newArr = arr1.concat(arr2);
console.log(newArr); // [1, 2, 3, 4, 5]
```

### 8. join() - объединяет все элементы массива в строку, разделенную указанным разделителем.
```javascript
let arr = [1, 2, 3];
let str = arr.join('-');
console.log(str); // '1-2-3'
```

### 9. reverse() - изменяет порядок элементов в массиве на обратный.
```javascript
let arr = [1, 2, 3];
arr.reverse();
console.log(arr); // [3, 2, 1]
```

### 10. sort() - сортирует элементы массива в порядке возрастания (если не указана функция сравнения).
```javascript
let arr = [3, 1, 4, 2, 5];
arr.sort();
console.log(arr); // [1, 2, 3, 4, 5]
```
### 11. map() в JavaScript создает новый массив, применяя функцию обратного вызова к каждому элементу исходного массива. Он не изменяет исходный массив, а возвращает новый массив с результатами выполнения функции обратного вызова для каждого элемента исходного массива.

> Синтаксис метода `map()` выглядит следующим образом:

```js
arr.map(callback(currentValue[, index[, array]])[, thisArg])
```

> где:

- `callback` - функция, которая будет вызвана для каждого элемента массива. Она принимает три аргумента:
  - `currentValue` - текущий обрабатываемый элемент массива;
  - `index` (необязательный) - индекс текущего элемента массива;
  - `array` (необязательный) - исходный массив, который обрабатывается;
- `thisArg` (необязательный) - значение, которое будет использоваться в качестве `this` при вызове функции обратного вызова.

> Метод `map()` возвращает новый массив, который состоит из результатов выполнения функции обратного вызова для каждого элемента исходного массива.

### 12 Метод `filter()` в JavaScript создает новый массив, содержащий все элементы исходного массива, для которых функция обратного вызова возвращает `true`. То есть, он фильтрует элементы массива на основе заданного условия. Например, можно использовать `filter()` для получения массива только с четными числами или только с элементами, удовлетворяющими определенному условию.
> Например, у нас есть массив чисел `[1, 2, 3, 4, 5, 6]`, и мы хотим создать новый массив, содержащий только четные числа. Мы можем использовать метод `filter()` для этого:

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // [2, 4, 6]
```

> В этом примере мы создали новый массив `evenNumbers`, который содержит только четные числа из исходного массива `numbers`. Мы передали функцию обратного вызова в метод `filter()`, которая проверяет, является ли число четным, и возвращает `true` или `false`. Если функция возвращает `true`, элемент добавляется в новый массив, если `false` - элемент не добавляется.

### 13.  Метод `find()` используется для поиска первого элемента в массиве, который удовлетворяет заданному условию. Если такой элемент найден, метод возвращает его значение, иначе возвращает `undefined`.

> Синтаксис: `array.find(callback(element[, index[, array]])[, thisArg])`

- `callback` - функция, которая будет вызвана для каждого элемента массива. Она принимает три аргумента:
  - `element` - текущий элемент массива;
  - `index` (необязательный) - индекс текущего элемента;
  - `array` (необязательный) - сам массив, в котором происходит поиск.
- `thisArg` (необязательный) - значение, которое будет использовано в качестве `this` при вызове функции `callback`.

* Пример:

```javascript
const numbers = [1, 2, 3, 4, 5, 6];

const evenNumber = numbers.find((number) => number % 2 === 0);

console.log(evenNumber); // 2
```

> В этом примере мы создали массив `numbers`, содержащий числа от 1 до 6. Затем мы использовали метод `find()` для поиска первого четного числа в массиве. Функция `callback` проверяет, делится ли текущее число на 2 без остатка. Метод `find()` возвращает первое число, которое удовлетворяет этому условию - 2.

### 14 Метод `reduce()` используется для последовательного применения функции к элементам массива с целью получения одного результата. Он принимает два аргумента: функцию-редуктор и начальное значение аккумулятора.

> Функция-редуктор принимает два аргумента: аккумулятор и текущий элемент массива. Она выполняет некоторые операции с этими аргументами и возвращает новое значение аккумулятора. Новое значение аккумулятора затем передается следующему вызову функции-редуктор с новым элементом массива.

> Начальное значение аккумулятора передается вторым аргументом метода `reduce()`. Если он не указан, то первый элемент массива становится начальным значением аккумулятора.

* Пример использования метода `reduce()`:

```javascript
const numbers = [1, 2, 3, 4, 5];

const sum = numbers.reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);

console.log(sum); // 15
```

> В этом примере мы используем метод `reduce()` для вычисления суммы элементов массива `numbers`. Начальное значение аккумулятора равно 0, а функция-редуктор просто складывает текущий элемент массива с аккумулятором. В результате мы получаем сумму всех элементов массива.

### 15 Метод `forEach()` используется для выполнения функции для каждого элемента массива без возвращения нового массива. Он принимает функцию обратного вызова в качестве аргумента и вызывает ее для каждого элемента массива. Функция обратного вызова может принимать три аргумента: текущий элемент, индекс текущего элемента и сам массив. Пример использования метода `forEach()`:

```javascript
const arr = [1, 2, 3, 4, 5];

arr.forEach(function(element, index, array) {
  console.log(`Element ${element} at index ${index} in array ${array}`);
});

// Output:
// Element 1 at index 0 in array 1,2,3,4,5
// Element 2 at index 1 in array 1,2,3,4,5
// Element 3 at index 2 in array 1,2,3,4,5
// Element 4 at index 3 in array 1,2,3,4,5
// Element 5 at index 4 in array 1,2,3,4,5
```

### 16 Метод `indexOf()` используется для поиска индекса первого вхождения заданного элемента в массиве. Если элемент не найден, метод возвращает -1. 

> Синтаксис: `arr.indexOf(searchElement[, fromIndex])`

- `searchElement` - элемент, индекс которого нужно найти в массиве.
- `fromIndex` (необязательный) - индекс, с которого начинается поиск элемента в массиве. Если значение `fromIndex` меньше 0, то поиск будет осуществляться от конца массива.

* Пример использования:

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr.indexOf(3)); // 2
console.log(arr.indexOf(6)); // -1
console.log(arr.indexOf(2, 2)); // -1
console.log(arr.indexOf(2, -3)); // 1
```

### 16.Метод `includes()` используется для проверки наличия заданного элемента в массиве. Если элемент найден, метод возвращает `true`, в противном случае - `false`. Например:

```javascript
const arr = [1, 2, 3, 4, 5];
console.log(arr.includes(3)); // true
console.log(arr.includes(6)); // false
```

# Destructuring
> Деструктурирование (destructuring) - это способ извлечь значения из объекта или массива и сохранить их в переменных. В языке JavaScript деструктурирование появилось в стандарте ES6.

* Примеры:

> 1. Деструктурирование массива

```js
var arr = [1, 2, 3];
var [a, b, c] = arr;

console.log(a); // 1
console.log(b); // 2
console.log(c); // 3
```

> 2. Деструктурирование объекта

```js
var obj = { name: "John", age: 30 };
var { name, age } = obj;

console.log(name); // "John"
console.log(age); // 30
```

> 3. Деструктурирование с параметрами по умолчанию

```js
var arr = [1, 2];
var [a, b, c = 3] = arr;

console.log(a); // 1
console.log(b); // 2
console.log(c); // 3
```

> 4. Деструктурирование с использованием оператора rest

```js
var arr = [1, 2, 3, 4, 5];
var [a, b, ...c] = arr;

console.log(a); // 1
console.log(b); // 2
console.log(c); // [3, 4, 5]
```
# Spread и Rest - это два синтаксических оператора в JS, которые позволяют с легкостью работать с массивами, объектами и функциями.

# Spread - это оператор ..., который раскрывает массивы и объекты на элементы. Он позволяет вставлять элементы массива или объекта в другой массив или объект, а также передавать аргументы в функцию. Например:

```js
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];

let merged = [...arr1, ...arr2]; // объединяем два массива

console.log(merged); // [1, 2, 3, 4, 5, 6]

let obj1 = { a: 1, b: 2 };
let obj2 = { c: 3, d: 4 };

let mergedObj = { ...obj1, ...obj2 }; // объединяем два объекта

console.log(mergedObj); // { a: 1, b: 2, c: 3, d: 4 }
```

# Rest - это оператор ..., который воспринимает все оставшиеся аргументы в функции как массив. Он позволяет передавать неопределенное количество аргументов в функцию. Например:

```js
function sum(a, b, ...rest) {
  let result = a + b;
  for (let i = 0; i < rest.length; i++) {
    result += rest[i];
  }

  return result;
}

console.log(sum(1, 2)); // 3
console.log(sum(1, 2, 3, 4, 5)); // 15
```

> В примерах выше мы используем оператор ... для раскрытия массивов и объектов, а также для передачи неопределенного количества аргументов в функцию. Благодаря этим операторам можно легко и быстро создавать новые структуры или работать с уже существующими данными.


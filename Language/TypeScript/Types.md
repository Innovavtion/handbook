# Основные типы

### Примитивы

```ts
let name: string = "Name"; // Строковый тип
let age: number = 20; // Числовой тип
let married: boolean = false; // Boolean тип
```

### Массивы

```ts
let names: string[] = ["Name", "Name2"]; // Массив строк
let ages: number[] = [2, 3]; // Массив чисел

let names: Array<string>; // Тоже самое что и массив строк. Джинерик.
```

### Any

TypeScript также имеет специальный тип, any который вы можете использовать, когда не хотите, чтобы определенное значение вызывало ошибки проверки типов.

### Типовые аннотации к переменным

Когда вы объявляете переменную с помощью const, var или let, вы можете дополнительно добавить аннотацию типа, чтобы явно указать тип переменной.

```ts
let myName: string = "Alice";
// Везде, где это возможно, TypeScript пытается автоматически определить типы в вашем коде.
// Например, тип переменной выводится на основе типа ее инициализатора
let myName = "Alice";
```

### Аннотации типов параметров функций

Когда вы объявляете функцию, вы можете добавить аннотации типа после каждого параметра, чтобы объявить, какие типы параметров принимает функция. Аннотации типа параметра идут после имени параметра:

```ts
// Указываем какого типа нужно перадать аргумент(параметр) иначе ошибка
function greet(name: string) {
  console.log("Hello, " + name.toUpperCase() + "!!");
}
```

### Аннотации типов параметров функций

Указываем для того чтобы понять, что должна вернуть функция

```ts
function greet(): number {
  return 26;
}
```

### Типы объектов

Помимо примитивов, наиболее распространенным типом, с которым вы столкнетесь, является объектный тип . Это относится к любому значению JavaScript со свойствами, а это почти все! Чтобы определить тип объекта, мы просто перечисляем его свойства и их типы.

```ts
// Указываем какие типы будут у передаваемого объекта
function printCoord(pt: { x: number; y: number }) {
  console.log("The coordinate's x value is " + pt.x);
  console.log("The coordinate's y value is " + pt.y);
}
printCoord({ x: 3, y: 7 });
```

Типы объектов также могут указывать, что некоторые или все их свойства являются необязательными. Для этого добавьте **?** после имени свойства:

```ts
// у элемента last стоит вопрос, который указывает, что его не обезательно передавать
function printName(obj: { first: string; last?: string }) {
  // ...
}
// Все нормально отработает
printName({ first: "Bob" });
printName({ first: "Alice", last: "Alisson" });
```

### Типы союзов

Система типов TypeScript позволяет вам создавать новые типы из существующих, используя большое количество операторов. Теперь, когда мы знаем, как писать несколько типов, пора начать комбинировать их интересными способами.

Давайте напишем функцию, которая может работать со строками или числами:

```ts
function printId(id: number | string) {
  console.log("Your ID is: " + id);
}
// OK
printId(101);
// OK
printId("202");
// Error
printId({ myID: 22342 });
```

TypeScript разрешает операцию только в том случае, если она действительна для каждого члена союза. Например, если у вас есть union string | number, вы не можете использовать методы, доступные только для string:

```ts
function printId(id: number | string) {
  console.log(id.toUpperCase());
  // Property 'toUpperCase' does not exist on type 'string | number'.
  // Property 'toUpperCase' does not exist on type 'number'.
}
```

### Утверждение типа

Например, если вы используете document.getElementById, TypeScript знает только, что это вернет что - то вроде HTMLElement, но вы можете знать, что ваша страница всегда будет иметь HTMLCanvasElementидентификатор с заданным идентификатором.

В этой ситуации вы можете использовать утверждение типа , чтобы указать более конкретный тип:

```ts
const myCanvas = document.getElementById("main_canvas") as HTMLCanvasElement;
```

Вы также можете использовать синтаксис угловых скобок (кроме случаев, когда код находится в .tsxфайле), который эквивалентен:

```ts
const myCanvas = <HTMLCanvasElement>document.getElementById("main_canvas");
```

Подобно аннотации типа, утверждения типа удаляются компилятором и не влияют на поведение вашего кода во время выполнения.

### Буквенные типы

Сами по себе литеральные типы не очень ценны:

```ts
let x: "hello" = "hello";
// OK
x = "hello";
// Error
x = "howdy";
//Type '"howdy"' is not assignable to type '"hello"'.
```

Нет смысла иметь переменную, которая может иметь только одно значение!

Но объединяя литералы в союзы, вы можете выразить гораздо более полезную концепцию — например, функции, которые принимают только определенный набор известных значений:

```ts
function printText(s: string, alignment: "left" | "right" | "center") {
  // ...
}
printText("Hello, world", "left");
printText("G'day, mate", "centre");
//Argument of type '"centre"' is not assignable to parameter of type '"left" | "right" | "center"'.
```

[TypeScript - Everyday Types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html)

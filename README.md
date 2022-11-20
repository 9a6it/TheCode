* [**HTML**](#html)
* [**CSS**](#css)
* [**JS**](#js)

### HTML

*Базовые части разметки*
* Современный тип документа `<!DOCTYPE html>`
* Корневой элемент `<html>` с языком документа `lang`
* Метаинформация `<head>`
  * Кодировка документа `<meta charset="utf-8">`. Кодировка символов на странице явно указана, чтобы обеспечить корректное отображение текста. Кодировка `utf-8` предпочтительна.
  * `<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=1.0">`
  * Заголовок документа `<title>`
* Тело документа `<body>`
```html
<!DOCTYPE html>
<html lang="ru">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=1.0">
    <title>Заголовок страницы</title>
  </head>
  <body>Тело страницы</body>
</html>
```
\
*Регистр тегов и атрибутов*
* Имена тегов, атрибуты и их значения записаны строчными.
* Исключение: атрибуты для SVG-элементов, например: `viewBox`, `preserveAspectRatio` и другие.
```html
<ul>
  <li>Первый</li>
  <li>Второй</li>
  <li>Третий</li>
</ul>

<img class="image" src="images/picture.png" width="400" height="400" alt="Кот смотрит на солнышко">

<svg width="27" height="16" viewBox="0 0 128 76">
  <path d="M125,5.15c.89-3,0-5.15-4.23-5.15h-14a6,6,0,0,0-6.09Z"/>
</svg>
```
\
*Форматирование тегов*
* Вложенность тегов обозначается переносами и отступами.
* Каждый новый вложенный тег переносится на отдельную строку с отступом, кроме текстовых элементов.
* Текст внутри тегов остаётся на одной строке с тегами.
```html
<div class="menu">
  <ul>
    <li>
      <a href="#">Первый</a>
    </li>
    <li>
      <a href="#">Второй</a>
    </li>
    <li>
      <a href="#">Третий</a>
    </li>
  </ul>
</div>

<p><a href="#">В этом репозитории</a> вы увидите замечательную возможность оптимизацией графикой, а в <a href="#">этом</a> оптимизацию шрифтов.</p>
<p>Также в <i>тексте</i> может быть <b>какое-то</b> выделение.</p>
```
\
*Двойные и одиночные теги*
* Двойные теги имеют открывающий и закрывающий теги.
* Одиночные теги не имеют закрывающий тег или слэш.
```html
<ul>
  <li>Первый</li>
  <li>Второй</li>
  <li>Третий</li>
</ul>

<img src="images/picture.png" width="400" height="400" alt="Кот смотрит на солнышко">

<input type="text" name="name">
```
\
*Порядок атрибутов*
* Атрибут class идёт сразу после имени тега.
* Атрибуты идут в одном порядке, чтобы упростить их чтение.
```html
<label class="field-group-label" for="appointment-phone">
<input class="field-group-input field" type="text" id="appointment-phone" placeholder="+7-000-000-00-00">

<label class="field-group-label" for="appointment-date">
<input class="field-group-input field" type="text" id="appointment-date" placeholder="01.01.2020">
```
\
*Логические атрибуты*
* Логические атрибуты записаны без значения и в единообразной последовательности во всём документе.
```html
<input type="text" disabled required>
```
\
*Форматирование атрибутов*
* В записи атрибутов нет пробелов вокруг знака «равно» `=`.
```html
<input class="field-group-input field" type="text" id="appointment-date" placeholder="01.01.2020">
```
\
*Кавычки в атрибутах и в значениях*
* Значения атрибутов записаны в двойных кавычках.
* Вложенные кавычки в значениях являются одинарными.
```html
<input class="field-group-input field" type="text" id="appointment-date" placeholder="01.01.2020">

<button class="button" type="button" onclick="show('menu')">Меню</button>
```
\
*Размеры замещаемых элементов*
* У изображений, видео и `iframe` указаны размеры.
* По возможности изображениям указываются действительные размеры, так как это улучшает производительность отрисовки страницы: браузер не будет перерисовывать страницу в процессе загрузки и отображения изображения.
* В атрибутах нет единиц измерения.
```html
<img src="logo.png" alt="" width="300" height="150">
<svg width="16" height="16" xmlns="http://www.w3.org/2000/svg"></svg>
<video src="source/video.mp4" width="400" height="400"></video>
<iframe src="https://maps.google.com" width="400" height="400"></iframe>
```
\
*Разделители в имени класса*
* Разделителями в имени класса являются только дефисы `-` и подчёркивания `_`. В коде необходимо придерживаться одного стиля.
```html
<input class="form-input form-input-field" type="text">
<input class="form_input form_input_field" type="text">
<input class="form__input form-input__field" type="text">
<input class="form--input form-input--field" type="text">
```
\
*Атрибут* `method` *в форме*
* В атрибуте `method` указан тип отправки данных.
```html
<form method="post"></form>
<form method="get"></form>
```
\
*Подключение стилей*
* Стилевые файлы подключены с помощью `<link>` внутри `<head>`. При этом атрибут `type` для тега `<link>` не указан, так как его значение `text/css` устанавливается по умолчанию.
```html
<!DOCTYPE html>
<html lang="ru">
  <head>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>...</body>
</html>
```
\
*Подключение скриптов*
* Скрипты подключены в самом низу страницы, чтобы при её загрузке не блокировать отображение содержимого.
* При подключении скриптов в теге `<script>` атрибут `type` не указан, так как его значение `text/javascript` устанавливается по умолчанию.
```html
<!DOCTYPE html>
<html lang="ru">
  <head>...</head>
  <body>
    <!-- Содержимое страницы -->
    <script src="app.js"></script>
  </body>
</html>
```

### CSS

*Правило `@import`*
* Правило `@import` работает медленнее, чем тег `<link>`. В стилях `@import` не использован.
```html
<link rel="stylesheet" href="module.css">
```
\
*Регистр селекторов и свойств*
* Селекторы и свойства записаны строчными буквами.
```
.element {
  color: #ff0000;
}
```
\
*Структура объявления*
* Перед открывающейся фигурной скобкой стоит пробел. После скобки запись идёт с новой строки.
* Свойства стоят на отдельных строках.
* Свойства внутри блока имеют один внутренний отступ.
* После двоеточия стоит пробел. Перед двоеточием пробел не нужен.
* В конце объявления стоит точка с запятой.
* Закрывающая скобка стоит на новой строке и без отступа.
* Между блоками правил есть одна пустая строка.
```
.block {
  margin-bottom: 0;
  margin-top: 0;
  font-size: 14px;
  line-height: 20;
  color: #ff0000;
}

.element {
  background-color: #000000;
}
```
\
*Имена классов*
* Имена классов записаны строчными буквами.
* Имена классов такие, что по ним можно быстро понять, какому элементу страницы задан класс. Избегайте сокращений, но не делайте их слишком длинными (более трёх слов).
* Для написания классов использованы английские слова и термины. В названиях классов и атрибутов нет транслита.
```
.button { ... }
.alert-danger { ... }
.user-picture { ... }
.layout-center { ... }
```
\
*Перенос селекторов*
* Селекторы, разделённые запятой, записаны на новых строках.
```
h1,
h2,
h3 {
  margin-top: 0;
}
```
\
*Пробелы между комбинаторами*
* До и после комбинатора между селекторами стоит один пробел.
```
h2 + h3 { ... }
ul > li { ... }
```
\
*Формат цветов*
* Цвета записаны строчными в 6-значном формате HEX.
* Шестнадцатеричное значение цвета не сокращено, а записано полностью из всех шести символов. Для записи использованы строчные буквы.
* Цвета могут быть записаны функциями `rgba` или `hsla`, если нужна прозрачность.
```
.block {
  background-color: #ff0000;
  border-left-color: #00ff00;
  color: rgba(0, 0, 0, 0.5);
}
```
\
*Кавычки*
* Во всех случаях в стилях использованы двойные кавычки.
* В необязательных случаях кавычки не опущены.
```
.field[type="text"] {
  background-image: url("images/cat.jpg");
}
```
\
*Ведущий ноль и пробелы после запятых*
* Начальный ноль для значений не сокращён.
* После запятых в перечислениях стоит пробел.
```
.block {
  opacity: 0.5;
  background-color: rgba(0, 0, 0, 0.5);
}
```
\
*Повторяющиеся свойства*
* Свойства не повторяются в рамках одной декларации.
* Свойство может повторяться, если раньше описан сброс или общий случай.
```
.block {
  margin: 0;
  margin-left: 20px;
  border: 10px solid #000000;
  border-bottom-color: #ff0000;
}
```
\
*Единицы измерения*
* Единицы измерения не указаны там, где в них нет необходимости.
* В кастомных свойствах нужно указывать единицу измерения.
```
:root {
  --size: 0px;
}

.element {
  border: 0;
  box-shadow: 0 1px 2px #cccccc, inset 0 1px 0 #ffffff;
  margin-top: 0;
  width: calc(100% - var(--size));
}
```
\
*Дробные значения*
* В дробных значениях нет больше двух знаков после точки.
```
.block {
  width: 2.33%;
}
```
\
`!important`
* Ключевое слово `!important` не использовано для борьбы со специфичностью.
* Универсальные классы-хелперы могут использовать `!important`.
```
.visually-hidden {
  position: absolute !important;
  width: 1px !important;
  height: 1px !important;
  margin: 0 !important;
  border: 0 !important;
  padding: 0 !important;
  clip: rect(0 0 0 0) !important;
  overflow: hidden !important;
}
```
\
*Доступное скрытие*
* Контент скрыт утилитарным классом `visually-hidden`, чтобы он был доступен для скринридеров и поисковиков.
```
.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: 0;
  border: 0;
  padding: 0;
  white-space: nowrap;
  clip-path: inset(100%);
  clip: rect(0 0 0 0);
  overflow: hidden;
}
```
```html
<h2 class="visually-hidden">Заголовок</h2>
```
\
*Порядок свойств*
* Объявления логически связанных свойств сгруппированы в следующем порядке:
  * Позиционирование
  * Блочная модель
  * Типографика
  * Оформление
  * Анимация
  * Разное
* Позиционирование следует первым, потому что оно влияет на положение блоков в потоке документа. Блочная модель идёт следующей, так как она определяет размеры и расположение блоков.
* Все остальные объявления, которые изменяют вид внутренних частей блоков и не оказывают влияния на другие блоки, идут в последнюю очередь.
* Сгруппированные объявления в правиле отделены друг от друга пустой строкой.
* Порядок объявления подробных правил, таких как `font-size`, `font-family`, `line-height`, соответствует порядку в сокращённой версии правила. В случае совместного использования подробных и сокращённых правил, первой идёт сокращённая версия.
```
.declaration-order {
  /* Позиционирование */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Блочная модель */
  display: block;
  float: right;
  width: 100px;
  height: 100px;
  margin: 10px;
  padding: 10px;

  /* Типографика */
  font-family: "Arial", sans-serif;
  font-style: normal;
  font-size: 13px;
  line-height: 20px;
  font-weight: 700;
  text-align: center;
  color: #333333;

  /* Оформление */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;
  opacity: 1;

  /* Анимация */
  transition: color 1s;

  /* Разное */
  will-change: auto;
}
```

### JS

***Типы***

1.1. Простые типы: когда вы взаимодействуете с простым типом, вы напрямую работаете с его значением.
* `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`
  * `symbol` и `bigint` не могут быть полностью заполифиллены, поэтому они не должны использоваться, если разработка ведётся для браузеров или других сред, которые не поддерживают их нативно.

1.2. Сложные типы: когда вы взаимодействуете со сложным типом, вы работаете со ссылкой на его значение.
* `object`, `array`, `function`

\
***Объявление переменных***

2.1. Используйте `const` для объявления переменных; избегайте `var`. Это гарантирует, что вы не сможете переопределять значения, так как это может привести к ошибкам и к усложнению понимания кода.
2.2. Если вам необходимо переопределять значения, то используйте `let` вместо `var`.
2.3. Помните, что у `let` и `const` блочная область видимости, в то время как `var` имеет функциональную область видимости.

\
***Объекты***

3.1. Для создания объекта используйте литеральную нотацию.
```js
// плохо
const item = new Object();

// хорошо
const item = {};
```

3.2. Используйте вычисляемые имена свойств, когда создаёте объекты с динамическими именами свойств. Они позволяют вам определить все свойства объекта в одном месте.
```js
function getKey(k) {
  return `a key named ${k}`;
}

// плохо
const obj = {
  id: 5,
  name: 'San Francisco',
};
obj[getKey('enabled')] = true;

// хорошо
const obj = {
  id: 5,
  name: 'San Francisco',
  [getKey('enabled')]: true,
};
```

3.3. Используйте сокращённую запись метода объекта.
```js
// плохо
const atom = {
  value: 1,

  addValue: function (value) {
    return atom.value + value;
  },
};

// хорошо
const atom = {
  value: 1,

  addValue(value) {
    return atom.value + value;
  },
};
```

3.4. Используйте сокращённую запись свойств объекта. Это короче и понятнее.
```js
const lukeSkywalker = 'Luke Skywalker';

// плохо
const obj = {
  lukeSkywalker: lukeSkywalker,
};

// хорошо
const obj = {
  lukeSkywalker,
};
```

3.5. Группируйте ваши сокращённые записи свойств в начале объявления объекта. Так легче сказать, какие свойства используют сокращённую запись.
```js
const anakinSkywalker = 'Anakin Skywalker';
const lukeSkywalker = 'Luke Skywalker';

// плохо
const obj = {
  episodeOne: 1,
  twoJediWalkIntoACantina: 2,
  lukeSkywalker,
  episodeThree: 3,
  mayTheFourth: 4,
  anakinSkywalker,
};

// хорошо
const obj = {
  lukeSkywalker,
  anakinSkywalker,
  episodeOne: 1,
  twoJediWalkIntoACantina: 2,
  episodeThree: 3,
  mayTheFourth: 4,
};
```

3.6. Только недопустимые идентификаторы помещаются в кавычки. На наш взгляд, такой код легче читать. Это улучшает подсветку синтаксиса, а также облегчает оптимизацию для многих JS-движков.
```js
// плохо
const bad = {
  'foo': 3,
  'bar': 4,
  'data-blah': 5,
};

// хорошо
const good = {
  foo: 3,
  bar: 4,
  'data-blah': 5,
};
```

3.7. Не вызывайте напрямую методы `Object.prototype`, такие как `hasOwnProperty`, `propertyIsEnumerable`, и `isPrototypeOf`. Эти методы могут быть переопределены в свойствах объекта, который мы проверяем `{ hasOwnProperty: false }`, или этот объект может быть `null` (`Object.create(null)`).
```js
// плохо
console.log(object.hasOwnProperty(key));

// хорошо
console.log(Object.prototype.hasOwnProperty.call(object, key));

// отлично
const has = Object.prototype.hasOwnProperty; // кэшируем запрос в рамках модуля
console.log(has.call(object, key));
/* или */
import has from 'has'; // https://www.npmjs.com/package/has
console.log(has(object, key));
```

3.8. Используйте синтаксис расширения вместо `Object.assign` для поверхностного копирования объектов. Используйте параметр оставшихся свойств, чтобы получить новый объект с некоторыми опущенными свойствами.
```js
// очень плохо
const original = { a: 1, b: 2 };
const copy = Object.assign(original, { c: 3 }); // эта переменная изменяет `original`
delete copy.a; // если сделать так

// плохо
const original = { a: 1, b: 2 };
const copy = Object.assign({}, original, { c: 3 }); // copy => { a: 1, b: 2, c: 3 }

// хорошо
const original = { a: 1, b: 2 };
const copy = { ...original, c: 3 }; // copy => { a: 1, b: 2, c: 3 }

const { a, ...noA } = copy; // noA => { b: 2, c: 3 }
```

\
***Массивы***

4.1. Для создания массива используйте литеральную нотацию.
```js
// плохо
const items = new Array();

// хорошо
const items = [];
```

4.2. Для добавления элемента в массив используйте `push()` вместо прямого присваивания.
```js
const someStack = [];

// плохо
someStack[someStack.length] = 'abracadabra';

// хорошо
someStack.push('abracadabra');
```

4.3. Для копирования массивов используйте оператор расширения `...`.
```js
// плохо
const len = items.length;
const itemsCopy = [];
let i;

for (i = 0; i < len; i += 1) {
  itemsCopy[i] = items[i];
}

// хорошо
const itemsCopy = [...items];
```

4.4. Для преобразования итерируемого объекта в массив используйте оператор расширения `...` вместо `Array.from()`.
```js
const foo = document.querySelectorAll('.foo');

// хорошо
const nodes = Array.from(foo);

// отлично
const nodes = [...foo];
```

4.5. Используйте `Array.from()` для преобразования массивоподобного объекта в массив.
```js
const arrLike = { 0: 'foo', 1: 'bar', 2: 'baz', length: 3 };

// плохо
const arr = Array.prototype.slice.call(arrLike);

// хорошо
const arr = Array.from(arrLike);
```

4.6. Используйте `Array.from()` вместо оператора расширения `...` для маппинга итерируемых объектов, это позволяет избежать создания промежуточного массива.
```js
// плохо
const baz = [...foo].map(bar);

// хорошо
const baz = Array.from(foo, bar);
```

4.7. Используйте операторы `return` внутри функций обратного вызова в методах массива. Можно опустить `return`, когда тело функции состоит из одной инструкции, возвращающей выражение без побочных эффектов (8.2).
```js
// хорошо
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});

// хорошо
[1, 2, 3].map((x) => x + 1);

// плохо - нет возвращаемого значения, следовательно, `acc` становится `undefined` после первой итерации
[[0, 1], [2, 3], [4, 5]].reduce((acc, item, index) => {
  const flatten = acc.concat(item);
});

// хорошо
[[0, 1], [2, 3], [4, 5]].reduce((acc, item, index) => {
  const flatten = acc.concat(item);
  return flatten;
});

// плохо
inbox.filter((msg) => {
  const { subject, author } = msg;
  if (subject === 'Mockingbird') {
    return author === 'Harper Lee';
  } else {
    return false;
  }
});

// хорошо
inbox.filter((msg) => {
  const { subject, author } = msg;
  if (subject === 'Mockingbird') {
    return author === 'Harper Lee';
  }

  return false;
});
```

4.8. Если массив располагается на нескольких строках, то используйте разрывы строк после открытия и перед закрытием скобок.
```js
// плохо
const arr = [
  [0, 1], [2, 3], [4, 5],
];

const objectInArray = [{
  id: 1,
}, {
  id: 2,
}];

const numberInArray = [
  1, 2,
];

// хорошо
const arr = [[0, 1], [2, 3], [4, 5]];

const objectInArray = [
  {
    id: 1,
  },
  {
    id: 2,
  },
];

const numberInArray = [
  1,
  2,
];
```

\
***Деструктуризация***

5.1. При обращении к нескольким свойствам объекта используйте деструктуризацию объекта. Деструктуризация сохраняет вас от создания временных переменных для этих свойств и от повторного доступа к объекту. Повторный доступ к объектам создаёт более повторяющийся код, требует большего чтения и создаёт больше возможностей для ошибок. Деструктуризация объектов также обеспечивает единое местоположение определения структуры объекта, которое используется в блоке, вместо того, чтобы требовать чтения всего блока для определения того, что используется.
```js
// плохо
function getFullName(user) {
  const firstName = user.firstName;
  const lastName = user.lastName;

  return `${firstName} ${lastName}`;
}

// хорошо
function getFullName(user) {
  const { firstName, lastName } = user;
  return `${firstName} ${lastName}`;
}

// отлично
function getFullName({ firstName, lastName }) {
  return `${firstName} ${lastName}`;
}
```

5.2. Используйте деструктуризацию массивов.
```js
const arr = [1, 2, 3, 4];

// плохо
const first = arr[0];
const second = arr[1];

// хорошо
const [first, second] = arr;
```

5.3. Используйте деструктуризацию объекта для множества возвращаемых значений, но не делайте тоже самое с массивами.Вы сможете добавить новые свойства через некоторое время или изменить порядок без последствий.
```js
// плохо
function processInput(input) {
  // затем происходит чудо
  return [left, right, top, bottom];
}

// при вызове нужно подумать о порядке возвращаемых данных
const [left, __, top] = processInput(input);

// хорошо
function processInput(input) {
  // затем происходит чудо
  return { left, right, top, bottom };
}

// при вызове выбираем только необходимые данные
const { left, top } = processInput(input);
```

\
***Строки***

6.1. Используйте одинарные кавычки `''` для строк.
```js
// плохо
const name = "Capt. Janeway";

// плохо - литерал шаблонной строки должен содержать интерполяцию или переводы строк
const name = `Capt. Janeway`;

// хорошо
const name = 'Capt. Janeway';
```

6.2. Строки, у которых в строчке содержится более 100 символов, не пишутся на нескольких строчках с использованием конкатенации. Работать с разбитыми строками неудобно и это затрудняет поиск по коду.
```js
// плохо
const errorMessage = 'This is a super long error that was thrown because \
of Batman. When you stop to think about how Batman had anything to do \
with this, you would get nowhere \
fast.';

// плохо
const errorMessage = 'This is a super long error that was thrown because ' +
  'of Batman. When you stop to think about how Batman had anything to do ' +
  'with this, you would get nowhere fast.';

// хорошо
const errorMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.';
```

6.3. При создании строки программным путём используйте шаблонные строки вместо конкатенации. Шаблонные строки дают вам читабельность, лаконичный синтаксис с правильными символами перевода строк и функции интерполяции строки.
```js
// плохо
function sayHi(name) {
  return 'How are you, ' + name + '?';
}

// плохо
function sayHi(name) {
  return ['How are you, ', name, '?'].join();
}

// плохо
function sayHi(name) {
  return `How are you, ${ name }?`;
}

// хорошо
function sayHi(name) {
  return `How are you, ${name}?`;
}
```

6.4. Никогда не используйте `eval()`, так как это открывает множество уязвимостей.

6.5. Не используйте в строках необязательные экранирующие символы. Обратные слеши ухудшают читабельность, поэтому они должны быть только при необходимости.
```js
// плохо
const foo = '\'this\' \i\s \"quoted\"';

// хорошо
const foo = '\'this\' is "quoted"';
const foo = `my name is '${name}'`;
``

\
***Функции***

7.1. Используйте функциональные выражения вместо объявлений функций. У объявлений функций есть подъём. Это означает, что можно использовать функцию до того, как она определена в файле, но это вредит читабельности и поддержке. Если вы обнаружили, что определение функции настолько большое или сложное, что мешает понимать остальную часть файла, то, возможно, пришло время извлечь его в отдельный модуль. Не забудьте явно назвать функциональное выражение, независимо от того, подразумевается ли имя из содержащейся переменной (такое часто бывает в современных браузерах или при использовании компиляторов, таких как Babel). Это помогает точнее определять место ошибки по стеку вызовов.
```js
// плохо
function foo() {
  // ...
}

// плохо
const foo = function () {
  // ...
};

// хорошо
// лексическое имя, отличное от вызываемой(-ых) переменной(-ых)
const foo = function uniqueMoreDescriptiveLexicalFoo() {
  // ...
};
```


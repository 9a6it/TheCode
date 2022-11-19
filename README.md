**Структура**

*Группировка файлов*
* Файлы схожих типов группируются в папки: картинки, стили, скрипты, шрифты.
* Если внутри папок файлов становится много или выделяются подгруппы, можно добавить вложенные папки.
```
project/
  pictures/
    catalog/
      wine.jpg
      cheese.png
    product/
      wine-big.jpg
      cheese-big.png
  images/
    logo.svg
    favicons/
      32x32.png
      16x16.png
    content/
      cat.jpg
      map.png
  scripts/
    menu.js
    map.js
  styles/
    styles.css
  catalog.html
  index.html
```

\
**HTML**

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

*Регистр тегов и атрибутов*
* Имена тегов, атрибуты и их значения записаны строчными.
* Исключение: атрибуты для SVG-элементов, например: `viewBox`, `preserveAspectRatio` и другие.
```html
ul>
  <li>Первый</li>
  <li>Второй</li>
  <li>Третий</li>
</ul>

<img class="image" src="images/picture.png" width="400" height="400" alt="Кот смотрит на солнышко">

<svg width="27" height="16" viewBox="0 0 128 76">
  <path d="M125,5.15c.89-3,0-5.15-4.23-5.15h-14a6,6,0,0,0-6.09Z"/>
</svg>
```

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

*Порядок атрибутов*
* Атрибут class идёт сразу после имени тега.
* Атрибуты идут в одном порядке, чтобы упростить их чтение.
```html
<label class="field-group-label" for="appointment-phone">
<input class="field-group-input field" type="text" id="appointment-phone" placeholder="+7-000-000-00-00">

<label class="field-group-label" for="appointment-date">
<input class="field-group-input field" type="text" id="appointment-date" placeholder="01.01.2020">
```

*Логические атрибуты*
Логические атрибуты записаны без значения и в единообразной последовательности во всём документе.
```html
<input type="text" disabled required>
```

*Форматирование атрибутов*
* В записи атрибутов нет пробелов вокруг знака «равно» `=`.
```html
<input class="field-group-input field" type="text" id="appointment-date" placeholder="01.01.2020">
```

*Кавычки в атрибутах и в значениях*
* Значения атрибутов записаны в двойных кавычках.
* Вложенные кавычки в значениях являются одинарными.
```html
<input class="field-group-input field" type="text" id="appointment-date" placeholder="01.01.2020">

<button class="button" type="button" onclick="show('menu')">Меню</button>
```

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

*Разделители в имени класса*
* Разделителями в имени класса являются только дефисы `-` и подчёркивания `_`. В коде необходимо придерживаться одного стиля.
```html
<input class="form-input form-input-field" type="text">
<input class="form_input form_input_field" type="text">
<input class="form__input form-input__field" type="text">
<input class="form--input form-input--field" type="text">
```

*Атрибут* `method` *в форме*
* В атрибуте `method` указан тип отправки данных.
```html
<form method="post"></form>
<form method="get"></form>
```

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

\
**CSS**

*Правило `@import`*
* Правило `@import` работает медленнее, чем тег `<link>`. В стилях `@import` не использован.
```html
<link rel="stylesheet" href="module.css">
```

*Регистр селекторов и свойств*
* Селекторы и свойства записаны строчными буквами.
```
.element {
  color: #ff0000;
}
```

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

*Имена классов*
* Имена классов записаны строчными буквами.
* Имена классов такие, что по ним можно быстро понять, какому элементу страницы задан класс. Избегайте сокращений, но не делайте их слишком длинными (более трёх слов).
* Для написания классов использованы английские слова и термины. В названиях классов и атрибутов нет транслита.
```
.alert-danger { ... }
.user-picture { ... }
.button { ... }
.layout-center { ... }
```

*Перенос селекторов*
* Селекторы, разделённые запятой, записаны на новых строках.
```
h1,
h2,
h3 {
  margin-top: 0;
}
```

*Пробелы между комбинаторами*
* До и после комбинатора между селекторами стоит один пробел.
```
h2 + h3 { ... }
ul > li { ... }
```

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

*Кавычки*
* Во всех случаях в стилях использованы двойные кавычки.
* В необязательных случаях кавычки не опущены.
```
.field[type="text"] {
  background-image: url("images/cat.jpg");
}
```

*Ведущий ноль и пробелы после запятых*
* Начальный ноль для значений не сокращён.
* После запятых в перечислениях стоит пробел.
```
.block {
  opacity: 0.5;
  background-color: rgba(0, 0, 0, 0.5);
}
```

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

*Дробные значения*
* В дробных значениях нет больше двух знаков после точки.
```
.block {
  width: 2.33%;
}
```

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

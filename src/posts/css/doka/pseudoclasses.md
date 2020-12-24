---
title: Псевдоклассы
name: pseudo-classes
author: Roman_Ganin
co-authors:
designers:
contributors:
summary:
  - псевдокласс
  - селекторы
  - :active
  - :any
  - :any-link
  - :link
  - :visited
  - :checked
  - :default
  - :dir
  - :disabled
  - :enabled
  - :empty
  - :first
  - :first-child
  - :last-child
  - :nth-child
  - :nth-last-child
  - :only-child
  - :first-of-type
  - :nth-of-type
  - :last-of-type
  - :nth-last-of-type
  - :only-of-type
  - :fullscreen
  - :focus
  - :focus-within
  - :has
  - :hover
  - :indeterminate
  - :in-range
  - :out-of-range
  - :lang
  - :left
  - :right
  - :not
  - :optional
  - :required
  - :read-only
  - :read-write
  - :root
  - :target
  - :valid
  - :invalid
---

## Кратко

Псевдоклассы — особый вид селектора, который уточняет тип или состояние. Обычно это какой-то качественный признак: реакция на наведение курсора, порядок следования и другие.

## Пример

CSS для подсветки строки таблицы при наведении курсора:

```css
tr {
  /* В обычном состоянии цвет фон — белый */
  background: #fff;
}

tr:hover { /* При наведении курсора… */
  background: #c3bff5; /* …цвет фона изменится на голубой */
}
```

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="result" data-user="Realetive" data-slug-hash="wvzgJWP" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="table:hover">
  <span>See the Pen <a href="https://codepen.io/Realetive/pen/wvzgJWP">
  table:hover</a> by Roman Ganin (<a href="https://codepen.io/Realetive">@Realetive</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## Как это понять

Благодаря псевдоклассам мы можем контролировать _динамические_ параметры селекторов, то есть эти свойства сработают тогда, когда селектор **подходит** под дополнительный признак, не зависящий от уровня вложенности.

### Как пишется

```css
[селектор]:псевдокласс {
  свойство: значение;
}
```

Селектор может и отсутсвовать — тогда правило применится ко всем элементам, которые могут иметь признак этого псевдокласса (например, запись `:focus {}` применится к любому элементу, который будет выделен с помощью focus-навигации).

<!-- TODO: перелинковать со статьями, которые уже написаны -->

### `:active` ([основная статья](/posts/css/doka/active))

Применяется к интерактивным элементам в момент взаимодействия (например, нажатая кнопка).

### `:any`

Экспериментальный селектор (пока в черновиках спецификции). Позволяет сгруппировть схожие селекторы вместо последовательного перечисления через запятую.

### `:any-link` / `:link` ([основная статья](/posts/css/doka/link)) / `:visited` ([основная статья](/posts/css/doka/visited))

Применяется ко всем элементам,которые могут иметь атрибут `href` (`<a>`, `<area>` и `<link>`). `:link` характеризует ещё не посещённые страницы, `:visited` — наоборот, посещённые (в рамках одного домена).

### `:checked` ([основная статья](/posts/css/doka/checked))

Применяется к элементам, состояние которых меняется по атрибуту `checked`.

### `:default`

Находит элемент формы (`<input type="radio">`, `<input type="checkbox">`, `<option>`, `<button>`), установленный по умолчанию для группы связаных элементов (например, в случае с `<input type="checkbox">` селектор применится к тому чекбоксу, у которого в разметке установлен атрибут `checked`, т. е. он **по умолчанию** выбран).

### `:dir()`

Позволяет найти элементы по направлению текста в нём (например, в арабском направление письма идёт справа на лево).

### `:disabled` / `:enabled`

Позволяет находить элементы формы по состоянию их атрибута `disabled`.

### `:empty`

Применяется к элементам, у которых внутри нет других тегов. Например, можно проверить, что у кнопки не задан текст или иконка, чтобы задать минимальные размеры (хотя, для этого можно использовать и `min-width` / `min-height`).

### `:first`

Печатный селектор (применяется не в брауезере, а при выводе документа на печать) — определяет первую страницу.

### `:first-child` / `:last-child` / `:nth-child()` / `:nth-last-child()` / `:only-child`

Селекторы элемента по его положению относительно родителя (первый, последний, n-ый, единственный).

### `:first-of-type` / `:nth-of-type()` / `:last-of-typ`e /` :nth-last-of-type()` / `:only-of-type`

Селектор по типу внутри одного родителя.

### `:fullscreen`

Признак того, что документ развернули на всё окно (с помощью JavaScript).

### `:focus` ([основная статья](/posts/css/doka/focus)) / `:focus-within`

Элемент, который сейчас находится в фокусе (с помощью клавиши <kbd>Tab</kbd>). А `:focus-within` ещё обозначает элемент, внутри которого находится элемент в фокусе.

### `:has()` ([основная статья](/posts/css/doka/has))

Позволяет уточнить селектор, передав в аргумент отношение к элементу, к которому применятся псевдокласс `:has()`.

### `:hover` ([основная статья](/posts/css/doka/hover))

Элемент, на который сейчас навели курсор.

### `:indeterminate`

Элементы, который могут находиться в «промежуточном» состоянии:
- `<input type="checkbox">`, отображющий, что не все пункты вложенной группы были выделены;
- группа `<input type="radio">` с одинаковым `name`, но у которой ни один элемент не установлен в `checked`;
- `<progress>`.

### `:in-range` / `:out-of-range`

Применяется для `<input>`, у которого определены атрибуты `min` и `max` и введённое значение соответсвует (`:in-range`) или нет (`:out-of-range`) этому диапазону.

### `:lang()`

Селектор по языку содержимого текста.

### `:left` / `:right`

Печатные селекторы (применятся при выведении документа на печать), обозначающие левую (`:left`) или правую (`:right`) страницы.

### `:not()`

Находит элемент, которые **не соответсвует** селектору, который передан в качестве аргумента.

### `:optional` / `:required`

`:optional` находит любой `<input>`, у которого не устновлен атрибут `required` — то есть находит необязтельные поля ввода. А `:required` — наоборот, те `<input>`, у которых есть этот атрибут.

### `:read-only` / `:read-write`

Находит элементы, недоступные (`:read-only`) или наоборот (`:read-write`) для редактирования (например, в зависимости от наличия атрибута `disabled` или `readonly`).

### `:root`

Соответсвует корневому тегу-элементу документа. Для HTML это, соответсвенно, `<html>`, для SVG — `<svg>`, но выше по специфичности, чем просто селектор по тегу.

### `:target`

Селектор, который применится к элементу, `id` которого используется как якорная ссылка на фрагмент (например, на текущий блок можо сослаться по `<a href="#target">#target</a>`, а когда упоминание этого `id` будет в строке браузера, применятся стили, описанные в `:target`).

### `:valid` / `:invalid`

Селектор `:valid` соответсвует `<input>` или `<form>`-элементу, контент которого валиден в соответствии с типом поля. Обратный эффект у `:invalid` — сработает при ошибке HTML-валидации.

## Подсказки

💡 Псевдоклассы не обязательно описываются вместе с элементом — если он не указан, селектор будет обозначать любой доступный элемент, который *может иметь* этот псевдокласс (при активации нужного состояния).

## В работе

🛠 Понимание изменения состояния элементов и  манипулирование им через псевдоклассы помогает делать производительные интерфейсы даже без JavaScript или, например, создавать собственный стиль для контролов формы:

<p class="codepen" data-height="290" data-theme-id="light" data-default-tab="css,result" data-user="Realetive" data-slug-hash="KKgXmgX" data-preview="true" style="height: 290px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Кастомный чекбокс">
  <span>See the Pen <a href="https://codepen.io/Realetive/pen/KKgXmgX">
  Кастомный чекбокс</a> by Roman Ganin (<a href="https://codepen.io/Realetive">@Realetive</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

{% include "authors/Roman_Ganin/author.njk" %}

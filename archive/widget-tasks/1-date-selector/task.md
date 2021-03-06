importance: 5

---

# Селектор даты

Создайте тройной селектор даты, который выступает как единый компонент. То есть, можно подписываться на `"select"` сразу у этого компонента.

Конструктор:

```js
var dateSelector = new DateSelector({
  yearFrom: 2010, // начальный год в селекторе
  yearTo: 2020, // конечный год в селекторе
  value: new Date(2012, 2, 31) // текущая выбранная дата
});
```

События:

- `select` -- при изменении даты.

Методы:

- `setValue(date, quiet)` -- устанавливает дату `date`. Если второй аргумент `true`, то событие не генерируется.
- `getElement()` -- возвращает DOM-элемент для компоненты для вставки в документ.

Использование - добавление в документ:

```js
dateSelector.getElement().appendTo('body');
```

Использование - подписка на изменение и вывод значения:

```js
$(dateSelector).on("select", function(e) {
  $('#value').html(e.value);
});
```

Пример в действии:

[iframe border=1 src="solution"]

[edit task src="source"]

P.S. При выборе месяца дни должны подстраиваться под него. Чтобы не было доступно 31 февраля.
---
title: clear
slug: Web/CSS/clear
---

{{CSSRef}}

Свойство **`clear`** CSS указывает, может ли элемент быть рядом с плавающими [floating](/ru/docs/Web/CSS/float) элементами, которые предшествуют ему или должны быть перемещены вниз (очищены) под ними. Свойство `clear` применяется как к плавающим, так и к неплавающим элементам.

{{InteractiveExample("CSS Demo: clear")}}

```css interactive-example-choice
clear: none;
```

```css interactive-example-choice
clear: left;
```

```css interactive-example-choice
clear: right;
```

```css interactive-example-choice
clear: both;
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="example-container">
    <div class="floated-left">Left</div>
    <div class="floated-right">Right</div>
    <div class="transition-all" id="example-element">
      As much mud in the streets as if the waters had but newly retired from the
      face of the earth, and it would not be wonderful to meet a Megalosaurus,
      forty feet long or so, waddling like an elephantine lizard up Holborn
      Hill.
    </div>
  </div>
</section>
```

```css interactive-example
.example-container {
  border: 1px solid #c5c5c5;
  padding: 0.75em;
  text-align: left;
  line-height: normal;
}

.floated-left {
  border: solid 10px #ffc129;
  background-color: rgba(81, 81, 81, 0.6);
  padding: 1em;
  float: left;
}

.floated-right {
  border: solid 10px #ffc129;
  background-color: rgba(81, 81, 81, 0.6);
  padding: 1em;
  float: right;
  height: 150px;
}
```

При применении к неплавающим блокам он перемещает границу края [border edge](/ru/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model) элемента до тех пор, пока не окажется ниже края [margin edge](/ru/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model) поля всех соответствующих поплавков. Вертикальный край неплавающего блока сжимается.

Вертикальные поля между двумя плавающими элементами, с другой стороны, не будут разрушаться. При применении к плавающим элементам - [margin edge](/ru/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model) нижнего элемента перемещается ниже [margin edge](/ru/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model) всех соответствующих поплавков. Это влияет на положение более поздних поплавков, поскольку более поздние поплавки не могут быть расположены выше предыдущих.

Поплавки, которые имеют отношение к очистке, - это более ранние поплавки в одном и том же [контексте форматирования блоков](/ru/docs/Web/CSS/CSS_display/Block_formatting_context).

## Синтаксис

```css
/* Ключевые слова */
clear: none;
clear: left;
clear: right;
clear: both;
clear: inline-start;
clear: inline-end;

/* Global values */
clear: inherit;
clear: initial;
clear: unset;
```

### Значения

- `none`
  - : Является ключевым словом, указывающим, что элемент не перемещается вниз, чтобы очистить предыдущие плавающие элементы.
- `left`
  - : Является ключевым словом, указывающим, что элемент перемещается вниз, чтобы очистить _левые_ поплавки.
- `right`
  - : Является ключевым словом, указывающим, что элемент перемещается вниз, чтобы удалить прошлые _правые_ поплавки.
- `both`
  - : Это ключевое слово, указывающее, что элемент перемещается вниз, чтобы очистить как левые, так и правые поплавки.
- `inline-start`
  - : Является ключевым словом, указывающим, что элемент перемещается вниз для очистки поплавков _в начале содержащего его блока_, то есть _левые_ поплавки на скриптах **ltr** и _правые_ поплавки на скриптах **rtl**.
- `inline-end`
  - : Является ключевым словом, указывающим, что элемент перемещается вниз для очистки поплавков _в конце содержащего его блока_, то есть _правые_ поплавки на скриптах **ltr** и _левые_ поплавки на скриптах **rtl**.

### Формальный синтаксис

{{csssyntax}}

## Примеры

### clear: left

#### HTML

```html
<div class="wrapper">
  <p class="black">
    Давай лучше "бёзди хэппи" затянем, нежели Lorem ipsum dolor sit amet,
    consectetuer adipiscing elit. Phasellus sit amet diam. Duis mattis varius
    dui. Suspendisse eget dolor.
  </p>
  <p class="red">
    Пусть бегут неуклюже пешеходы по лужам, Lorem ipsum dolor sit amet,
    consectetuer adipiscing elit.
  </p>
  <p class="left">Этот абзац очищается слева.</p>
</div>
```

#### CSS

```css
.wrapper {
  border: 1px solid black;
  padding: 10px;
}
.left {
  border: 1px solid black;
  clear: left;
}
.black {
  float: left;
  margin: 0;
  background-color: black;
  color: #fff;
  width: 20%;
}
.red {
  float: left;
  margin: 0;
  background-color: pink;
  width: 20%;
}
p {
  width: 50%;
}
```

{{EmbedLiveSample('clear_left','100%','250')}}

### clear: right

#### HTML

```html
<div class="wrapper">
  <p class="black">
    Лучше нести бред и околесицу, но более осмысленную, чем Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit.
  </p>
  <p class="red">
    - Так я ж намедни намекал, что Lorem ipsum dolor sit amet, consectetuer
    adipiscing elit.
  </p>
  <p class="right">Этот абзац очищается справа.</p>
</div>
```

#### CSS

```css
.wrapper {
  border: 1px solid black;
  padding: 10px;
}
.right {
  border: 1px solid black;
  clear: right;
}
.black {
  float: right;
  margin: 0;
  background-color: black;
  color: #fff;
  width: 20%;
}
.red {
  float: right;
  margin: 0;
  background-color: pink;
  width: 20%;
}
p {
  width: 50%;
}
```

{{EmbedLiveSample('clear_right','100%','250')}}

### clear: both

#### HTML

```html
<div class="wrapper">
  <p class="black">
    Лучше нести осмысленную белиберду, чем "Lorem ipsum dolor sit amet,
    consectetuer adipiscing elit. Phasellus sit amet diam. Duis mattis varius
    dui. Suspendisse eget dolor.
  </p>
  <p class="red">
    Вот я и говорю, что "Lorem ipsum dolor sit amet, consectetuer adipiscing
    elit. Phasellus sit amet diam. Duis mattis varius dui. Suspendisse eget
    dolor".
  </p>
  <p class="both">Этот абзац очищает оба.</p>
</div>
```

#### CSS

```css
.wrapper {
  border: 1px solid black;
  padding: 10px;
}
.both {
  border: 1px solid black;
  clear: both;
}
.black {
  float: left;
  margin: 0;
  background-color: black;
  color: #fff;
  width: 20%;
}
.red {
  float: right;
  margin: 0;
  background-color: pink;
  width: 20%;
}
p {
  width: 45%;
}
```

{{EmbedLiveSample('clear_both','100%','300')}}

## Характеристики

{{Specifications}}

## Совместимость с браузерами

{{Compat}}

## Смотрите также

- [Box model](/ru/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model)

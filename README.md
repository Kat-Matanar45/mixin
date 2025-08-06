# 🎯 Полезные SASS миксины

Коллекция универсальных миксинов для ускорения верстки и улучшения читаемости кода.

---

## 1. 📱 Адаптивные media-запросы

```scss
@mixin respond($breakpoint) {
  @if $breakpoint == sm {
    @media (max-width: 576px) { @content; }
  } @else if $breakpoint == md {
    @media (max-width: 768px) { @content; }
  } @else if $breakpoint == lg {
    @media (max-width: 992px) { @content; }
  } @else if $breakpoint == xl {
    @media (max-width: 1200px) { @content; }
  }
}
```

**Пример:**

```scss
.container {
  padding: 20px;
  @include respond(md) {
    padding: 10px;
  }
}
```

---

## 2. 🎯 Центрирование Flexbox'ом

```scss
@mixin flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

**Пример:**

```scss
.modal {
  @include flex-center;
}
```

---

## 3. ✂️ Обрезка текста (многоточие)

```scss
@mixin text-truncate {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
```

**Пример:**

```scss
.title {
  width: 200px;
  @include text-truncate;
}
```

---

## 4. 📏 Размеры (ширина и высота)

```scss
@mixin size($width, $height: $width) {
  width: $width;
  height: $height;
}
```

**Пример:**

```scss
.avatar {
  @include size(50px);
}
```

---

## 5. 🧩 Псевдоэлементы

```scss
@mixin pseudo($display: block, $pos: absolute, $content: '') {
  content: $content;
  display: $display;
  position: $pos;
}
```

**Пример:**

```scss
.button::after {
  @include pseudo;
  background: red;
  width: 5px;
  height: 5px;
}
```

---

## 6. 🌈 Градиентный фон

```scss
@mixin gradient($start, $end, $angle: 90deg) {
  background: linear-gradient($angle, $start, $end);
}
```

**Пример:**

```scss
.header {
  @include gradient(#ff8a00, #e52e71);
}
```

---

## 7. ⚡ Плавные переходы

```scss
@mixin transition($props: all, $duration: 0.3s, $timing: ease) {
  transition: $props $duration $timing;
}
```

**Пример:**

```scss
.link {
  @include transition(color);
}
```

---

## 8. 🔤 Подключение шрифтов

```scss
@mixin font-face($name, $file, $weight: 400, $style: normal) {
  @font-face {
    font-family: "#{$name}";
    src: local("#{$file}"),
         url('../fonts/#{$file}.woff2') format('woff2'),
         url('../fonts/#{$file}.woff') format('woff');
    font-weight: $weight;
    font-style: $style;
    font-display: swap;
  }
}
```

**Пример:**

```scss
@include font-face("Roboto", "roboto-regular", 400);
```

---

## 9. 🖼️ Фоновые изображения

```scss
@mixin bg ($size: "contain", $position: "center") {
  background-size: #{$size};
  background-position: #{$position};
  background-repeat: no-repeat;
}
```

**Пример:**

```scss
.icon {
  background-image: url('../img/icon.svg');
  @include bg("cover", "top left");
}
```

---

## 10. 🎮 Анимация кнопок

```scss
@mixin btn_anim($scaleMax: 1.05, $scaleMin: 0.95) {
  transform-origin: center center;
  transition: all ease-out 240ms;

  &:hover {
    transform: scale($scaleMax);
  }

  &:focus {
    outline: transparent;
  }

  &:focus-visible {
    transform: scale($scaleMax) translateY(-5%);
  }

  &:active {
    transform: scale($scaleMin);
  }
}
```

**Пример:**

```scss
.btn {
  @include btn_anim;
}
```

---

## 11. 🧼 Обнуление стилей кнопки

```scss
@mixin no-btn ($display: "inline-block") {
  padding: 0;
  margin: 0;
  border: 0;
  background-color: transparent;
  border-radius: 0;
  cursor: pointer;
  appearance: none;
  display: #{$display};
}
```

**Пример:**

```scss
.icon-btn {
  @include no-btn;
}
```

---

## 12. :fire: Для контейнеров

```scss
@mixin container($max-width:"120rem",$padding:"2rem"){
	width: 100%;
	max-width: #{$max-width};
	padding: 0 #{$padding};
	margin: 0 auto;
}
```
---

> 💡 **Совет:** вынеси все миксины в файл `_mixins.scss` и подключай его через `@import` или `@use`.

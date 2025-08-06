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

Пример использования:

```scss
.container {
  padding: 20px;
  @include respond(md) {
    padding: 10px;
  }
}
```

## 2. 🎯 Центрирование Flexbox'ом

```scss
@mixin flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

Пример:

```scss
.modal {
  @include flex-center;
}
```

## 3. ✂️ Обрезка текста (многоточие)

```scss
@mixin text-truncate {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
```

Пример:

```scss
.title {
  width: 200px;
  @include text-truncate;
}
```


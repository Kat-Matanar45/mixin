# mixin

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

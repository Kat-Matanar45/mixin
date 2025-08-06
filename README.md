# mixin

🔁 1. Media Queries (адаптивность)
scss
Копировать
Редактировать
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
Пример использования:

scss
Копировать
Редактировать
.container {
  padding: 20px;
  @include respond(md) {
    padding: 10px;
  }
}
📏 2. Центрирование Flexbox'ом
scss
Копировать
Редактировать
@mixin flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}
Пример:

scss
Копировать
Редактировать
.modal {
  @include flex-center;
}
📐 3. Обрезка текста (многоточие)
scss
Копировать
Редактировать
@mixin text-truncate {
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
Пример:

scss
Копировать
Редактировать
.title {
  width: 200px;
  @include text-truncate;
}
🔳 4. Размеры в одном миксине
scss
Копировать
Редактировать
@mixin size($width, $height: $width) {
  width: $width;
  height: $height;
}
Пример:

scss
Копировать
Редактировать
.avatar {
  @include size(50px); // ширина и высота по 50px
}
🟰 5. Псевдоэлементы (::before и ::after)
scss
Копировать
Редактировать
@mixin pseudo($display: block, $pos: absolute, $content: '') {
  content: $content;
  display: $display;
  position: $pos;
}
Пример:

scss
Копировать
Редактировать
.button::after {
  @include pseudo;
  background: red;
  width: 5px;
  height: 5px;
}
🌈 6. Градиентный фон
scss
Копировать
Редактировать
@mixin gradient($start, $end, $angle: 90deg) {
  background: linear-gradient($angle, $start, $end);
}
Пример:

scss
Копировать
Редактировать
.header {
  @include gradient(#ff8a00, #e52e71);
}
💡 7. Transition + customizable property
scss
Копировать
Редактировать
@mixin transition($props: all, $duration: 0.3s, $timing: ease) {
  transition: $props $duration $timing;
}
Пример:

scss
Копировать
Редактировать
.link {
  @include transition(color);
}

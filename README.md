# Видеоплеер

Готовый видеоплеер с кастомными элементами управления

## Особенности

- Автоматическое создание плеера после загрузки всех ресурсов
- Кастомизируемые элементы управления (кнопки, панель управления)
- Поддержка полноэкранного режима
- Управление громкостью и воспроизведением

## Как подключить

### 1. Подключение необходимых библиотек

Добавьте в ваш HTML-файл следующие скрипты и стили:

```html
<!-- Font Awesome для иконок -->
<link rel="stylesheet" href="font-awesome.min.css" />

<!-- jQuery -->
<script src="https://code.jquery.com/jquery-3.4.1.min.js"></script>

<!-- Playable библиотека -->
<script src="https://unpkg.com/playable@2.10.3/dist/statics/playable.bundle.min.js"></script>

<!-- Скрипт плеера -->
<script src="player.js"></script>
```

### 2. HTML разметка

Создайте контейнер для плеера с необходимой структурой:

```html
<div id="player" class="player">
  <!-- Контейнер для видео -->
  <div class="js-video-container video-container"></div>

  <!-- Панель управления -->
  <div class="controls-panel">
    <button class="js-play-button buttons">
      <i class="fa fa-play button" aria-hidden="true"></i>
    </button>
    <button class="js-pause-button buttons" hidden>
      <i class="fa fa-pause button" aria-hidden="true"></i>
    </button>
    <button class="js-volume-button buttons">
      <i class="fa fa-volume-up" aria-hidden="true"></i>
    </button>
    <button class="js-mute-button buttons" hidden>
      <i class="fa fa-volume-off" aria-hidden="true"></i>
    </button>
    <div style="flex-grow: 1"></div>
    <button class="js-fullscreen-button buttons">
      <i class="fa fa-expand" aria-hidden="true"></i>
    </button>
  </div>
</div>
```

### 3. Инициализация плеера

Добавьте скрипт инициализации после разметки:

```html
<script type="text/javascript">
  createPlayer({ elementId: "player" });
</script>
```

## Настройки

Размеры плеера
Размеры задаются через CSS класс .player:

```css
.player {
  width: 800px;
  height: 600px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 1);
}
```

## Изменение видео

По умолчанию используется тестовое видео. Чтобы изменить видео, укажите параметр src:

```javascript
createPlayer({
  elementId: "player",
  src: "https://example.com/your-video.mp4",
});
```

## Элементы управления

### Обязательные элементы

`js-video-container` — контейнер для видео. Обязателен для работы плеера.

### Кнопки управления

Все кнопки автоматически управляют своим состоянием (скрываются/показываются):

### 1. Воспроизведение/Пауза

`js-play-button` — кнопка воспроизведения (скрывается при активном воспроизведении)

`js-pause-button` — кнопка паузы (скрывается при остановке)

### 2. Управление звуком

`js-volume-button` — включение звука

`js-mute-button` — отключение звука

### 3. Полноэкранный режим

`js-fullscreen-button` — переход в полноэкранный режим

## Стилизация

Кнопки имеют класс `buttons` с базовыми стилями:

```css
.buttons {
  width: 40px;
  height: 40px;
  margin: 5px;
  font-size: large;
  color: white;
  border-style: none;
  cursor: pointer;
  background-color: transparent;
}
```

Панель управления имеет черный фон:

```css
.controls-panel {
  display: flex;
  background-color: black;
}
```

Полный пример
См. файл `index.html` для полного рабочего примера.

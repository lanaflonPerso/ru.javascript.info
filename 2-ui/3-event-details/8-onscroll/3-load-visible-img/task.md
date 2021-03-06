importance: 4

---

# Загрузка видимых изображений

Допустим, у нас есть клиент с низкой скоростью соединения, и мы хотим сэкономить его трафик.

Для этого мы решили не показывать изображения сразу, а заменять их на "макеты", как тут:

```html
<img *!*src="placeholder.svg"*/!* width="128" height="128" *!*data-src="real.jpg"*/!*>
```

То есть, изначально, все изображения -- `placeholder.svg`. Когда страница прокручивается до того положения, где пользователь может увидеть изображение -- мы меняем `src` на значение из `data-src`, и таким образом изображение загружается.

Вот пример в `iframe`:

[iframe src="solution"]

Прокрутите его, чтобы увидеть загрузку изображений "по требованию".

Требования:
- При загрузке страницы те изображения, которые уже видимы, должны загружаться сразу же, не ожидая прокрутки.
- Некоторые изображения могут быть обычными, без `data-src`. Код не должен касаться их.
- Если изображение один раз загрузилось, оно не должно больше перезагружаться при прокрутке.

P.S. Если можете, реализуйте более продвинутое решение, которое будет загружать изображения на одну страницу ниже/после текущей позиции.

P.P.S. Достаточно обрабатывать вертикальную прокрутку, горизонтальную не требуется.

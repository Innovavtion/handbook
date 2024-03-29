## SVG

Scalable Vector Graphics это разметка, основанная на XML, который содержит двумерные векторы. Векторами могут быть простые геометрические формы, сложные контуры, да и всё то же самое, что можно сделать в Иллюстраторе. Этот формат изображений имеет намного больше общего с веб-страницей, чем тот же JPEG. SVG намного мощнее — им легко можно управлять при помощи кода (в текстовом редакторе или с помощью CSS / JS).

**Приёмы для уменьшения размеров файла**:

- разбираясь подробнее с правильным удалением всего ненужного, мы можем сделать ещё кое-что в графическом редакторе. Сперва нужно убедиться, что используется настолько мало контуров/форм, насколько это возможно, так же как и точек на этих контурах. Можно объединять и упрощать всё, что поддаётся упрощению, и удалить все ненужные точки.
- Дальше будем увеличивать изображение. В Иллюстраторе удобно включить просмотр с пиксельной сеткой View > Pixel Preview и проверить, как располагаются контуры. Чтобы разместить контуры по сетке, потребуется немного времени, но эти усилия окупятся и позволят добиться более чёткого рендеринга (лучше обратить на это внимание заранее).
- И, наконец, последнее, но немаловажное, то, о чём обычно забывают — это активировать gzip сжатие SVG на вашем сайте в .htaccess файле.

**Варианты использования**:

- **Img** - Здесь всё делается так же, как с любым изображением в этом формате. Можно даже использовать SVG как элемент \<picture>. Но помните, что возможности преобразований в этом формате ограничены.
- **Background-image** Не стоит сохранять этот формат в base64, это приведёт к блокировке загрузки стилей. Помните, что возможности манипуляций в этом формате ограничены.
- **Iframe** Вы можете загрузить SVG как \<iframe>. Это позволит сделать многое, но я не уверен, что это лучший вариант использования, чтобы продвинуться вперёд.
- **Embed** \<embed> применяется «во внешних приложениях» или «в интерактивном контенте». Вы можете использовать это для SVG, но лучше не стоит.
- **Object** \<object> возможно лучший вариант, если вам нужно изменять SVG, не встраивая его в HTML.
- **Inline** Встраивание SVG в код не повлияет на HTTP-запрос, но изображение не будет кешироваться в браузере. Это самый простой способ управления, однако поддержка встроенного SVG кода может стать настоящим мучением.

**заключение**:
Если хочется выжать максимум из SVG, используйте \<object>. В качестве альтернативы подходит встроенный SVG, который не повлияет на HTTP-запрос, но не будет кешироваться. Если SVG выступает в роли обычного изображения, то подойдёт \<img> или background-image. Можно использовать \<iframe> и \<embed>, но я не думаю, что это лучшие варианты, и поэтому не буду больше заострять на них внимание.

---

[источник](https://svgontheweb.com/ru/#preparation)

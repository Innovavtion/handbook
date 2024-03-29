## Flexbox

#### Краткое объяснение:

**Flexbox расшифровывается как Flexible Box — гибкий ящик или блок.** Гибкость — основная идея этого способа. Читается как «флексбокс» или просто «флекс». Flexbox — один из двух современных методов построения **сеток** страницы.

**Сетка** — своеобразный каркас, который описывает, как расположены элементы. Благодаря ей веб-страницы выглядят понятно и аккуратно, а блоки не «плывут» вразнобой. Флексы используют для построения больших и малых сеток.

- **Большие, основные сетки** — это те, которые описывают положение крупных блоков. Например, это заголовки, текстовые блоки, боковые блоки со ссылками и виджетами и так далее.

- **Малые, микросетки** — это сетки внутри крупных блоков. Они описывают, как в них располагаются более маленькие элементы: ссылки, тексты, картинки и так далее.

Еще флексбокс применяется для других задач: выравнивания элементов, расположения их в списке, мелких дизайнерских исправлений и так далее.

#### С чего начать

**Создание контейнера** - **display: flex**;

#### flex-direction:

С помощью команды **flex-direction** можно **изменить направление оси**. У команды есть четыре значения:

- **row** — ряд, горизонтальная линия слева направо;
- **reverse-row** — ряд справа налево;
- **column** - колонка, вертикальная линия сверху вниз;
- **reverse-column** — колонка снизу вверх.

#### justify-content:

С помощью свойства **justify-content**, **выровнять контент**. По умолчанию они прижаты к левому или верхнему краю оси в зависимости от ее направления. Есть такие значения:

- **flex-start** или просто **start** — выравнивать по **«начальной точке»** оси, то есть по левому краю для row или по верхнему для column;
- **flex-end** или **end** — выстраивать по **«конечной точке»**, правой или нижней;
- **center** — концентрировать элементы в центре;
- **space-between** — прижимать крайние элементы к левому и правому краям, а элементы между ними распределять равномерно;
- **space-around** — то же самое, но с отступами от левого и правого края для крайних элементов. Каждый отступ от края в два раза меньше, чем отступы между элементами;
- **space-evenly** — то же самое, но отступы от краев такие же, как между элементами.

#### align-items:

**Выравнивать элементы**. Можно выстроить элементы не только вдоль оси, но и «поперек» нее: для row — по вертикали, для column — по горизонтали. Поведение описывается свойством **align-items**.

Его значения похожи на justify-content, но все же отличаются:

- **stretch** — элементы растягиваются поперек оси и заполняют все свободное пространство по обе стороны от нее;
- **start** — элементы сохраняют свой размер и выравниваются по верхнему или левому краю;
- **center** — элементы группируются по центру. Можно сказать, что их центральная часть «закреплена» на оси;
- **end** — элементы выравниваются по нижнему или правому краю;
- **baseline** — выравнивание происходит по «базовой линии» контента.

#### align-self:

Свойство **align-self** выравнивает флекс-элементы текущей строки, переписывая значение align-items. Если у какого-либо flex-элемента margin в поперечной оси выставлен в auto, то align-self игнорируется.

- **auto** - Берёт родительское значение align-items или stretch, если нет родителя;
- **flex-start** - Элемент выравнивается в начале поперечной оси контейнера;
- **flex-end** - Элемент выравнивается в конце поперечной оси контейнера;
- **center** - Элемент выравнивается по центральной линии на поперечной оси;
- **baseline** - Элемент выравнивается по базовой линии текста;
- **stretch** - Элемент растягивается таким образом, чтобы занять все свободное пространтсво контейнера по поперечной оси.

#### flex-basis:

Свойство **flex-basis** определяет основу флекса, которая является начальным размером элемента.

Похоже на свойства width и height, к которым добавляется содержимое элемента.

- auto - указывает автоматический размер, основанный на содержимом элемента.
- <ширина> - Задает ширину элемента в px, mm, pt или в процентах. При этом размер вычисляется относительно родителя. Отрицательное значение недопустимо.

#### flex-grow:

Свойство **flex-grow** определяет, сколько пространства может занимать флекс внутри контейнера.

В качестве значения принимаются числа, они задают пропорции каждого флекса. К примеру, если для всех элементов установлено значение 1, то они получатся равного размера. Если какой-то элемент получил значение 2, то его размер будет в два раза больше остальных.

- <число> - Применяется целые числа. Отрицательные значения игнорируются.

#### flex-shrink:

Свойство **flex-shrink** устанавливает коэффициент сжатия флексов в контейнере и задаёт, насколько элемент будет уменьшаться по отношению к другим флексам, чтобы разместить все элементы в одну строку.

- <число> - Принимаются целые числа. Отрицательные значения игнорируются.

---

[Официальная документация](https://www.w3.org/TR/css-flexbox-1/#flex-containers), [Краткая документация](https://tpverstak.ru/flex-cheatsheet/), [Неплохой справочник](https://hcdev.ru/css/).

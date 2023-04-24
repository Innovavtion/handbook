## Methodologies (Методологии)

[Habr](https://code.tutsplus.com/ru/tutorials/the-30-css-selectors-you-must-memorize--net-16048), [Triu](https://triu.ru/ponimanie-metodologii-napisaniya-css-hongkiat/)

**Методологии** - помогают создавать расширяемые,легко поддержываемые и повторно использумые компоненты интерфейса.

**Самые распространенные методологии**:

1. [**БЭМ**](https://ru.bem.info/methodology/css/ "ссылка на документацию") (Блок, Элемент, Модификатор)
2. [**ООCSS**](https://triu.ru/osnovy-obektno-orientirovannogo-css-oocss/ "можно почитать тут") (Объектно-ориентированный CSS)
3. [**SMACSS**](https://habr.com/ru/articles/256109/ "habr статья") (Масштабируемая и модульная архитектура для CSS)
4. [**ACSS**](https://habr.com/ru/articles/256109/ "habr статья") (атомарный CSS)

#### БЭМ - Блок, Элемент, Модификатор

**Блок** - это повторяющийся визуальный шаблон, который можно абстрагировать в независимый фрагмент HTML, CSS и возможно JavaScript.

**Элемент** - относится к компонентам блока (изображение, заголовок, текст и т.д).

**Модификатор** - используется, когда изменяется(модифицыруется) состояние блока или элемента.

#### ООCSS - Объектно-ориентированный CSS

По сути, CSS-объект - это повторяющийся визуальный шаблон, который можно абстрагировать в независимый фрагмент HTML, CSS и возможно JavaScript. Затем этот объект можно повторно использовать на всем сайте.

**Плюсы OOCSS**:
Многоразовые коды визуального оформления, гибкие коды местоположения, сокращение глубинных вложенных селекторов.

**Минусы OOCSS**:
Без достаточного количества повторяющихся визуальных шаблонов разделение структур и визуальных стилевых кодов кажется ненужным.

#### SMACSS

**Базовые стили** (Base rules) - это стили основных элементов сайта - body, input, button, ul, ol и т.п. В этой секции используются в основном селекторы тэгов и атрибутов, классы - в исключительных случаях(например, если у вас стилизованные JavaScript-ом селекты).

**Стили макета** (Layout rules) - здесь находятся стили глобальных элементов размеры шапки, футера, сайдбара и т.п.

**Стили модулей** (Modules rules) - стили модулей, то есть блоков, которые могут использоваться несколько раз на одной странице. Для классов модулей не рекомендуется использовать id и селекторы тэгов (для многократного использования и независимости от контекста соответственно).

**Стили состояния** (State rules) - в этом разделе прописываются различные состояния модулей и скелета сайта.

**Тема** (Theme rules) - здесь описываются стили оформлений, который со временем, возможно, нужно будет заменить (так удобно делать, например, новогоднее оформление; для html-тем, выставленных на продажу такие стили позволяют переключать цветовую гамму и т.п.).

#### ACSS

Atomic CSS, редко также ACSS — атомарный CSS. В некотором роде этот подход представляет собой OOCSS, возведенный в абсолют.

При использовании такого подхода для каждого повторно используемого свойства должен быть сформирован отдельный класс.

**Пример**: стиль «margin-top: 1px» предполагает создание класса «mt-1», стиль «width: 200px» создание класса «w-200».

Однако у этого подхода есть существенные недостатки! Вот они:

- наименования классов представляют собой описательные названия свойств, не описывая семантическую сущность элемента, что иногда может усложнить разработку;
- настройки отображения элементов переносятся непосредственно в HTML (это не то, для чего были придуманы таблицы стилей, не так ли?).
Landing page: Путешествие по России
-------------
### Задачи проекта
1. Верстка должна попиксельно совпадать с [макетом](https://www.figma.com/file/5S2WSbEFL6awjVWJ0NWL8Q/Sprint-3_-Russia-_-desktop-mobile?node-id=28503%3A0) дизайнера
2. Шрифты должны быть подключены локально
3. Изображения оптимизированы
4. Контент должен легко читаться спомощью скринридера
5. Именование классов и файловая структура реализованы в соответствии с БЭМ
6. Корректное изображение на экранах разных размеров

### Tехнологии
`HTML5`, `CSS3`, `CSS Flexbox`, `CSS Grid Layout`, `BEM Nested`

### Чему научил проект
1. Как оказалось при тестировании, родной браузер моего нового Vivo не поддерживает CSS Grid Layout. Блоки сверстанные на гридах развалились, а добавление префиксов решило проблему лишь частично. Если бы проект был призван продавать - это было бы проблемой. Решение - не использовать гриды для столь простого дизайна или использовать, но писать CSS фолбек с помощью дерективы @supports

### Сценарий реализации проекта
1. Собирем каркас страницы, используя семантичные теги и необходимые атрибуты, наполняем каркас контентом, расставляем в текстовых блоках неразрывные пробелы, проверяем через [валидатор](https://validator.w3.org/#validate_by_input), слушаем через скринридер, например для Windows - NVDA, по итогу правим ошибки.
2. Готовим файлы и структуру. Изображения оптимизируем через [Squoosh](https://squoosh.app/), добавляем в папку images, добавляем в разметку, убираем различия отображения элементов в разных браузерах - добавляем [normalize.css](https://necolas.github.io/normalize.css/) в папку vendor, добавляем исходники шрифтов в форматах .woff, .woff2 в папку fonts, подключаем шрифты, создаем папку blocks для блоков.
3. Проект был практически декомпозирован на первом этапе, доопределим что здесь блок, а что элемент. Дадим названия. Используем и флексы и гриды, подход desktop-first.
4. Настраиваем Live Server, PerfectPixel и пишем правила CSS
5. Реализуем адаптивность. Ориентируемся на 5 интервалов. 

### Можно улучшить
Контейнеризация.
1. Между секциями одинаковый отступ в 92px. Чтобы не писать каждому блоку margin, можно задать секции main display: grid; grid-row-gap: 92px;
2. Если мы не используем технологию CSS Grid, можно вынести внешнюю геометрию блока в элемент родительского блока. Например, body даём .page, div даём .page__container, header даём .page__header,  main даём .page__content и т.д. и прописываем нужные margin.
3. В макете мы видим чередование секций на всю ширину родителя и с отступом в 100px. Мы можем не писать дополнительный padding каждому блоку, а вынести разные ширины в элементы блока section. Например, .section .section_type_narrow. Этот же подход подойдет и для внешней геометрии - .section__geometry

Сверстанная работа https://marinasirenko-git.github.io/russian-travel/


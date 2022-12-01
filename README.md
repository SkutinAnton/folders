# Инструкции

- [Структура папки](#структура-папки)

## Структура папки

#### Зачем?
Позволяет правильно структурировать большие (по количеству файлов), так и сложные (по логике) компоненты/страницы/разделы. Делает их расширяемыми и предсказуемыми за счет копирования структуры проекта

#### Как?
Эта структура применяется когда у компонента появляется сложная логика которая выносится во вспомогательные функции (helpers, hooks и тд), когда создаются дополнительные вспомогательные компоненты, когда создаются целые страницы и разделы

<pre>
 <code>
  <b>component</b>
  |- <b>story</b>
  |-- Component.stories.jsx
  |-- mock.js
  |
  |- <b>common</b>
  |-- helpers
  |-- hooks
  |-- ...
  |
  |- <b>components</b>
  |-- core
  |-- block
  |-- ...
  |
  |- <b>entries</b>
  |-- <b>entry-1</b>
  |--- common
  |--- components
  |--- Entry-1.jsx
  |--- Entry-1.module.scss
  |--- index.js
  |
  |-- <b>entry-2</b>
  |--- Entry-2.jsx
  |--- Entry-2.module.scss
  |--- index.js
  |
  |- Component.jsx
  |- Component.module.scss
  |- index.js
 </code>
</pre>

### Основная вложенность (все папки являются опциональными):

- story - подключение компонента в storybook 
- common - общий переиспользуемый код (функции-помощники)
- components - общие переиспользуемые компоненты
- entries - точки входа (продукты, программы и тд)

#### Структура story:

В этой папке находятся файлы для подключения компонента в storybook

- Файл mock.js создается если для компонента нужны mock-данные (опционально)

<pre>
 <code>
  <b>story</b>
  |- Component.stories.jsx
  |- mock.js
 </code>
</pre>

#### Структура common:

В этой папке находятся общие функции-помощники такие как валидация, хуки, константы, миксины и тд.

- Может создаваться один файл в котором пишутся функции

<pre>
 <code>
  <b>common</b>
  |- helpers.js
  |- constants.js
  |- ...
 </code>
</pre>

- Может создаваться подпапка и внутри создаются функции

<pre>
 <code>
  <b>common</b>
  |- <b>helpers</b>
  |-- helper-1.js
  |-- helper-2.js
  |
  |- <b>constants</b>
  |-- constant-1.js
  |-- constant-2.js
  |- ...
 </code>
</pre>

#### Структура сomponents:

В этой папке находятся общие компоненты для текущего компонента

- Может создаваться папка для каждого компонента (для простых структур)

<pre>
 <code>
  <b>сomponents</b>
  |- <b>component-1</b>
  |-- Component-1.jsx
  |-- Component-1.module.scss
  |-- index.js
  |
  |- <b>component-2</b>
  |-- Component-2.jsx
  |-- Component-2.module.scss
  |-- index.js
  |- ...
 </code>
</pre>

- Может создаваться подпапка (по типу компонентов) в которой создаются компоненты (для более сложных структур)

<pre>
 <code>
  <b>сomponents</b>
  |- <b>core</b>
  |-- <b>core-component-1</b>
  |--- CoreComponent-1.jsx
  |--- CoreComponent-1.module.scss
  |--- index.js
  |
  |-- <b>core-component-2</b>
  |--- CoreComponent-2.jsx
  |--- CoreComponent-2.module.scss
  |--- index.js
  |
  |- <b>block</b>
  |-- <b>block-component-1</b>
  |--- BlockComponent-1.jsx
  |--- BlockComponent-1.module.scss
  |--- index.js
  |
  |-- <b>block-component-2</b>
  |--- BlockComponent-2.jsx
  |--- BlockComponent-2.module.scss
  |--- index.js
  |- ...
 </code>
</pre>

#### Структура entries:

В этой папке находятся компоненты которые являются точками входа (продукты, программы и тд)

- Может создаваться компонент без дополнительных папок **common** и **components** (для простых структур)

<pre>
 <code>
  <b>entries</b>
  |- <b>entry</b>
  |-- Entry.jsx
  |-- Entry.module.scss
  |-- index.js
  |- ...
 </code>
</pre>


- Может создаваться компонент с дополнительными папками **common** и **components** (для сложных структур)

<pre>
 <code>
  <b>entries</b>
  |- <b>entry</b>
  |-- <b>common</b>
  |-- <b>components</b>
  |-- Entry.jsx
  |-- Entry.module.scss
  |-- index.js
  |- ...
 </code>
</pre>

#### Исключения:

Эта документация описывает общие подходы к структуре папок. Будут встречаться моменты которые не будут подходить ни под одно правило и тогда они будут являться исключением. Такие моменты нужно обсуждать всем вместе для принятия правильной реализации.

#### Примеры в которых реализована структура:
- entries/full
- entries/digest

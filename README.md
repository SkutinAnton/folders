# Инструкции

- [Структура папки](#структура-папки)

## Структура папки

<pre>
 <code>
  <b>component</b>
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
  |-- entry-1
  |--- common
  |--- components
  |--- Entry.jsx
  |--- Entry.module.scss
  |--- index.js
  |
  |-- entry-2
  |
  |- Component.jsx
  |- Component.module.scss
  |- index.js
 </code>
</pre>

### Основная вложенность:

- common - общий переиспользуемый код (функции-помощники)
- components - общие переиспользуемые компоненты
- entries - точки входа (продукты, программы и тд)

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

- Может создаваться подпапка если есть вложенность и внутри создаются функции (приоритетнее)
<pre>
 <code>
  <b>common</b>
  |- helpers
  |-- helper-1.js
  |-- helper-2.js
  |-- ...
  |- constants
  |-- constant-1.js
  |-- constant-2.js
  |- ...
 </code>
</pre>

#### Структура сomponents:

В этой папке находятся общие компоненты для текущего компонента (для простых структур)

- Может создаваться папка компонента
<pre>
 <code>
  <b>сomponents</b>
  |- component-1
  |-- Component-1.jsx
  |-- Component-1.module.scss
  |-- index.js
  |
  |- component-2
  |-- Component-2.jsx
  |-- Component-2.module.scss
  |-- index.js
  |- ...
 </code>
</pre>

- Может создаваться подпапка (по типу) в которой создаются компоненты (для более сложных структур)
<pre>
 <code>
  <b>сomponents</b>
  |- core
  |-- core-component-1
  |--- CoreComponent-1.jsx
  |--- CoreComponent-1.module.scss
  |--- index.js
  |
  |-- core-component-2
  |--- CoreComponent-2.jsx
  |--- CoreComponent-2.module.scss
  |--- index.js
  |
  |- block
  |-- block-component-1
  |--- BlockComponent-1.jsx
  |--- BlockComponent-1.module.scss
  |--- index.js
  |
  |-- block-component-2
  |--- BlockComponent-2.jsx
  |--- BlockComponent-2.module.scss
  |--- index.js
  |- ...
 </code>
</pre>

#### Структура entries:
Эта папка опциональная. Она может быть если есть несколько точек входа (продукты, программы и тд), а не один через основной компонент

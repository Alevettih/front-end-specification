# Front-end development specification

> Feel free to create pull requests to add content. Open issues to discuss ideas, or get clarification.

## Для чего это нужно?

> We should be on the same page

Чтобы front-end отдел превратился во front-endman-а.

### Кто такой front-endman?

Он скрывается во front-end отделе.

Он не совершает ошибок, его код всегда идеален.

Он следует лучшим стандартам и использует лучшие практики.

Он может работает с любыми технологиями.
В то же время он не распыляется благодаря тому, что он состоит из множества частей
и каждая его часть знает свою технологию на столько хорошо, что может написать книгу.

Он [SuperDRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself). Все, что он сделал один раз
в следующий сделает в три раза быстрее.

Он знает все героические [принципы](https://www.artima.com/weblogs/viewpost.jsp?thread=331531).

### Основные принципы

Основные принципы front-endman-а это:

#### [Reusability](https://en.wikipedia.org/wiki/Reusability)

Разработка ведется с помощью модулей, которые можно скачать из каталога,
если в каталоге еще нет нужного вам модуля, то он разрабатывается с расчетом на
то, чтобы добавить его в каталог для использования в будущем.

Описание модульного принципа смотри [тут](#modules)

#### [Automation](https://en.wikipedia.org/wiki/Automation)

> Все, ... автоматизировать, ... автоматизировать.

Тестирование, развертывание проекта, [настройка ОС](https://github.com/vlad-yaremenko/dotfiles), приготовление кофе,
должно быть максимально быстрым и требовать минимальных телодвижений со стороны разработчика.

### Front-endman required knowledge

- [Intermediate english level](https://tracktest.eu/english-levels-cefr/)
- [HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5), [CSS3](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS3), [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript), [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)
- [Responsive Web](https://developers.google.com/search/mobile-sites/mobile-seo/responsive-design), [SCSS](https://sass-lang.com/), [BEM](https://en.bem.info/methodology/)
- [Git](https://git-scm.com/)
- [HTTP(S)](https://en.wikipedia.org/wiki/HTTPS), [RESTful APIs](https://en.wikipedia.org/wiki/Representational_state_transfer), [SSH](https://www.ssh.com/ssh/)
- [NPM](https://www.npmjs.com/), [Webpack](https://webpack.js.org/), [Gulp](https://gulpjs.com/)
- [ES6](https://github.com/lukehoban/es6features), [TypeScript](http://www.typescriptlang.org/)
- [Basic terminal usage](https://maker.pro/education/basic-linux-commands-for-beginners), Personal text editor (WebStorm, Vim, Sublime Text, etc.)
- [Test automation](https://en.wikipedia.org/wiki/Test_automation)
- [Data structures](https://en.wikipedia.org/wiki/Data_structure) & [Algorithms](https://en.wikipedia.org/wiki/Algorithm)
- [GOF Design patterns](https://en.wikipedia.org/wiki/Design_Patterns), [Architectural patterns](https://web.archive.org/web/20120623081009/http://aahninfotech.com/arct_pattern.html)
- [Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
- [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)), [YAGNI](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it), [KISS](https://en.wikipedia.org/wiki/KISS_principle) etc

Тут [больше](https://codeburst.io/the-2018-web-developer-roadmap-826b1b806e8d)

### Personal qualities

- Концентрация. Он изучает выбранную тему до конца. Он не умеет все и сразу.
- Для фиксации прогресса он пишет статью на изученную тему и делится ей с обществом.
- Он может признать свои проблемы. У него есть список проблем и он стремительно идёт к их устранению.

## Architecture

Создание архитектуры ведётся в [draw.io](https://www.draw.io/)

На планирование архитектуры в обязательном порядке выделяется **от 8-ми часов**.

### Stages

При разработке архитектуры нужно:

- Выбрать стек технологий
- Разбить проект на отдельные модули
- Описать работу сервисов
- Продумать взаимодействие между сервисами и модулями

### Rules

При написании модуля избегать **сильной привязки к окружению**.

**Работу с сервисами выносить в корневые модули страниц**. Исключать вызовы сервисов в компонентах (input, select, dropdown).

Все строковые значения (url, идентификаторы) **выносить в constants**.

Любые функции общего назначения (форматирование даты, подготовка данных) **выноситься в helper**.

**Get** методы и функции должны **возвращать значение**.

## README

Все проекты сопровождаются [README.md](/files/README.md) файлом в котором описаны:

- Название проекта
- Короткое описание
- Homepage
- Ссылку на систему баг трекинга
- Инструкция по установке зависимостей и настройке окружения
- Команды для:
  - Старта разработки. Запуск watch-еров
  - Сборки
  - Запуска тестов
- Указаны основные технологии
- Указаны поддержка браузеров

## Browsers support

Если заказчик не определил поддержку браузеров, то по умолчанию мы поддерживаем:

![Chrome](https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome\_48x48.png) | ![Firefox](https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox\_48x48.png) |![Edge](https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge\_48x48.png) | ![Opera](https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera\_48x48.png) | ![Safari](https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png)
---      | ---      | ---      | ---      | ---      |
Last 2 ✔ | Last 2 ✔ | Last 2 ✔ | Last 2 ✔ | Last 2 ✔ |

## Base setup

### .files

- [.gitignore](files/.gitignore.example)
- [.*lint](#code-linting)
- [.browserslistrc](files/.browserslistrc) - файл конфига для [Browsers list](https://github.com/browserslist/browserslist)
- .env - Описывает переменные окружения для node.js проектов
- .babelrc
- [.editorconfig](files/.editorconfig) - Синхронизирует настройки редакторов. Hужно установить [плагин](http://editorconfig.org/#download) для своего редактора, если его нет.

### Package.json

package.json находится в корневой директории и является стартовой точкой проекта.

Для линтинга кода package.json имеет несколько обязательных dev-зависимостей.

#### Project

```json
{
  "name": "project-name",
  "version": "0.0.1",
  "scripts": {
    "start": "Start development process",
    "publish": "Create build for production",
    "test": "Run tests (unit, lint, ...)",
    "stylelint": "stylelint \"**/*.scss\" --syntax scss"
  },
  "dependencies": {
    "name": "version"
  },
  "devDependencies": {
    "name": "version"
  },
  "browserslist": [
    "> 2% and Last 2 versions and not ie 11",
    "not ie_mob <= 11",
    "not op_mini all",
    "not dead"
  ]
}
```

Тут больше [package.json](https://docs.npmjs.com/files/package.json)

## Markup

Для разметки страницы используется HTML5.

## Styles

Для написания стилей используется [шаблонизатор SCSS](https://sass-lang.com/)

Для поддержания code style подключается [файл](/files/.stylelintrc) конфигураций [StyleLint](https://stylelint.io/)

Настройки StyleLint формируются из [правил StyleLint](https://stylelint.io/user-guide/rules/)
и дополнительных плагинов:

- [stylelint config standard](https://github.com/stylelint/stylelint-config-standard) - основа для правил StyleLint
- [stylelint-scss](https://github.com/kristerkari/stylelint-scss#list-of-rules) - правила для линтинга .scss файлов
- [stylelint-no-unsupported-browser-features](https://github.com/ismay/stylelint-no-unsupported-browser-features) - проверяет поддержку браузером написанных правил
- [stylelint-z-index-value-constraint](https://github.com/kristerkari/stylelint-z-index-value-constraint) - позволяет установить максимальное и минимальное значение для z-index
- [stylelint-declaration-strict-value](https://github.com/AndyOGo/stylelint-declaration-strict-value) - плагин, добавляющий правило согласно которому необходимо определённые свойства (цвета, шрифты, z-index) указывать только через переменные

Для запуска StyleLint необходимо установить зависимости

```bash
# Install dependencies
npm i -D stylelint stylelint-config-standard stylelint-no-unsupported-browser-features stylelint-scss stylelint-z-index-value-constraint stylelint-declaration-strict-value

# Run linting
stylelint ./path/to/styles/*.scss --syntax scss
```

### Methodologies

При разработке стилей используется [BEM](http://getbem.com/) методология.

## JavaScript

### ES6+ (base rules)

Код должен соответствовать требованием [Airbnb](https://github.com/airbnb/javascript).

В каждый проект, для избежания элементарных ошибок, подключается [конфигурационный](/files/.eslintrc) файл [ESLint](https://eslint.org/).

В ESLint конфиг подключаеются дополнительные модули:

- [eslint-config-airbnb-base](https://www.npmjs.com/package/eslint-config-airbnb-base) - правила eslint по стандарту airbnb
- [babel-eslint](https://github.com/babel/babel-eslint) - babel парсер для eslint
- [eslint-plugin-compat](https://github.com/amilajack/eslint-plugin-compat) - проверяет поддержку браузером

Для запуска ESLint необходимо установить зависимости

```bash
# Install dependencies
npm i -D eslint eslint-config-airbnb-base babel-eslint eslint-plugin-compat

# Run linting
./node_modules/.bin/eslint ./path/to/scripts/*.js
```

### React

React приложения соответствуют всем правилам [ES6+](#es6-base-rules) приложений. Также необходим установить
зависимости для линтинга React приложений:

- [eslint-plugin-react](https://www.npmjs.com/package/eslint-plugin-react) - Плагин с правилами
  ESLint для приложений на React

```bash
npm i -D eslint-plugin-react
```

В проекте используется [файл](/files/react/.eslintrc) конфигураций ESLint для React приложений.

### Angular

Полезности для упрощения жизни на Angular проекте можно найти [здесь](/files/angular/README.md)

### Additional code style conventions

Также желательно использовать дополнительные соглашения по стилю кода, принятые внутри компании. Смотри [здесь](/files/code-style-addons/README.md)

## Development process

### Code linting

Подключенные *Lint файлы будут делать невозможным билд/коммит проекта без соблюдения их правил.

#### *Lint files list

- [ESLint](/files/.eslintrc)
- [React ESLint](/files/react/.eslintrc)
- [StyleLint](/files/.stylelintrc)
- TSLint

### [Git-hooks](/files/hooks/README.md)

Правильно подключенные git-hooks сделают невозможным  коммиты/выливку проекта  без прохождения предварительно установленных вами тестов. В простой установке git-hooks нам поможет [husky](https://github.com/typicode/husky), по ссылке есть более подробное описание, как можно его использовать.

> npm install husky --save-dev

Дописываем необходимые команды в наш package.json

```json
{
  "name": "project-name",
  "version": "0.0.1",
  "scripts": {
    "start": "Start development process",
    "publish": "Create build for production",
    "eslint": "./node_modules/.bin/eslint ./path/to/scripts/*.js",
    "stylelint": "stylelint ./path/to/styles/*.scss --syntax scss",
    "lint": "npm run eslint && npm run stylelint",
    "test": "jest"
  },
  "husky":{
    "hooks": {
      "pre-commit": "npm run lint",
      "pre-push": "npm run lint && npm test"
    }
  }
}
```

Дополнительная информация по ссылке в заголовке
### TODO

Все изменения, которые нужно внести в код или реализовать, должны быть описаны в TODO комментариях, в тех местах, где нужно реализовать функционал или внести изменения.

Это делается для того, чтобы не держать в голове все изменения и дать другим разработчикам понимание того, что нужно изменить или не трогать.

При продакшн сборке все TODO комментарии удаляются.

### Comments

Избегайте бессмысленного комментирования кода, имена переменных и функций должны говорить сами за себя.

Comments – Do not write comments for what you are doing, instead write comments on why you are doing.
Specify about any hacks, workaround and temporary fixes. Additionally, mention pending tasks
in your to-do comments, which can be tracked easily.

При продакшн сборке все комментарии удаляются.

### Branch flow

> Please make short pull requests. Save your code reviwer

#### Main branches

Во время инициализации проекта создаются основные ветки. С бесконечным жизненным циклом.

**dev** - содержит самую последнюю версию.

**master** - содержит версию с текущим релизом.

Ветки **master** и **dev** могут изменяться только посредством merge request.

Всё что попадает в ветку **dev** отправляется (в идеале при помощи CI/CD) на тестовый сервер.

То же самое и с веткой **master** - всё что в неё попадает отправляется на стейджинг сервер.

Тегирование **master** означает его выливку на прод сервер.

#### Feature branch

Для каждого таска или баг фикса создается **feature** или **bugfix** ветка от **master** или **dev** ветки, в зависимости от того какую кодовую базу необходимо расширить/пофиксить.

В название ветки должно входить тип задачи, краткое (не более трёх слов), разделяемое дефисами, описание и номер задачи, отделённый через нижнее прдчёркивание.

```
$ git checkout -b [task-type]/[task-name]_[task#] dev
```

Например для Jira:
```
bugfix/test-task_TP1
feature/test-task_TP1
```
Для WorkSection:
```
bugfix/test-task_0000001
feature/test-task_0000001
```


**Feature** ветка должна сливаться с **master** или **dev** веткой через merge request.

**Feature** ветку нужно назвать `feature/[name]_[task#]`. Для **Feature** веток запрещены следующие имена `bugfix/*`, `master`, `dev`.

**Bugfix** ветку нужно назвать `bugfix/[name]_[task#]`.

[Read me](https://guides.github.com/introduction/flow/)

#### Commit Messages

При коммите, в сообщении, указывается тип задачи, заголовок задачи и ссылка на неё.
Если выполнена только часть работ по таску - добавить краткое описание выполненной работы.

Например:

```
Feature: Task name.
Task ref: [task#](https://projects.requestum.com/project/0000001/task#)

A short description of the work performed as part of the task.
```
P.S. - Bash сам поставит перенос строки при нажатии на `enter` если не закрыты кавычки `'` или `"`

### Code review

Первое, что должен проверить ревьювер - работает ли функционал так, как должен.

#### Основные задачи code review

- Распространить знания по команде
- Научиться думать, как остальные члены команды
- Повысить качество и поддерживаемость кода

#### Все, что можно автоматизировать, должно быть автоматизированно

Отлов ошибок нужно предоставить тестам

Следование code style-у должен проверять *lint-ер. Это повысит читаемость кода и упростит его
поддержку.

#### Ревьювер

> Find problems, Not solutions

Важно искать возможные проблемы в решении, а не стараться максимально оптимизировать код (если
это не является целью). Если решение уж очень плохое, сообщить автору об этом, понять как он к этому
пришел и помочь найти другое решение.

Code review - high priority task.

**Максимальное** время на ревью **1 час**. Далее код отправляется на доработку или принимается

Не просматривай более 500 строк кода за раз

Если что-то копируется больше 2-х раз, это может быть копипастом

##### Проверь:

- Работает ли функционал так как описано в требованиях
- Maintainability
  - Читается ли код как проза
  - Нарушения семантики - делает ли класс/метод то что написано в его названии
- Тестируемость
- Логические ошибки
- Архитектурные ошибки
- Возможности для упрощения, использования паттернов.
- Idiomatic - используются ли все возможности языка, фреймворка
- Использование плохих практик
- Team code convention
- No hard coding, use constants/configuration values
- Зависимости между классами/компонентами/модулями. Везде ли они нужны?
- Reliability - отлов исключений
- Security
  - Are all data inputs checked (for the correct type, length, format, and range) and encoded?
  - Where third-party utilities are used, are returning errors being caught?
  - Are output values checked and encoded?
  - Are invalid parameter values handled?
- Performance
- Usability & User experience

#### Author, please

> Don't make me think

Одна цель - один коммит

Title - коротко описывает функционал.

Description - описывает что было изменённо, на что нужно обратить внимание. Содержит описание таска.

**Не squash коммиты до окончания ревью**

**Делай code review самостоятельно перед коммитом** (просматривай `git diff`)

Постарайтесь ответить на каждый комментарий

Merge request должен содержать не более 400 строк кода

Удаляйте закомментированный код. Его можно легко восстановить с помощью VCS.

#### Feedback mechanism

Используйте комментарии в merge request. По окончанию code review сообщите от этому автору в личном сообщении.

Instead of explaining the entire solution to developers during the code review process, simply
share the links of relevant websites or encourage them to research on the
internet by providing keywords.

[Read me](https://medium.com/@palantir/code-review-best-practices-19e02780015f)

### Testing

На этапе оценки проекта **важно** включить минимум 30% тестирования основного функционала.

Наличие или отсутствие тестов может зависеть от пожеланий заказчика.

#### [Theoretical basis for testing](/files/tests/THEORETICAL_BASIS.md)

#### BrowserStack

Для тестирования кроссбраузерности используется BrowserStack.

Для работы с ним нужно установить [chrome extension](https://chrome.google.com/webstore/detail/browsersync/odccdjehkinjebnjnkpbjeplabccchfe),
прописать в настройках расширения `https://www.browserstack.com/`

![Browsersync options](https://i.imgur.com/RCZzT84.png)

и зайти в общий [BrowserStack](https://www.browserstack.com/).

В случае, если BrowserStack занят, страница будет заблокирована, пока BrowserStack не освободится.

Все пожелания по расширению оставляем [тут](https://github.com/vlad-yaremenko/browsersync-extension/issues)

### Good breeding

#### Pre-development process

- [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) check

#### UI

При разработке UI делается акцент на качество UX.
Вот некоторые примеры хорошего UX:

- Закрывать попапы по нажатию esc
- Возможность ходить по всем элементам управления с помощью tab
- Возможность управления стрелочками в селекте
- Реакция на focus
- Активная ссылка не должна нажиматься дважды
- Вывод сообщений об ошибке

У нас [тут больше](http://bfy.tw/Gt9G)

#### Forms handling

Смотри [здесь](/files/forms/README.md)

### Modules

TODO: Describe modules principle

## Issues

Suggestions/improvements [welcome](https://github.com/vlad-yaremenko/front-end-specification/issues)!

## Task list

Task list for implementation [here](https://trello.com/b/cxAOrkGn)

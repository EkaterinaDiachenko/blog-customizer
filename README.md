# Blog Customizer

**Blog Customizer** — приложение для настройки оформления статьи. Выбирайте шрифт, цвета и ширину контента в боковой панели, применяйте изменения и подбирайте удобный для чтения вариант.

## Технологический стек:

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![SCSS](https://img.shields.io/badge/SCSS-CC6699?style=for-the-badge&logo=sass&logoColor=white)
![CSS Modules](https://img.shields.io/badge/CSS_Modules-1572B6?style=for-the-badge&logo=cssmodules&logoColor=white)
![Webpack](https://img.shields.io/badge/Webpack-2B3A42?style=for-the-badge&logo=webpack&logoColor=8DD6F9)

### Компоненты и инструменты разработки

![Storybook](https://img.shields.io/badge/Storybook-FF4785?style=for-the-badge&logo=storybook&logoColor=white)
![ESLint](https://img.shields.io/badge/ESLint-4B32C3?style=for-the-badge&logo=eslint&logoColor=white)
![Stylelint](https://img.shields.io/badge/Stylelint-263238?style=for-the-badge&logo=stylelint&logoColor=white)
![Prettier](https://img.shields.io/badge/Prettier-F7B93E?style=for-the-badge&logo=prettier&logoColor=black)

Компоненты представлены в Storybook. ESLint и Stylelint проверяют код и стили, Prettier отвечает за форматирование.

## Основной функционал
- Боковая панель настроек с открытием по кнопке и закрытием по клику вне панели.
- Выбор типа, размера и цвета шрифта.
- Изменение цвета фона и ширины контента.
- Применение выбранного оформления по кнопке «Применить».
- Возврат формы и статьи к исходным настройкам по кнопке «Сбросить».

## Реализация:
- Интерфейс разделён на статью, форму настроек и переиспользуемые UI-компоненты.
- Настройки формы и применённое оформление хранятся отдельно через `useState`.
- Форма передаёт выбранные значения в корневой компонент через callback-функции.
- Оформление статьи обновляется с помощью CSS-переменных.
- Закрытие панели по внешнему клику вынесено в отдельный хук.
- Варианты оформления, начальные значения и типы настроек собраны в `articleProps.ts`.


<details>
<summary><h2>Структура проекта</h2></summary>

```text
blog-customizer/
├── src/
│   ├── components/
│   │   ├── app/                 # Состояние и применение оформления
│   │   ├── article/             # Статья
│   │   └── article-params-form/ # Боковая панель с формой настроек
│   ├── constants/               # Варианты оформления и типы настроек
│   ├── fonts/                   # Локальные шрифты и их подключение
│   ├── styles/                  # Общие стили
│   ├── ui/                      # Кнопки, списки и другие UI-компоненты
│   └── index.tsx                # Точка входа приложения
├── public/                      # HTML-шаблон
├── webpack/                     # Настройки разработки и сборки
├── .storybook/                  # Настройки Storybook
├── postcss.config.js            # Обработка CSS
├── tsconfig.json                # Настройки TypeScript
├── package.json                 # Зависимости и команды
└── README.md                    # Документация проекта
```

</details>

## Запуск

1. В каталоге проекта установите зависимости:

```bash
npm ci
```

2. Запустите приложение:

```bash
npm start
```

## Полезные команды

| Команда | Назначение |
| --- | --- |
| `npm start` | запуск сервера разработки |
| `npm run build` | сборка приложения в каталог `dist` |
| `npm run storybook` | запуск Storybook на порту 6006 |
| `npm run build-storybook` | сборка Storybook |
| `npm run stylelint` | проверка SCSS-стилей |
| `npm run stylelint:fix` | автоматическое исправление ошибок в стилях |
| `npm run lint` | проверка и автоматическое исправление кода |
| `npm run format` | форматирование исходных файлов |
| `npm test` | последовательный запуск исправления стилей, линтера и форматирования |

В этом проекте `npm test` запускает инструменты качества кода и изменяет файлы, а не выполняет модульные или браузерные тесты.

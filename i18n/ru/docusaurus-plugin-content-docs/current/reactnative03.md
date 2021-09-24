---
id: reactnative03
title: Props - параметры
sidebar_label: Props - параметры
---

import YouTube from 'react-youtube'

Большинство компонентов можно настроить при их создании с различными параметрами. Эти параметры создания называются - `props`.

Ваши собственные компоненты также могут использовать `props`. Это позволяет вам создать один компонент, который будет использоваться во многих разных местах вашего приложения, с немного разными свойствами в каждом месте. Чтобы получить их значения, обратитесь к `props.YOUR_PROP_NAME` в ваших функциональных компонентах или `this.props.YOUR_PROP_NAME` в ваших компонентах класса. Вот пример:

```SnackPlayer name=index.js
import * as React from 'react'
import { Text } from 'react-native'

const HelloWorld = (props) => (
  <Text>Hello {props.name}!</Text>
)

const App = () => (
  <>
    <HelloWorld name='Luk' />
    <HelloWorld name='John' />
    <HelloWorld name='Ivan' />
  </>
)

export default App
```

Использование `name` в качестве `props` позволяет нам настроить компонент приветствия, чтобы мы могли повторно использовать этот компонент для каждого из наших приветствий. В этом примере также используется компонент `HelloWorld` в JSX. Способность делать это - вот что делает React таким крутым.

<!-- ### Только для чтения

Компонент, объявленный как функция или класс, никогда не должен модифицировать свои свойства `props`. Рассмотрим эту `sum` функцию:

```jsx
const sum = (a, b) => a + b
```

Такие функции называются "чистыми". Потому что они не изменяют свои аргументы и всегда возвращают одинаковый результат для одних и тех же аргументов.

В противоположность им, следующая функция не является чистой, потому что она изменяет свои аргументы:

```jsx
const count => (account, amount) => account += amount
```

React является очень гибким, но он имеет одно строгое правило:

:::tip
Все React-компоненты должны работать как чистые функции в отношении своих свойств `props`.
:::


## Проблемы?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

Пишите в [Discord](https://discord.gg/6GDAfXn) или телеграмм [чат](https://t.me/jscampapp), а также подписывайтесь на наши [новости](https://t.me/javascriptapp)

 

## Вопросы

Как называются параметры создания компонента?

1. `prop`
2. `props`

Компонент, объявленный как функция или класс, никогда не должен модифицировать свои свойства `props`?

1. `true`
2. `false`

Все React-компоненты должны работать как чистые функции в отношении своих свойств `props`?

1. `true`
2. `false`

## Done ✅

Чтобы узнать, насколько хорошо вы усвоили этот урок, пройдите тест в [мобильном приложении](http://onelink.to/njhc95) нашей школы по этой теме или в [боте Telegram](https://t.me/javascriptcamp_bot).

![Sumerian school](/img/app.jpg)

## Ссылки:

1. [React Native - official website](https://reactnative.dev/docs/tutorial)
2. [Learn React](https://learn-reactjs.ru/basics/components-and-props) -->


## Оплата

Сейчас ты находишся на урезанной версии сайта, после оформления подписки на [Patreon](https://www.patreon.com/javascriptcamp), ты получишь полный доступ к обучающему курсу, а также доступ к серетным каналам нашего сервера в [Discord](https://discord.gg/6GDAfXn).  

Качай наше [мобильное приложение](http://onelink.to/njhc95) или пройди тестирование в нашем [JavaScript телеграм боте](https://t.me/javascriptcamp_bot), а также подпишись на [наши новости](https://t.me/javascriptapp).

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)


[![Sumerian school](/img/app.jpg)](http://onelink.to/njhc95)

 

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):


<table>
  <tr>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /><a href="#financial-gHashTag" title="Financial">📖 💵</a></td>
  </tr>
</table>


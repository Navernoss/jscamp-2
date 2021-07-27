---
id: javascript19
title: सरणी पुनरावृत्ति विधियाँ (map, filter, reduce)
sidebar_label: सरणी पुनरावृत्ति विधियाँ (map, filter, reduce)
---

![@serverSerrverlesskiy](/img/javascript/headers/22.jpg)

भाषा👅 JavaScript अन्य डेटा संरचनाओं पर सरणियों के लिए एक स्पष्ट प्राथमिकता है। उनके पास बहुत सी सुविधाजनक विशिष्ट तरकीबें हैं, उदाहरण के लिए, पुनरावृत्ति विधियों का एक पूरा सेट: `map`, `filter`, `reduce`.

## map

![Create](https://media.giphy.com/media/ffd0F6WNcRJMQ/giphy.gif)

तरीका `map()` बनाता है🏗️ नया🆕 निर्दिष्ट फ़ंक्शन को कॉल करने के परिणाम के साथ एक सरणी⚙️ सरणी के प्रत्येक तत्व के लिए।

### वाक्य - विन्यास

![Book](https://media.giphy.com/media/s6OiiampNcye4/giphy.gif)

```javascript
let new_array = arr.map(function callback( currentValue[, index[, array]]) {
    // के लिए आइटम लौटाता है new_array
}[, thisArg])
```

तरीका `map` पारित फ़ंक्शन को कॉल करें⚙️ `callback` प्रत्येक तत्व के लिए एक बार, जिस क्रम में वे प्रकट होते हैं, और निर्माण करते हैं 🆕 इसे कॉल करने के परिणामों से एक नई सरणी। समारोह⚙️ `callback` केवल उन सरणी सूचकांकों के लिए कहा जाता है जिनमें मान असाइन किए गए हैं, जिनमें शामिल हैं `undefined`. इसे लापता सरणी तत्वों के लिए नहीं कहा जाता है (अर्थात, उन सूचकांकों के लिए जिन्हें कभी निर्दिष्ट नहीं किया गया था, हटा दिया गया था, या कभी कोई मान नहीं दिया गया था)।

समारोह⚙️ `callback` तीन तर्कों के साथ बुलाया गया:

- तत्व का मान,
- तत्व सूचकांक
- और वह सरणी जिसके माध्यम से पारित किया जाता है।

यदि विधि में `map` पैरामीटर पारित किया गया था `thisArg`, कॉल करते समय `callback` यह एक मूल्य के रूप में इस्तेमाल किया जाएगा `this`. अन्यथा, मान के रूप में `this` मूल्य का उपयोग किया जाएगा `undefined`. अंतत: अर्थ `this`, समारोह से देखने योग्य⚙️ `callback`, निर्धारित करने के लिए सामान्य नियमों के अनुसार निर्धारित `this`, समारोह से दृश्यमान⚙️.

तरीका `map` उस सरणी को नहीं बदलता है जिसके लिए इसे बुलाया गया था (हालांकि फ़ंक्शन⚙️ यह कर सकते हैं!)।

विधि द्वारा संसाधित तत्वों की श्रेणी `map`, फ़ंक्शन के पहले कॉल से पहले सेट करें⚙️ `callback`. विधि निष्पादित होने के बाद सरणी में जोड़े गए आइटम `map`, не будут посещены समारोह⚙️ `callback`. यदि सरणी के मौजूदा तत्वों को फ़ंक्शन द्वारा बदल दिया जाता है⚙️ `callback`, उनके मान फ़ंक्शन को दिए गए⚙️ उस समय के मान होंगे जब विधि `map` उनका दौरा करेंगे। हटाए गए आइटम का दौरा नहीं किया जाएगा।

### उदाहरण:

![Math](https://media.giphy.com/media/xT1Ra5h24Eliux3UVq/giphy.gif)

#### सरल उदाहरण

आपके पास कई वस्तुओं की एक सरणी है, प्रत्येक एक अलग व्यक्ति का प्रतिनिधित्व करता है👨. यहां बहुत सारा डेटा हो सकता है: सिनेमा से नाम, उम्र, बालों का रंग और पसंदीदा चरित्र, लेकिन फिलहाल यह सब आवश्यक नहीं है - आप उन्हें देने के लिए केवल इन लोगों के पासपोर्ट नंबरों की एक सरणी प्राप्त करना चाहते हैं सभी सम्मेलन पास।

```jsx live
function learnJavaScript() {
  const friends = [
    { passport: '03005988', name: 'Joseph Francis Tribbiani Jr', age: 32, sex: 'm' },
    { passport: '03005989', name: 'Chandler Muriel Bing', age: 33, sex: 'm' },
    { passport: '03005990', name: 'Ross Eustace Geller', age: 33, sex: 'm' },
    { passport: '03005991', name: 'Rachel Karen Green', age: 31, sex: 'f' },
    { passport: '03005992', name: 'Monica Geller', age: 31, sex: 'f' },
    { passport: '03005993', name: 'Phoebe Buffay', age: 34, sex: 'f' }
  ]
  let passports = friends.map(friend => friend.passport + ' ')
  return passports
}
```

#### कुछ मामलों में, आपको स्ट्रिंग के रूप में चयनित कुंजियों के साथ ऑब्जेक्ट्स की एक सरणी प्रदर्शित करने की आवश्यकता हो सकती है 👇 :

```jsx live
function learnJavaScript() {
  const users = [
    { id: 11, name: 'Adam', age: 23, group: 'editor' },
    { id: 47, name: 'John', age: 28, group: 'admin' },
    { id: 85, name: 'William', age: 34, group: 'editor' },
    { id: 97, name: 'Oliver', age: 28, group: 'admin' }
  ]

  let result = users.map(({ id, age, group }) => `\n${id} ${age} ${group}`).join('')

  return result
}
```

#### सेल्सियस मानों की एक सरणी से फ़ारेनहाइट मानों की एक सरणी बनाना:

![Thermometer](https://media.giphy.com/media/W23dJLsAW5knUU27Fv/giphy.gif)

किसी दिए गए सूत्र के साथ सरणी के प्रत्येक तत्व को संसाधित करने वाला एक उदाहरण 👇 :

```jsx live
function learnJavaScript() {
  let celsius = [-15, -5, 0, 10, 16, 20, 24, 32]

  let fahrenheit = celsius.map(t => t * 1.8 + 32 + ' ')

  return fahrenheit
}
```

<!-- ### Отображение массива чисел на массив квадратных корней

Отображение таблицы пользователей в виде читаемой строки только с указанными ключами
Следующий код📟 берёт массив чисел и создаёт 🆕 новый массив, содержащий квадратные корни чисел из первого массива.

```jsx live
function learnJavaScript() {
  var numbers = [1, 4, 9]
  var roots = numbers.map(Math.sqrt) + ' '
  return roots
}
``` -->

#### एक तर्क वाले फ़ंक्शन का उपयोग करके संख्याओं की एक सरणी प्रदर्शित करना 👇 :

```jsx live
function learnJavaScript() {
  const numbers = [1, 4, 9]

  const doubles = numbers.map(num => num * 2 + ' ')

  return doubles
}
```

<!-- ![Wow](https://media.giphy.com/media/1ym5LJ17vp77BL8X5O/giphy.gif)

#### Обобщённое использование `map`

Этот пример показывает, как использовать `map` на объекте строки `String` для получения массива байт в кодировке `ASCII`, представляющего значения символов 👇 :

```jsx live
function learnJavaScript() {
  var map = Array.prototype.map
  var a =
    map.call('Hello World', function (x) {
      return x.charCodeAt(0)
    }) + ' '
  return a
}
```

#### Использование `map` для переворачивания строки

```jsx live
function learnJavaScript() {
  var str = '12345'
  result = [].map
    .call(str, function (x) {
      return x
    })
    .reverse()
    .join('')
  return result
}
``` -->

## filter

![filter](https://media.giphy.com/media/xT5LMGupUKCHb7DnFu/giphy.gif)

तरीका `filter()` बनाता है 🆕 सभी तत्वों के साथ एक नया सरणी जो पास किए गए फ़ंक्शन में निर्दिष्ट सत्यापन को पारित करता है⚙️.

काम का नतीजा `filter` हमेशा एक सरणी है। यदि समारोह⚙️ तत्व रिटर्न के लिए🔄 `true` ✅ (या कोई "सत्य" अर्थ), यह तत्व परिणाम में शामिल है, अन्यथा यह शामिल नहीं है।

### वाक्य - विन्यास

![write](https://media.giphy.com/media/6Do13TV1OfOF2/giphy.gif)

```javascript
let newArray = arr.filter(function callback(element[, index, [array]])[, thisArg])
```

### विवरण

![m](https://media.giphy.com/media/DQaeCdCqhHWx3n4dvH/giphy.gif)

तरीका `filter()` पारित फ़ंक्शन को कॉल करें⚙️ `callback` सरणी में मौजूद प्रत्येक तत्व के लिए एक बार और सभी मानों के साथ एक नया सरणी बनाता है जिसके लिए फ़ंक्शन⚙️ `callback` लौटा हुआ `true` ✅ या एक मूल्य बन रहा है `true` ✅ जब लाया गया `boolean`. समारोह⚙️ `callback` केवल उन सरणी सूचकांकों के लिए कहा जाता है जिन्होंने मान निर्दिष्ट किए हैं; इसे उन इंडेक्स के लिए नहीं कहा जाता है जिन्हें छोड़ दिया गया है या कभी भी मान असाइन नहीं किया गया है। ऐरे तत्व जो फ़ंक्शन सत्यापन को विफल करते हैं⚙️ `callback`, बस छोड़ दिए गए हैं और इसमें शामिल नहीं हैं 🆕 नई सरणी।

समारोह⚙️ `callback` तीन तर्कों के साथ बुलाया गया:

- तत्व का मूल्य;
- तत्व सूचकांक;
- वह सरणी जिसके माध्यम से मार्ग किया जाता है।

यदि विधि में `filter()` पैरामीटर पारित किया गया था `thisArg`, किसी फ़ंक्शन को कॉल करते समय⚙️ यह एक मूल्य के रूप में इस्तेमाल किया जाएगा `this`. अन्यथा, मान के रूप में `this` मूल्य का उपयोग किया जाएगा `undefined`. अंतत: अर्थ `this`, समारोह से देखने योग्य⚙️, निर्धारित करने के लिए सामान्य नियमों के अनुसार निर्धारित `this`, समारोह से दृश्यमान⚙️.

तरीका `filter()` उस सरणी को नहीं बदलता जिसके लिए इसे बुलाया गया था।

विधि द्वारा संसाधित तत्वों की श्रेणी `filter()`, फ़ंक्शन के पहले कॉल से पहले सेट करें⚙️ `callback`. विधि निष्पादित होने के बाद सरणी में जोड़े गए आइटम `filter()`, समारोह द्वारा दौरा नहीं किया जाएगा⚙️ `callback`. यदि सरणी के मौजूदा तत्व बदलते हैं, तो मान फ़ंक्शन को पास हो जाते हैं⚙️ `callback`, उस समय मान होंगे जब विधि `filter()` उनका दौरा करेंगे। हटाए गए आइटम का दौरा नहीं किया जाएगा।

### उदाहरण

![math](https://media.giphy.com/media/3orieN7HEHI0tw8x5C/giphy.gif)

#### सभी छोटे मानों को फ़िल्टर करना

निम्नलिखित उदाहरण का उपयोग करता है `filter()` बनाने के लिए🏗️ एक फ़िल्टर की गई सरणी जिसके सभी तत्व . से अधिक या उसके बराबर हैं `value`, और सभी छोटे `value` निकाला गया।

```jsx live
function learnJavaScript() {
  const isBigEnough = value => value >= 10

  let filtered = [12, 5, 8, 130, 44].filter(isBigEnough) + ' '

  return filtered
}
```

![Wow](https://media.giphy.com/media/M33UV4NDvkTHa/giphy.gif)

## reduce

![count](https://media.giphy.com/media/xUPGcqaVH1cDeKZTBS/giphy.gif)

तरीका `reduce` एक सरणी के संदर्भ में भी चलता है और प्रत्येक तत्व के लिए फ़ंक्शन⚙️ को कॉल करता है, लेकिन इससे परे, यह सभी कॉल के परिणामों को एक ही मान में जमा करता है। इस व्यवहार को नियंत्रित किया जा सकता है।

`reduce` संग्रह के तत्वों को बदलने का इरादा नहीं है जैसे `map`. इसका कार्य एक या दूसरे तरीके से सभी तत्वों के "योग" की गणना करना और इसे वापस करना है।

परिणामी मूल्य कुछ भी हो सकता है: एक संख्या, एक स्ट्रिंग, एक वस्तु, एक सरणी - यह सब उस समस्या पर निर्भर करता है जिसे वह हल करता है JavaScript विकासकर्ता।

तरीका `reduce` 2 पैरामीटर लेता है:

- समारोह, जैसे `map`, जिसे संग्रह में प्रत्येक आइटम के लिए क्रमिक रूप से बुलाया जाएगा;
संचायक का प्रारंभिक मूल्य है।

समारोह में⚙️ 2 तर्क भी:

- पहला संचित मूल्य (संचयक) है;
- सीधे सरणी का एक तत्व।

### वाक्य - विन्यास

```javascript
array.reduce(function callback[, initialValue])
```

### विवरण

![describe](https://media.giphy.com/media/3orieVr84udUl4wbQs/giphy.gif)

तरीका `reduce()` выполняет функцию⚙️ `callback` один раз для каждого элемента, присутствующего в массиве, за исключением пустот, принимая четыре аргумента: начальное значение (или значение от предыдущего вызова `callback`), значение текущего элемента, текущий индекс и массив, по которому происходит итерация.

При первом вызове функции⚙️, параметры `accumulator` и `currentValue` могут принимать одно из двух значений. Если при вызове `reduce()` передан аргумент `initialValue`, то значение `accumulator` будет равным значению `initialValue`, а значение `currentValue` будет равным первому значению в массиве. Если аргумент `initialValue` не задан, то значение `accumulator` будет равным первому значению в массиве, а значение `currentValue` будет равным второму значению в массиве.

Если массив пустой и аргумент `initialValue` не указан, будет брошено исключение `TypeError`. Если массив состоит только из одного элемента (независимо от его положения в массиве) и аргумент `initialValue` не указан, или если аргумент `initialValue` указан, но массив пустой, то будет возвращено🔄 одно это значение, без вызова функции⚙️ `callback`.

### Начальное значение аккумулятора

![hatchng](https://media.giphy.com/media/xT1R9Qy80qNb8oQGGc/giphy.gif)

Разберемся с начальным значением. В примере оно равно `0`, так как мы считаем численное значение – сумму возрастов. На месте нуля может быть любое другое число/строка (пустая или нет)/объект/массив – любое значение, с которого вы начинаете аккумуляцию. Для примера объединим имена всех друзей в одну строчку 👇 :

```jsx live
function learnJavaScript() {
  const friends = [
    { passport: '03005988', name: 'Joseph Francis Tribbiani Jr', age: 32, sex: 'm' },
    { passport: '03005989', name: 'Chandler Muriel Bing', age: 33, sex: 'm' },
    { passport: '03005990', name: 'Ross Eustace Geller', age: 33, sex: 'm' },
    { passport: '03005991', name: 'Rachel Karen Green', age: 31, sex: 'f' },
    { passport: '03005992', name: 'Monica Geller', age: 31, sex: 'f' },
    { passport: '03005993', name: 'Phoebe Buffay', age: 34, sex: 'f' }
  ]

  const names = friends.reduce((accumulator, friend) => `${accumulator} ${friend.name}, `, 'Friends: ')

  return names
}
```

Здесь исходным значением послужила строка `"Friends:"`, к которой постепенно добавились имена всех друзей.

Если вы не указываете исходное значение явно, им неявно становится первый 1️⃣ элемент массива. В этом случае функция⚙️ для него уже не вызывается.

### Пример

#### Суммирование всех значений в массиве:

```jsx live
function learnJavaScript() {
  const initialValue = 0

  const sum = [1, 2, 3].reduce((accumulator, currentValue) => {
    return accumulator + currentValue
  }, initialValue)

  return sum
}
```

И тоже самое в одну строчку кода:

```jsx live
function learnJavaScript() {
  const sum = [1, 2, 3].reduce((x, y) => x + y)

  return sum
}
```

<!-- #### Сглаживание массива массивов:

![transform](https://media.giphy.com/media/dVleMgtOlPE6Q/giphy.gif)

Код📟 решает задачу преобразования массива массивов в один плоский массив. Результат первой итерации будет равен: `[…[], …[1, 2, 3]]` что означает, что он преобразуется в `[1, 2, 3]` — это значение мы предоставляем как `acc` на второй итерации и так далее.

```jsx live
function learnJavaScript() {
  const nested = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
  ]

  const flat = nested.reduce((acc, it) => [...acc, ...it], [])

  return flat + ' '
}
```

#### Разворачивание массива массивов:

```jsx live
function learnJavaScript() {
  const flattened = [
    [0, 1],
    [2, 3],
    [4, 5]
  ].reduce(function (a, b) {
    return a.concat(b) + ' '
  })

  return flattened
}
``` -->

## chaining

![unity](https://media.giphy.com/media/jTf2Io0LtBXGZddOVE/giphy.gif)

Программирование на JavaScript поддерживает удобный паттерн чейнинг (`chaining`) – объединение нескольких функций⚙️ в одну цепочку с последовательной передачей результата.

Все три разобранных метода вызываются в контексте массива, а два 2️⃣ из них еще и возвращают🔄 массив. Таким образом, их очень легко объединить.

Например, посчитаем общий возраст всех мальчиков 👇 :

```jsx live
function learnJavaScript() {
  const friends = [
    { passport: '03005988', name: 'Joseph Francis Tribbiani Jr', age: 32, sex: 'm' },
    { passport: '03005989', name: 'Chandler Muriel Bing', age: 33, sex: 'm' },
    { passport: '03005990', name: 'Ross Eustace Geller', age: 33, sex: 'm' },
    { passport: '03005991', name: 'Rachel Karen Green', age: 31, sex: 'f' },
    { passport: '03005992', name: 'Monica Geller', age: 31, sex: 'f' },
    { passport: '03005993', name: 'Phoebe Buffay', age: 34, sex: 'f' }
  ]
  let totalBoysYears = friends
    .filter(friend => friend.sex === 'm')
    .reduce((accumulator, friend) => accumulator + friend.age, 0)
  return totalBoysYears
}
```

Или соберем номера паспортов девочек, чтобы купить им билеты на самолет до Лас-Вегаса 👇 :

```jsx live
function learnJavaScript() {
  const friends = [
    { passport: '03005988', name: 'Joseph Francis Tribbiani Jr', age: 32, sex: 'm' },
    { passport: '03005989', name: 'Chandler Muriel Bing', age: 33, sex: 'm' },
    { passport: '03005990', name: 'Ross Eustace Geller', age: 33, sex: 'm' },
    { passport: '03005991', name: 'Rachel Karen Green', age: 31, sex: 'f' },
    { passport: '03005992', name: 'Monica Geller', age: 31, sex: 'f' },
    { passport: '03005993', name: 'Phoebe Buffay', age: 34, sex: 'f' }
  ]
  let girlsPassports = friends.filter(friend => friend.sex === 'f').map(friend => friend.passport) + ' '
  return girlsPassports
}
```

## Заключение

С использованием этих замечательных функций⚙️ код📟 стало читать удобнее. Итак, ниже приведен список статей, в которых более подробна рассмотрена эта тема.

## Проблемы?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

Пишите в [Discord](https://discord.gg/6GDAfXn) или телеграмм [чат](https://t.me/jscampapp), а также подписывайтесь на наши [новости](https://t.me/javascriptapp)

## Вопросы:

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

Функция, вызываемая для каждого элемента массива?

1. `currentValue`
2. `array`
3. `callback`

Метод, который создаёт🏗️ новый массив с результатом вызова указанной функции для каждого элемента массива:

1. `map`
2. `filter`
3. `reduce`

Результирующим значением метода `reduce` может выступать:

1. Число
2. Массив
3. Что угодно

Суммирование всех значений в массиве достигается методом:

1. `map`
2. `filter`
3. `reduce`

Необязательный параметр или значение, используемое в качестве `this` при вызове функции `callback`:

1. `array`
2. `index`
3. `thisArg`

Метод, который создаёт🏗️ новый массив со всеми элементами, прошедшими проверку, задаваемую в передаваемой функции:

1. `map`
2. `filter`
3. `reduce`

Объединение нескольких функций в одну цепочку с последовательной передачей результата:

1. unity
2. chaining
3. merger

Для того чтобы понять, на сколько вы усвоили этот урок, пройдите тест в [мобильном приложении](http://onelink.to/njhc95) нашей школы по этой теме.

![Sumerian school](/img/app.jpg)

## Ссылки:

1. [Упрости свой JavaScript – используй map, reduce и filter](https://proglib.io/p/javascript-map-reduce-filter)
2. [15 Полезных javascript примеров map(), reduce() и filter()](https://webdevblog.ru/15-poleznyh-javascript-primerov-map-reduce-i-filter)
3. [Array.prototype.map()](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
4. [Array.prototype.filter()](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
5. [Array.prototype.reduce()](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/AlisaNasibullina"><img src="https://avatars3.githubusercontent.com/u/74646904?s=460&v=4" width="200px;" alt=""/><br /><sub><b>AlisaNasibullina</b></sub></a><br /><a href="#mentoring-KoDim-React" title="Mentoring">📖</a></td>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /><a href="#financial-gHashTag" title="Financial">💵</a></td>
    <td align="center"><a href="https://github.com/Resoner2005"><img src="https://avatars1.githubusercontent.com/u/75675814?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Resoner2005</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/issues?q=author%3AResoner2005" title="Bug reports">🐛 🎨 🖋</a></td>
    <td align="center"><a href="https://github.com/Navernoss"><img src="https://avatars0.githubusercontent.com/u/75784137?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Navernoss</b></sub></a><br /><a href="#content-Navernoss" title="Content">🖋 🐛 🎨 </a></td>
  </tr>
  
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)

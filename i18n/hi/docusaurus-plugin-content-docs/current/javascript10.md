---
id: javascript10
title: वस्तुओं
sidebar_label: वस्तुओं
---

![@serverSerrverlesskiy](/img/javascript/headers/11.jpg)

वस्तुएं एक कोठरी की तरह होती हैं📦 चीजों के लिए, भंडारण के लिए इरादा 📦 और अन्य प्रकार के डेटा का परिवहन।
JavaScript एक सरल प्रतिमान के साथ बनाया गया है। अवधारणा सरल वस्तुओं पर आधारित है। एक वस्तु गुणों का एक संग्रह है, और प्रत्येक संपत्ति में एक नाम (कुंजी) और उस नाम से जुड़ा एक मूल्य होता है। किसी गुण का मान एक फलन हो सकता है, जिसे किसी वस्तु की विधि या कोई अन्य प्रकार कहा जा सकता है।

![Object](https://media.giphy.com/media/xTiTnFEfyt0vqhQzDi/giphy.gif)

इस लेख में, हम वस्तुओं के सबसे बुनियादी गुणों को देखेंगे। JavaScript, जंतु🏗️ और परिवर्तन, गुणों की गणना।

वस्तु में JavaScript एक साधारण सहयोगी सरणी है या, दूसरे शब्दों में, "हैश"। यह किसी भी मैच को स्टोर करता है `"मौलिक मूल्य"` और कई मानक तरीके हैं।

वस्तुओं में JavaScript वास्तविक जीवन में वस्तुओं की तरह (एक व्यक्ति👨, बस, भवन, आदि) के कई नाम हैं (कुंजी🗝️) параметров (आयु, नाम, बालों का रंग, स्थिति) विशिष्ट मूल्यों के साथ (15 .), John, black, 'true') ✅ :

```javascript
let obj = {
  age: 15,
  name: 'John',
  color: 'black',
  student: true
}
```

वस्तु विधि JavaScript - यह सिर्फ एक फ़ंक्शन है जिसे सहयोगी सरणी में जोड़ा गया है।

```jsx live
function learnJavaScript() {
  let obj = {
    // गुण: मान
    age: 15,
    name: 'John',
    // विधि: समारोह
    say: () => 'Hello!'
  }
  return obj.say()
}
```

### वस्तु निर्माण

![Object](https://media.giphy.com/media/2YaKpvYQEcl1WuJJTl/giphy.gif)

कम्प्यूटर में🖥️ हम कल्पना कर सकते हैं `एक वस्तु` कैबिनेट के रूप में📦 उस पर हस्ताक्षर किए गए नाम-गुणों के साथ (`पहुँच कुंजियाँ`). कैबिनेट के अंदर📦 बक्से🧰 - डेटा (विशिष्ट जानकारी) और चीजों के समान छोटी वस्तुएं भी हो सकती हैं। द्वारा `चाभी` आवश्यक बॉक्स🧰 इसमें नया खोजना, हटाना या जोड़ना (लिखना) आसान है `मूल्य`.

![obj01](/img/javascript/12/01.png)

यह दो . है 2️⃣ बनाने के विकल्प🏗️ खाली वस्तु:

```javascript
// समकक्ष रिकॉर्ड
let obj = {}
let person = new Object()
```

दूसरा विकल्प व्यवहार में बहुत कम ही प्रयोग किया जाता है।

![obj00](/img/javascript/12/00.png)

## उन्नत निर्माण

![Extended](https://media.giphy.com/media/2XflxzlJfoSDycf3BBu/giphy.gif)

गुण निर्माण के दौरान सीधे निर्दिष्ट किए जा सकते हैं🏗️ वस्तु, प्रपत्र के घुंघराले ब्रेसिज़ में एक सूची के माध्यम से {..., `मौलिक मूल्य,` ...} और बनाएँ🏗️ जटिल वस्तुएं:

```jsx live
function learnJavaScript() {
  const obj = {
    age: 15,
    name: 'John',
    color: 'black',
    passport: {
      serial: 5721,
      number: 258963,
      date: '27.10.2015'
    },
    student: true
  }

  return obj.passport.date
}
```

बनाया था🏗️ объект विशिष्ट मूल्यों के साथ पांच गुण होते हैं, जिनमें से एक पासपोर्ट डेटा है, जो एक एम्बेडेड ऑब्जेक्ट है। ध्यान दें कि ऑब्जेक्ट के दूर के गुणों या विधियों को कॉल कैसे किया जाता है। अपना पासपोर्ट नंबर वापस पाने का प्रयास करें।

## गुण जोड़ना

![Adding](https://media.giphy.com/media/3CZ2iGe1ByKfhZxaD7/giphy.gif)

वहाँ दो हैं 2️⃣ किसी वस्तु में गुण जोड़ने के लिए वाक्य रचना। 1️⃣ पहला आवर्त है, दूसरा वर्गाकार कोष्ठक है:

```javascript
// समकक्ष रिकॉर्ड
obj.age = 15
obj['age'] = 15
```

```jsx live
function learnJavaScript() {
  let obj = {
    name: 'John'
  }

  obj.age = 15

  return obj.age
}
```

वर्ग कोष्ठक मुख्य रूप से तब उपयोग किए जाते हैं जब `संपत्ति का नाम` (properties) में स्थित `परिवर्तनशील` 🔔 :

```javascript
let nameProp = 'age'
obj[nameProp] = 15
```

यहाँ चर के माध्यम से 🔔 `nameProp` संपत्ति का नाम सेट करें `"age"`, जो साहचर्य सरणी में कुंजी है जिसके द्वारा निहित है `मूल्य 15`.

```jsx live
function learnJavaScript() {
  let obj = {
    name: 'John'
  }

  let nameProp = 'age'
  obj[nameProp] = 15

  return obj.age
}
```

## संपत्तियों तक पहुंचना

![Door](https://media.giphy.com/media/l378znZcUM7b6VDyM/giphy.gif)

संपत्ति को एक्सेस करके एक्सेस किया जाता है 👇 :

```jsx live
function learnJavaScript() {
  let obj = {} // वस्तु खाली है
  obj.age = 17 // समकक्ष obj['age']=17 या तुरंत obj={age:17}

  let result1 = obj.age // विकल्प 1
  let result2 = obj['age'] // विकल्प 2

  return result1 + ' или ' + result2
}
```

यदि वस्तु `ऐसी कोई संपत्ति नहीं`, तो परिणाम होगा `'undefined'`. इसे अपने ब्राउज़र कंसोल में देखें।

```javascrript
let obj = {}
obj.nokey
```

![nokey](/img/javascript/15.jpg)

कोई गलती नहीं🙅‍♂️ गैर-मौजूद संपत्ति तक पहुँचने पर, कोई नहीं होगा, बस एक विशेष मूल्य लौटाया जाएगा `undefined`. किसी समारोह के अंदर अनुपस्थित होने पर⚙️ चाभी 🗝️ शब्द `return`, वही मान वापस आ जाएगा `undefined` - किसी चीज की कमी।

## गुण हटाना

![Delete](https://media.giphy.com/media/5xaOcLwEvFOizxHVyVy/giphy.gif)

हटा देगा ➖ संपत्ति संचालक `delete`. पिछले उदाहरण से पासपोर्ट नंबर निकालने का प्रयास करें:

कंसोल में पिछले उदाहरण से ऑब्जेक्ट बनाएं।

```javascript
const obj = {
  age: 15,
  name: 'John',
  color: 'black',
  passport: {
    serial: 5721,
    number: 258963,
    date: '27.10.2015'
  },
  student: true
}
```

अब नेस्टेड वस्तु को हटा दें `passport`

```javascript
delete obj.passport
```

अब अगर हम इसकी ओर मुड़ें, तो हमें परिणाम मिलता है `undefined`

```javascript
obj.passport
```

![delete obj](/img/javascript/16.jpg)

## वस्तु के तरीके

![Description](https://media.giphy.com/media/3ohzAqLk7azQ0O6RvW/giphy.gif)

अन्य भाषाओं के रूप में👅, वस्तुओं पर JavaScript यहां है `तरीकों`.

उदाहरण के लिए, आइए बनाते हैं🏗️ एक वस्तु `sport` सीधे विधि के साथ `run`:

```jsx live
function learnJavaScript() {
  let sport = {
    run: n => 'John' + ' दौड़ा ' + n + ' मीटर की दूरी पर!'
  }

  return sport.run(300)
}
```

### एक विधि जोड़ना

![Add](https://media.giphy.com/media/5ns6077LTlGACuwRQR/giphy.gif)

किसी मौजूदा ऑब्जेक्ट में एक विधि जोड़ना आसान है, एक फ़ंक्शन असाइन करें⚙️ `function(n) { ... }` संपत्ति `sport.run`.

```jsx live
function learnJavaScript() {
  let sport = {}

  sport.run = n => 'एथलीट दौड़ा ' + n + ' मीटर और यह था ' + 'Nikita'

  return sport.run(350)
}
```

<!-- :::note Обратите внимание
Очень часто методы используют в своих расчетах свойства своего же объекта.
::: -->

यह कक्षाओं, सृजन के बारे में नहीं है🏗️ प्रतियां और इस तरह। सरल - आप किसी भी समय एक नई विधि जोड़ सकते हैं या किसी मौजूदा को हटा सकते हैं।

<!--
```jsx live
function learnJavaScript() {
  var sport = {
    name: 'Nikita',
    age: 18
  }

  sport.run = (n, str) => {
    if (str === 'men') return 'Спортсмен пробежал ' + n + ' метров и это был ' + sport.name
    if (str === 'women') return 'Спортсменка пробежала ' + n + ' метров и это была ' + sport.name
    if (str !== 'men' || str !== 'women') return 'Человек пробежал ' + n + ' метров.'
  }

  return sport.run(350, 'women')
}
```

Подумайте, чем можно заменить множественный `if()`. JavaScript - очень динамический язык👅. -->

## वस्तु गुणों के माध्यम से लूपिंग

![enumeration](https://media.giphy.com/media/h5FIFDs6rXLpWlWWZJ/giphy.gif)

किसी वस्तु के सभी गुणों पर पुनरावृति करने के लिए, एक विशेष प्रकार के निर्माण का उपयोग किया जाता है `for .. in`:

```javascript
for(let key in obj) {
  // key - संपत्ति का नामs
  // obj[key] - संपत्ति मूल्य
  ...
}
```

Например 👇 :

```jsx live
function learnJavaScript() {
  let result = ''

  const obj = {
    age: 15,
    b: 'true',
    color: 'red'
  }

  for (let key in obj) {
    result += key + ':' + obj[key] + ' '
  }

  return result
}
```

और चुपके से, ईमानदार होने के लिए, लगभग कोई भी परिवर्तनशील 🔔 पर्यावरण में एक छोटी वस्तु है JavaScript. तो, उनका उपयोग करने से डरो मत।

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## सवाल और जवाब

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

कमांड के साथ एक खाली वस्तु बनाई जाती है:

1. `let obj = {}`
2. `function obj()`
3. `let x = 10`

ऑब्जेक्ट स्टोर मेल खाता है:

1.कुंजी: मूल्य
2.नाम: उपनाम
3.चर = मान

किसी विशिष्ट कुंजी को मान निर्दिष्ट करने का सिंटैक्स syntax (संपत्ति):

1. `color() = "green"`
2. `obj.color = "red"`
3. `function color () => "yellow"`

वस्तु विधि JavaScript - यह है

1. बस एक साहचर्य सरणी में जोड़ा गया एक फ़ंक्शन
2. बाहरी कार्य
3. वस्तु के बाहर वर्णित चर
वस्तु गुणों के माध्यम से लूपिंग

1. `for (let i = 0; i <= 100; i++) { sum += i }`
2. `for(let key in obj) { }`
3. `while (условие) { }`

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल।

![Sumerian school](/img/app.jpg)

## कड़ियाँ:

1. [MDN web doc. Developer.mozilla.org - लेख "डेटा प्रकार JavaScript और डेटा संरचनाएं"](https://developer.mozilla.org/ru/docs/Web/JavaScript/Data_structures)
2. [MDN web doc. Developer.mozilla.org - लेख "वस्तुओं का प्रारंभ"](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/Object_initialize)
3. [लेख "Object Types"](https://www.javascript.express/types/object_types)
4. [लेख "ऑब्जेक्ट्स", साइट Learn.javascript.ru](https://learn.javascript.ru/object)
5. [किशोरों के लिए कोड: प्रोग्रामिंग के लिए एकदम सही शुरुआती गाइड, खंड 1: Javascript - Jeremy Moritz ](https://www.amazon.com/Code-Teens-Beginners-Programming-Javascript-ebook/dp/B07FCTLVPC)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/KoDim-React"><img src="https://avatars1.githubusercontent.com/u/72087863?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy K.</b></sub></a><br /><a href="#mentoring-KoDim-React" title="Mentoring">📖</a></td>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /><a href="#financial-gHashTag" title="Financial">💵</a></td>
    <td align="center"><a href="https://github.com/Resoner2005"><img src="https://avatars1.githubusercontent.com/u/75675814?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Resoner2005</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/issues?q=author%3AResoner2005" title="Bug reports">🐛 🎨 🖋</a></td>
    <td align="center"><a href="https://github.com/Navernoss"><img src="https://avatars0.githubusercontent.com/u/75784137?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Navernoss</b></sub></a><br /><a href="#content-Navernoss" title="Content">🖋 🐛 🎨 </a></td>
  </tr>
  
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)

<!--

<!--
Это уже выходит за рамки текущей статьи, но вообще - существует еще одна форма перебора свойств, которая более надежна, особенно если используется библиотека типа prototype.

```javascript
for (prop in object) {
  if (!object.hasOwnProperty(prop)) continue
  //...
}
```
Эта форма отфильтровывает свойства, которые принадлежат не самому объекту, а его прототипу. Поэтому она работает, даже если в прототип Object добавлены новые свойства.

Более элегантный вариант записи:

```javascript
for (prop in object)
  if (object.hasOwnProperty(prop)) {
    //...
  }
```

### Доступ к объекту из метода

Обычно хочется, чтобы метод не просто вызывался из объекта, но имел доступ к самому объекту, мог менять находящиеся в нем данные.

Для этого используется ключевое слово this:

В отличие от многих языков, this никак не привязано к объекту, а обозначает просто объект, вызвавший эту функцию.
Например,

```javascript
function thisObj() {
  let vasya = { name: 'Вася' }
  let petya = { name: 'Петя' }

  let sayName = function () {
    console.log('Я - ' + (this.name ? this.name : 'безымянный'))
  }
  vasya.sayName = sayName

  // один и тот же метод в двух объектах
  petya.sayName = vasya.sayName

  // тут - this будет petya
  petya.sayName() // Я - Петя

  // тут - this будет vasya
  vasya.sayName() // Я - Вася

  // а тут - вызывается метод глобального объекта window, у которого нет имени
  sayName() // Я - безымянный
}

thisObj()
```
-->

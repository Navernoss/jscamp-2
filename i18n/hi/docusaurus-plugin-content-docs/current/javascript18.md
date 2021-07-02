---
id: javascript18
title: ऑपरेटर्स Rest तथा Spread
sidebar_label: ऑपरेटर्स Rest तथा Spread
---

![@serverSerrverlesskiy](/img/javascript/headers/19.jpg)

कई अंतर्निहित कार्य⚙️ JavaScript तर्कों की एक मनमानी संख्या का समर्थन करें।

उदाहरण के लिए:

`Math.max(arg1, arg2, ..., argN)` – पारित तर्कों की अधिकतम संख्या की गणना करता है।
`Math.min(arg1, arg2, ..., argN)` - रिटर्न🔄 पारित तर्कों का न्यूनतम मूल्य।

इस लेख में, हम सीखेंगे कि इसे अपने कार्यों के साथ कैसे करें।⚙️ और ऐसे कार्यों को कैसे पारित करें⚙️ एक सरणी के रूप में पैरामीटर।

## अवशिष्ट पैरामीटर `(...rest)`

![Parametrs](https://media.giphy.com/media/3osxYoufeOGOA7xiX6/giphy.gif)

फ़ंक्शन को कॉल करें⚙️ किसी भी संख्या में तर्कों के साथ संभव है, भले ही इसे कैसे परिभाषित किया गया हो।

उदाहरण के लिए 👇 :

```jsx live
function learnJavaScript() {
  let summa = (a, b, c) => {
    return a + b + c
  } // रकम 3 नंबर

  return summa(1, 2, 3, 4, 5, 6, 7)
}
```

अतिरिक्त तर्क त्रुटि का कारण नहीं बनेंगे, लेकिन निश्चित रूप से केवल पहले तीन को ही गिना जाएगा।

### संकल्पना ES6

![Idea](https://media.giphy.com/media/3o6Mbj2w67HnPQKgcE/giphy.gif)

मानक से शुरू ES6 की तरह एक अवधारणा थी `...rest` - अवशिष्ट पैरामीटर।

```jsx
let goFun = (...rest) => {
  // कलन विधि
}
```

मुक्त मापदंडों को तीन बिंदुओं द्वारा दर्शाया जा सकता है `...`. Бइसका शाब्दिक अर्थ है: "शेष पैरामीटर एकत्र करें और उन्हें एक सरणी में रखें"।

उदाहरण के लिए, आइए सभी तर्कों को एक सरणी में एकत्रित करें `args`👇 :

```jsx live
function learnJavaScript() {
  let sumAll = (...args) => {
    // args — पास करने के लिए तर्कों की सरणी का नाम
    let sum = 0
    for (let arg of args) if (typeof arg === 'number') sum += arg // sum - सभी संख्यात्मक तर्कों का योग एकत्र करेगा
    return sum
  }
  return sumAll(1, 2, 3, 4, 5, 6, 7, 'React', 'Native')
}
```

उत्तर पहले से ही 28 है और कोई त्रुटि नहीं है🙅‍♂️! तर्कों या सरणी के आयाम को बदलने का प्रयास करें।

### एकाधिक पैरामीटर

हम पहले कुछ पैरामीटर को वेरिएबल में रख सकते हैं 🔔 , और बाकी - एक सरणी में इकट्ठा करने के लिए।
इसका मतलब है कि आप बस सम्मिलित कर सकते हैं `...rest`, लेकिन केवल फ़ंक्शन के अंतिम पैरामीटर के बजाय।

![paste](https://media.giphy.com/media/3o6ZtafpgSpvIaKhMI/giphy.gif)

```jsx
let goFun = (first, second, ...rest) => {
  // कलन विधि
}
```

नीचे दिए गए उदाहरण में, पहले दो2️⃣ फ़ंक्शन तर्क पहला और अंतिम नाम बन जाएगा, और तीसरा और बाद वाला एक सरणी बन जाएगा `titles[i]` 👇 :

```jsx live
function learnJavaScript() {
  let free = ''
  let showName = (firstName, lastName, ...titles) => {
    free = firstName + ' ' + lastName // नाम + उपनाम
    return titles[0] + ' ' + titles[1]
  }
  // शेष पैरामीटर सरणी में जाएंगे titles = ["React", "Native"]
  // titles[0]  // React
  // titles[1]  // Native

  let result = showName('जूलियस', 'सीज़र', 'React', 'Native')

  return free + ' या ' + result
}
```

### संभावित गलतियाँ

![error](https://media.giphy.com/media/xTiN0L7EW5trfOvEk0/giphy.gif)

अवशिष्ट पैरामीटर अंत में होना चाहिए, ताकि आप लिख न सकें 🖊️ उनके बाद कुछ भी।
यह कारण होगा `एक गलती`:

```jsx
function f(arg1, ...rest, arg2) {   // arg2 के पश्चात ...rest ?
  // त्रुटि!
}
```

:::note याद कीजिए
`...rest` हमेशा अंतिम होना चाहिए।
:::

## एक्सटेंशन ऑपरेटर `...spread`

![operators](https://media.giphy.com/media/3o6Mbfd5fQszubehmE/giphy.gif)

हमने सीखा कि पैरामीटर सूची से एक सरणी कैसे प्राप्त करें, लेकिन कभी-कभी आपको इसके विपरीत करने की आवश्यकता होती है - सरणी को कॉल किए गए फ़ंक्शन में धकेलें।⚙️.

उदाहरण के लिए, एक अंतर्निहित फ़ंक्शन है⚙️ `Math.max`. वह वापस आ गयी🔄 सूची से सबसे बड़ी संख्या:

```jsx live
function learnJavaScript() {
  return Math.max(3, 5, 1, 17, 14, 8, 2, 11)
}
```

### यह इतना आसान नहीं है

![Index_finger](https://media.giphy.com/media/4ZcYCubFNk8AUHcZVw/giphy.gif)

मान लें कि हमारे पास संख्याओं की एक सरणी है `[3, 5, 1]`. उसके लिए कैसे कॉल करें `Math.max`?

आप बस उन्हें सम्मिलित नहीं कर सकते — `Math.max` संख्याओं की एक सूची प्राप्त करने की अपेक्षा करता है, एक भी सरणी नहीं।

```jsx live
function learnJavaScript() {
  let arr = [3, 5, 1, 17, 14, 8, 2, 11]
  return Math.max(arr) // NaN - मान अपरिभाषित होगा
}
```

हम निश्चित रूप से मैन्युअल रूप से नंबर दर्ज कर सकते हैं: `Math.max(arr[0], arr[1], arr[2]).`

लेकिन, सबसे पहले, यह बुरा लगता है, और दूसरी बात, हम हमेशा यह नहीं जानते कि कितने तर्क होंगे। उनमें से बहुत सारे हो सकते हैं, या बिल्कुल नहीं।

### मापदंडों की घटना

![Transform](https://media.giphy.com/media/xT4uQr9H3EDL7Ha2hq/giphy.gif)

एक्सटेंशन ऑपरेटर यहां हमारी मदद करेगा `...spread`. यह अवशिष्ट मापदंडों के समान है - यह `...` का भी उपयोग करता है, लेकिन ठीक इसके विपरीत करता है।

जब कार्यात्मक⚙️ `...spread` फ़ंक्शन को कॉल करते समय उपयोग किया जाता है⚙️, यह सरणी-वस्तु को परिवर्तित करता है `arr` तर्क सूची के लिए।

के लिये `Math.max` 👇 :

```jsx live
function learnJavaScript() {
  let arr = [3, 5, 1, 17, 14, 8, 2, 11]

  return Math.max(...arr) // ऑपरेटर ...arr सरणी को परिवर्तित करता है `arr` तर्क सूची के लिए
}
```

इसी तरह, हम कई iterables पास कर सकते हैं 👇 :

```jsx live
function learnJavaScript() {
  let arr1 = [1, 2, 34, 41]
  let arr2 = [8, 3, 18, 17]
  let arr3 = [2, 4, 16, 38]

  return 'Max = ' + Math.max(...arr1, ...arr2, ...arr3)
}
```

ठंडा! प्रोग्रामिंग के लिए एक बहुत ही लचीला दृष्टिकोण। आप स्प्रेड ऑपरेटर को सामान्य मानों के साथ भी जोड़ सकते हैं।

### सरणियों को मिलाना

![Merger](https://media.giphy.com/media/rytLWOErAX1F6/giphy.gif)

एक्सटेंशन ऑपरेटर `...spread` सरणियों को मर्ज करने के लिए भी इस्तेमाल किया जा सकता है 👇 :

```jsx live
function learnJavaScript() {
  let arr1 = [3, 5, 7]
  let arr2 = [4, 2, 8]

  let merged = [100, ...arr1, 500, ...arr2]
  let str = 'सरणी: ' + merged

  return <b>{str}</b>
}
```

### स्ट्रिंग में कनवर्ट करना

![Transform](https://media.giphy.com/media/RLVHPJJv7jY1q/giphy.gif)

कार्यात्मक⚙️ विस्तार ऑपरेटर `...spread` किसी भी चलने योग्य वस्तु के साथ काम करता है।

उदाहरण के लिए, स्प्रेड ऑपरेटर स्ट्रिंग को वर्णों की एक सरणी में बदलने के लिए उपयुक्त है 👇 :

```javascript
let str = 'नमस्ते, Alex!'
let result = [...str]
```

![spread](/img/javascript/13.jpg)

चलिए देखते हैं क्या होता है। हुड के तहत, स्प्रेड ऑपरेटर तत्वों पर पुनरावृति करने के लिए पुनरावृत्तियों का उपयोग करता है। ठीक वैसे ही जैसे `for..of`.

चक्र `for..of` वर्णों के अनुक्रम के रूप में स्ट्रिंग पर पुनरावृति करता है, इसलिए से `...str` यह पता चला है "П", "р", "и", "в", "е", "т"...
परिणामी वर्ण मानक घोषणा का उपयोग करके एक सरणी में एकत्र किए जाते हैं🗣️ सरणी `[...str].`

इस कार्य के लिए, हम उपयोग कर सकते हैं और `Array.from`. यह एक चलने योग्य वस्तु (जैसे एक स्ट्रिंग) को एक सरणी में भी परिवर्तित करता है 👇 :

```javascript
let str = 'नमस्ते'
Array.from(str) // "पी", "आर", "तथा", "में", "इ", "तो"
// Array.from चलने योग्य को एक सरणी में परिवर्तित करता है
```

![spread](/img/javascript/14.jpg)

परिणाम समान है `[...str].` लेकिन बीच `Array.from(obj)` तथा `[...obj]` इसमे अंतर है:

- `Array.from` छद्म सरणियों और पुनरावृत्तियों दोनों के साथ काम करता है।
- विस्तार ऑपरेटर `...spread` काम करता है `केवल` पुनरावर्तनीय के साथ।

इसलिये `Array.from` — एक अधिक बहुमुखी विधि।

## संपूर्ण

![Elipsis](https://media.giphy.com/media/UWXLULrP5KGDC/giphy.gif)

जब हम देखते हैं `"..."` कोड में📟 , यह अवशिष्ट मापदंडों के रूप में हो सकता है `...rest`, और प्रसार ऑपरेटर `...spread`.

उन्हें अलग कैसे बताएं:

- यदि एक `...` फ़ंक्शन तर्क सूची के अंत में स्थित है, ये "अवशिष्ट पैरामीटर" हैं। यह बाकी अनिर्दिष्ट तर्कों को एकत्र करता है और उनमें से एक सरणी बनाता है।
- यदि एक `...` फ़ंक्शन कॉल या अन्य जगहों पर होता है, यह "स्प्रेड ऑपरेटर" है। यह फ़ंक्शन को प्रारंभ करने के लिए एक सरणी से तत्वों को निकालता है।

याद रखने के लिए उपयोगी:

- अपरिभाषित संख्या में तर्कों के साथ नए फ़ंक्शन बनाने के लिए अवशिष्ट मापदंडों का उपयोग किया जाता है।
- स्प्रेड ऑपरेटर का उपयोग करके, आप एक फ़ंक्शन में एक सरणी सम्मिलित कर सकते हैं, जो डिफ़ॉल्ट रूप से, तर्कों की एक नियमित सूची के साथ काम करता है।
"एक साथ, ये निर्माण मूल्यों के सेट को सरणियों में बदलना आसान बनाते हैं और इसके विपरीत।

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## सवाल और जवाब

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

यदि एक `...` फ़ंक्शन तर्क सूची के अंत में स्थित है, तो हम इसके साथ काम कर रहे हैं:

1. अवशिष्ट पैरामीटर
2. विस्तार ऑपरेटर
3. यादृच्छिक संकेतक

अपरिभाषित संख्या में तर्कों के साथ एक फ़ंक्शन बनाने के लिए, उपयोग करें:

1. अवशिष्ट पैरामीटर `...rest`
2. विस्तार ऑपरेटर `...spread`
3. बाहरी कॉल फ़ंक्शन

आप दो सरणियों का उपयोग करके एक में जोड़ सकते हैं:

1. एक्सटेंशन ऑपरेटर
2. ऑपरेटर `Array.from`
3. अवशिष्ट पैरामीटर

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल।

![Sumerian school](/img/app.jpg)

## लिंक

1. [MDN web doc. लेख "spread syntax"](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/spread_syntax)
2. [लेख "अवशिष्ट पैरामीटर्स और स्प्रेडिंग ऑपरेटर"](https://learn.javascript.ru/rest-parameters-spread-operator)
3. [लेख " ऑपरेटर spread तथा rest"](https://medium.com/@stasonmars/%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%82%D0%BE%D1%80-spread-%D0%B8-rest-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B2-javascript-22eb33cb0825)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/KoDim-React"><img src="https://avatars1.githubusercontent.com/u/72087863?v=4?s=200" width="200px " alt=""/><br /><sub><b>Dmitriy K.</b></sub></a><br /><a href="#mentoring-KoDim-React" title="Mentoring">📖</a></td>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px " alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /><a href="#financial-gHashTag" title="Financial">💵</a></td>
    <td align="center"><a href="https://github.com/Resoner2005"><img src="https://avatars1.githubusercontent.com/u/75675814?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Resoner2005</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/issues?q=author%3AResoner2005" title="Bug reports">🐛 🎨 🖋</a></td>
    <td align="center"><a href="https://github.com/Navernoss"><img src="https://avatars0.githubusercontent.com/u/75784137?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Navernoss</b></sub></a><br /><a href="#content-Navernoss" title="Content">🖋 🐛 🎨 </a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)

<!--
Например:
```jsx
function showName() {
  console.log( arguments.length )
  console.log( arguments[0] )
  console.log( arguments[1] )

  // Объект arguments можно перебирать
  // for (let arg of arguments) console.log(arg)
}

// Вывод: 2, Юлий, Цезарь
showName("Юлий", "Цезарь")

// Вывод: 1, Илья, undefined (второго аргумента нет)
showName("Илья")
```
Раньше в языке не было остаточных параметров, и получить все аргументы функции можно было только с помощью arguments. Этот способ всё ещё работает, мы можем найти его в старом коде.
Но у него есть один недостаток. Хотя arguments похож на массив, и его тоже можно перебирать, это всё же не массив. Он не поддерживает методы массивов, поэтому мы не можем, например, вызвать arguments.map(...).
К тому же, arguments всегда содержит все аргументы функции — мы не можем получить их часть. А остаточные параметры позволяют это сделать.
Соответственно, для более удобной работы с аргументами лучше использовать остаточные параметры.
-->

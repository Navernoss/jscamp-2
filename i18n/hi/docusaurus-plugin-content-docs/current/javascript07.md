---
id: javascript07
title: नंबर
sidebar_label: नंबर
---

import YouTube from 'react-youtube'

![@serverSerrverlesskiy](/img/javascript/headers/07.jpg)

मॉडर्न में JavaScript वहाँ दो हैं 2️⃣ संख्या के प्रकार:

### `number`

नियमित संख्या numbers JavaScript 64-बिट प्रारूप में संग्रहीत IEEE-754, जिसे "डबल प्रिसिजन फ्लोटिंग पॉइंट नंबर" भी कहा जाता है (double precision floating point numbers). Эये वे नंबर हैं जिनका हम सबसे अधिक उपयोग करेंगे। पूर्णांकों को एक अलग प्रकार की संख्या नहीं माना जाता है। फ़्लोटिंग पॉइंट नंबरों के अलावा, तीन वर्ण मान भी हैं जो संख्यात्मक डेटा प्रकार से संबंधित हैं: `Infinity`, `-Infinity`, и `NaN` (गैर संख्या).

![Numbers](https://media.giphy.com/media/JtBZm3Getg3dqxK0zP/giphy.gif)

### `bigInt`

संख्याएँ मनमानी लंबाई के पूर्णांकों के साथ काम करना संभव बनाती हैं। उनकी शायद ही कभी आवश्यकता होती है और उन मामलों में उपयोग किया जाता है जहां अधिकतम सुरक्षित पूर्णांक मान के बाहर के मानों के साथ काम करना आवश्यक होता है। `Number`.

कोई भी संख्या, यहाँ तक कि दशमलव भिन्न, जिसमें बहुत से दशमलव स्थान हों, को कभी भी उद्धृत नहीं किया जाता है।

आप चार प्रकार के संख्यात्मक शाब्दिक उपयोग कर सकते हैं: दशमलव, बाइनरी, ऑक्टल और हेक्साडेसिमल। चूंकि अंतिम तीन का उपयोग बहुत ही कम किया जाता है, इसलिए हम उनके विस्तृत विवरण को छोड़ देंगे। 🖊️ , ठीक है, जिज्ञासु लोग कर सकते हैं उन्हें जानिए [यहां](https://developer.mozilla.org/ru/docs/Web/JavaScript/Guide/Numbers_and_dates).

:::caution
अग्रणी शून्य का उपयोग करते समय सावधान रहें! इसका मतलब है कि आपको दशमलव संख्या के सामने शून्य डालने की आवश्यकता नहीं है।
:::

```jsx
1234567890
42

0888 // 888 दशमलव के रूप में संभाला
0777 // गैर-सख्त अष्टाधारी के रूप में संभाला (511 दशमलव)
```

## अंकगणितीय आपरेशनस

![Arithmetic operation](https://media.giphy.com/media/gEvab1ilmJjA82FaSV/giphy.gif)

एक नया पूर्णांक बनाने के लिए दो या दो से अधिक पूर्णांकों का उपयोग किया जा सकता है। एक नया पूर्णांक बनाने के कई तरीके हैं। दो या दो से अधिक संख्याओं से नई संख्या बनाने की विधि को अंकगणित कहते हैं।
सामान्य तौर पर, कई अंकगणितीय ऑपरेशन होते हैं, लेकिन केवल चार मुख्य होते हैं: जोड़, घटाव, गुणा और भाग। उन्हें मुख्य कहा जाता है, क्योंकि अन्य सभी क्रियाएं उनके पास लाई जाती हैं।

पलस हसताक्षर `+` जोड़ व्यक्त करने के लिए प्रयोग किया जाता है: `4 + 4` उत्तर: `8`

घटाव के लिए माइनस `-`: `7 - 6` उत्तर: `1`

तारांकन `*` गुणन का प्रतिनिधित्व करता है: `3 * 4` उत्तर: `12`

फॉरवर्ड स्लैश `/` डिवीजन: `15 / 5` उत्तर: `3`

यदि एक पंक्ति में एक से अधिक क्रियाएं की जाती हैं, तो उन्हें एक दूसरे से अलग करने के साथ-साथ कोड बनाने के लिए📟 अधिक पठनीय, हम उपयोग करते हैं - (कोष्ठक)। आइए निम्नलिखित वाक्यों को कंसोल में टाइप करें। उनमें से प्रत्येक के उत्तर में केवल एक अंक होना चाहिए।9️⃣:

```
 3 * (2 + 1)
(3 + 9) / (10 - 6)
(2 + 3 * 4) / (6 + 1)
 2 * (5 - 8 / 2) * (3 + 1)
```

में प्रवेश करें `LIVE EDITOR` सूचीबद्ध मूल्य 👇 :

```jsx {2} live
function learnJavaScript() {
  let result = 2 + 3 // यहां
  return result
}
```

## संयुक्त असाइनमेंट

![Conbination](https://media.giphy.com/media/l2Sq8jlaqqnqBoGhG/giphy.gif)

एक ऑपरेटर एक अभिव्यक्ति में ऑपरेंड पर की गई कुछ क्रियाओं का एक प्रतीकात्मक पदनाम है(उदाहरण के लिए: `+`, `-`, `*`, `/`).

संकार्य कार्यक्रम में संसाधित कुछ मूल्य का प्रतिनिधित्व करता है। ऑपरेंड किसी भी डेटा प्रकार का हो सकता है। ऑपरेटर के बाईं ओर का ऑपरेंड बायां ऑपरेंड है, ऑपरेटर के दाईं ओर का ऑपरेंड दायां ऑपरेंड है।

मुख्य संयुक्त असाइनमेंट ऑपरेटर साइन है समान रूप से `=`, यह दाएं ऑपरेंड का मान बाईं ओर निर्दिष्ट करता है। अर्थात - `x = y` एक चर के लिए एक मान निर्दिष्ट करता है 🔔 `y`, परिवर्तनशील 🔔 `x`.

आप पहले ही एक से अधिक बार देख चुके हैं कि गणितीय ऑपरेटरों की मदद से चर के लिए मूल्यों का असाइनमेंट कैसे होता है। 🔔 . उदाहरण के लिए, इस तरह:

```javascript
let sum = 2 + 3 // राशि का मूल्य 7
```

और आपके पास शायद यह भूलने का समय नहीं था कि आप किसी भी समय पहले से ज्ञात चर के मान को बदल सकते हैं। 🔔 :

```jsx live
function learnJavaScript() {
  let sum = 2 + 3
  sum = sum + 3 // अब योग का मूल्य बन गया है 8
  return sum
}
```

अतिरिक्त असाइनमेंट `+=` एक चर के मूल्य को जल्दी से बढ़ाने के लिए! यहां कुछ उदाहरण दिए गए हैं:

```javascript
let मूल्य = 5
मूल्य += 2 // मूल्य अब क 7 (बराबर मूल्य = // मूल्य + 2)
मूल्य += 3 // मूल्य अब क 10 (बराबर, что मूल्य = // मूल्य + 3)
मूल्य = मूल्य + मूल्य // 20 (लेकिन आप बस कर सकते हैं मूल्य += // मूल्य)
मूल्य += मूल्य // 40 (बराबर मूल्य = मूल्य + // मूल्य)
```

आप पहले ही अनुमान लगा चुके हैं कि इसी तरह की चीजें अन्य गणितीय संक्रियाओं के साथ काम करती हैं, है ना?!

```javascript
मूल्य –= 25 // मूल्य अब क 15 (बराबर मूल्य = मूल्य − // 25)
मूल्य -= 2 // मूल्य अब क 30 (बराबर मूल्य = // मूल्य - 2)
मूल्य /= 3 // मूल्य अब क 10 (बराबर मूल्य = // value / 3)
मूल्य // उत्तर: 10
```

इसके बाद, सूचीबद्ध सभी उदाहरणों की जाँच करें `LIVE EDITOR`:

```jsx live
function learnJavaScript() {
  let मूल्य = 0 + 0
  return मूल्य
}
```

आप संयुक्त असाइनमेंट के बारे में अधिक पढ़ सकते हैं [यहां](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/Assignment_Operators)

## वेतन वृद्धि और कमी

![increment](https://media.giphy.com/media/dX9qnaX4OH3avyMcU3/giphy.gif)

ऑपरेटर `++` (वेतन वृद्धि) अपने ऑपरेंड के मूल्य को एक से बढ़ा देता है। यदि ऑपरेंड का मान एक संख्या नहीं है, तो ऑपरेटर स्वचालित रूप से इसे एक संख्या में बदल देता है, इसे एक से बढ़ा देता है, और परिणाम देता है, जो ऑपरेंड को वापस सौंपा जाता है:

```jsx live
function learnJavaScript() {
  let increment = 0
  increment++
  return increment
}
```

ऑपरेटर `--` (घटती) इंक्रीमेंट ऑपरेटर के समान काम करता है, लेकिन इसके ऑपरेंड के मूल्य में वृद्धि नहीं करता है, लेकिन इसके विपरीत, इसे एक से घटा देता है:

```jsx live
function learnJavaScript() {
  let decrement = 6
  decrement--
  return decrement
}
```

## ऑपरेटर modulo

![function](https://media.giphy.com/media/seVVu09CPz2upPeU1s/giphy.gif)

संकेत `%` (प्रतिशत) हम शेष भाग को निरूपित करते हैं। ऑपरेटर रिटर्न🔄 बाएं ऑपरेंड को दाएं से विभाजित करने का पूर्णांक शेष। लौटाया हुआ🔄 मूल्य को हमेशा लाभांश का चिन्ह मिलता है, भाजक का नहीं। यह अंतर्निहित फ़ंक्शन का उपयोग करता है⚙️ modulo, परिणाम प्राप्त करने के लिए, जो कि विभाजन का पूर्णांक शेष है `let1` पर `let2`.

`12 % 5` परिणाम `2`

`NaN % 2` परिणाम `NaN`

`1 % 2` परिणाम `1`

`2 % 3` परिणाम `2`

`4 % 2` परिणाम `0`

`5.5 % 2` परिणाम `1.5`

में सूचीबद्ध सभी उदाहरण देखें `LIVE EDITOR` और आप तुरंत सब कुछ समझ जाएंगे:

```jsx live
function learnJavaScript() {
  let modulo = 12 % 5
  return modulo
}
```

## गोलाई

![Balls](https://media.giphy.com/media/6glYLqOQ3dlok/giphy.gif)

तरीका `Math.round()` रिटर्न🔄 संख्या, निकटतम पूर्णांक के लिए गोल। यदि संख्या का भिन्नात्मक भाग से बड़ा या उसके बराबर है `0,5`, तर्क को निकटतम बड़े पूर्णांक में गोल किया जाएगा। यदि संख्या का भिन्नात्मक भाग कम है `0,5`, तर्क को निकटतम छोटे पूर्णांक में गोल किया जाएगा।

`result = Math.round(20.49)` मान लौटाता है 20

`result = Math.round(20.5)` मान लौटाता है 21

इसे स्वयं जांचें:

```jsx live
function learnJavaScript() {
  let result = Math.round(20.49)
  return result
}
```

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## सवाल और जवाब:

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

क्या अंकगणितीय संक्रियाओं को मूल कहा जाता है?

1. जोड़, घटाव
2. गुणा, भाग
3. जोड़, घटाव, गुणा, भाग

सही तरीके से कैसे पढ़ें `+=`?

1. वेतन वृद्धि
2. अतिरिक्त के साथ असाइनमेंट
3. प्लस और इक्वल

इंक्रीमेंट को चिन्ह (ओं) से कैसे लिखा जाता है?

1. `++`
2. `--`
3. `+`

शेष भाग के लिए चिन्ह क्या है?

1. `%`
2. `/`
3. `\`

मातलब क्या है `Math.round` कार्रवाई पर वापस आ जाएगा `Math.round (20.62)`?

1. `22`
2. `20`
3. `21`

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल।

![Sumerian school](/img/app.jpg)

## लिंक:

1. [MDN web docs](https://developer.mozilla.org/ru/docs/Web/JavaScript/Guide/Numbers_and_dates)
2. [किशोरों के लिए कोड: प्रोग्रामिंग के लिए एकदम सही शुरुआती मार्गदर्शिका, खंड १: Javascript - Jeremy Moritz ](https://www.amazon.com/Code-Teens-Beginners-Programming-Javascript-ebook/dp/B07FCTLVPC)
3. [JavaScript.ru](https://learn.javascript.ru/number)
4. [पूर्णांक अंकगणित](https://maths-public.ru/arithmetic/actions)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<table>
  <tr>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /> <a href="https://github.com/gHashTag/react-native-village/commits?author=gHashTag" title="Documentation">📖</a><a href="#financial-gHashTag" title="Financial">💵</a></td>
    <td align="center"><a href="https://github.com/Resoner2005"><img src="https://avatars1.githubusercontent.com/u/75675814?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Resoner2005</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/issues?q=author%3AResoner2005" title="Bug reports">🐛 🎨 🖋</a></td>
  </tr>
  
</table>

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)

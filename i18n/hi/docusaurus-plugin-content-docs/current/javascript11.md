---
id: javascript11
title: रूपांतरण और कास्टिंग टाइप करें
sidebar_label: रूपांतरण और कास्टिंग टाइप करें
---

![@serverSerrverlesskiy](/img/javascript/headers/09.jpg)

## कास्ट (type coercion)

यह एक डेटा प्रकार से दूसरे में मानों का स्वचालित या अंतर्निहित रूपांतरण है (उदाहरण के लिए, एक स्ट्रिंग से एक संख्या)। प्रकार रूपांतरण प्रकार रूपांतरणों के समान होते हैं क्योंकि वे दोनों एक ही कुंजी के साथ एक डेटा प्रकार से दूसरे में मूल्यों को परिवर्तित करते हैं। यह एक डेटा प्रकार से दूसरे में मूल्यों का एक स्वचालित या निहित रूपांतरण है (उदाहरण के लिए, एक स्ट्रिंग से ए संख्या)। प्रकार रूपांतरण प्रकार रूपांतरणों के समान हैं क्योंकि वे दोनों एक ही कुंजी के साथ मूल्यों को एक डेटा प्रकार से दूसरे में परिवर्तित करते हैं🗝️ अंतर यह है कि प्रकार रूपांतरण निहित है, जबकि प्रकार रूपांतरण निहित या स्पष्ट हो सकता है।

![transformation](https://media.giphy.com/media/xT4uQr9H3EDL7Ha2hq/giphy.gif)

के उदाहरण 👇 :

```jsx live
function learnJavaScript() {
  const value1 = '5'
  const value2 = 9
  let sum = value1 + value2

  return sum
}
```

उपरोक्त उदाहरण में JavaScript नंबर देता है `9` एक स्ट्रिंग में और फिर दोनों को जोड़ता है 2️⃣ एक साथ मान, जिसके परिणामस्वरूप एक स्ट्रिंग `59`. JavaScript स्ट्रिंग या संख्या के बीच एक विकल्प था और स्ट्रिंग का उपयोग करने का निर्णय लिया।

संकलक के परिणामस्वरूप लाइन हो सकती थी `5` नंबर पर और राशि वापस करें `14`, लेकिन उसने नहीं किया। इस परिणाम को प्राप्त करने के लिए, आपको स्पष्ट रूप से स्ट्रिंग को रूपांतरित करने की आवश्यकता है `5` विधि का उपयोग करके एक संख्या में `Number()`👇 :

```jsx live
function learnJavaScript() {
  const value1 = '5'
  const value2 = 9
  let sum = Number(value1) + value2

  return sum
}
```

## रूपांतरण टाइप करें (type conversion)

![Transformation](https://media.giphy.com/media/l2SpMMVivErM0Q7jG/giphy.gif)

यानी डेटा को एक डेटा टाइप से दूसरे डेटा टाइप में ट्रांसफर करना। निहित रूपांतरण तब होता है जब संकलक स्वचालित रूप से डेटा प्रकारों को असाइन (असाइन) करता है, लेकिन स्रोत कोड📟 पूर्ण करने के लिए स्पष्ट रूप से रूपांतरण की भी आवश्यकता हो सकती है।

### स्ट्रिंग रूपांतरण

![Transformation](https://media.giphy.com/media/RLVHPJJv7jY1q/giphy.gif)

स्ट्रिंग रूपांतरण तब होता है जब आप किसी चीज़ को स्ट्रिंग के रूप में प्रस्तुत करना चाहते हैं। उदाहरण के लिए, हम फ़ंक्शन का उपयोग कर सकते हैं `String(value)`, मान को एक स्ट्रिंग में बदलने के लिए 👇 :

```jsx live
function learnJavaScript() {
  let value = true // boolean

  value = String(value)
  return typeof value
}
```

परिवर्तन एक स्पष्ट तरीके से होता है। `true` ✅ हो जाता है `"true"` ✅

### संख्यात्मक रूपांतरण

![Transformation](https://media.giphy.com/media/4H5nOUqX7FywOGpCF7/giphy.gif)

गणितीय कार्यों में संख्यात्मक रूपांतरण होता है⚙️ और अभिव्यक्तियाँ।

```jsx live
function learnJavaScript() {
  let value = '6' / '2'

  return value
}
```

हम फ़ंक्शन का उपयोग कर सकते हैं `Number(value)`, स्पष्ट रूप से परिवर्तित करने के लिए `value` संख्या के लिए 👇 :

```jsx live
function learnJavaScript() {
  let str = '123'
  let num = Number(str)

  return typeof num
}
```

स्पष्ट रूपांतरण का उपयोग अक्सर तब किया जाता है जब हम स्ट्रिंग संदर्भ से संख्या प्राप्त करने की अपेक्षा करते हैं, उदाहरण के लिए टेक्स्ट से 📜 फार्म फ़ील्ड।

यदि स्ट्रिंग को स्पष्ट रूप से किसी संख्या में नहीं डाला जा सकता है, तो रूपांतरण परिणाम होगा `NaN` (अंग्रेज़ी Not-a-Number, "नंबर नहीं"). उदाहरण के लिए 👇:

```jsx live
function learnJavaScript() {
  let age = Number('किसी संख्या के बजाय कोई स्ट्रिंग')

  return age
}
```

### संख्यात्मक रूपांतरण नियम:

| मूल्य         |                                                                           इसमें बदला गया…                                                                           |
| ---------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| `undefined`      |                                                                                `NaN`                                                                                 |
| `null `          |                                                                                 `0`                                                                                  |
| `true` / `false` |                                                                              `1` / `0`                                                                               |
| `string`         | किनारों पर सफेद जगह काट दी गई है। इसके अलावा, यदि एक खाली स्ट्रिंग बनी रहती है, तो हमें 0 मिलता है, अन्यथा एक गैर-रिक्त स्ट्रिंग से एक संख्या "रीड" होती है। त्रुटि पर🙅‍♂️ परिणाम NaN. |

उदाहरण:

```javascript
Number('   123   ') // 123
Number('123z') // NaN (किसी वर्ण के स्थान पर किसी संख्या को पढ़ने में त्रुटि "z")
Number(true) // 1
Number(false) // 0
Number(null) // 0
Number(undefined) // NaN
```

कृपया ध्यान दें कि `null` तथा `undefined` अलग व्यवहार करें। इसलिए, `null` शून्य हो जाता है, जबकि `undefined` शेष बचा `NaN`.

### बूलियन परिवर्तन

![Transformation](https://media.giphy.com/media/JjAdpCxrdro7m/giphy.gif)

तार्किक परिवर्तन सबसे सरल है। तार्किक संचालन में होता है, लेकिन फ़ंक्शन का उपयोग करके स्पष्ट रूप से भी किया जा सकता है⚙️ `Boolean(value)`.

### बूलियन रूपांतरण नियम:

मूल्य जो सहज हैं "खाली", पसंद `0`, खाली लाइन, `null`, `undefined` तथा `NaN`, बनना `false`. अन्य सभी मूल्य बन जाते हैं `true`.

```javascript
Boolean(1) // true
Boolean(0) // false
Boolean('नमस्ते!') // true
Boolean('') // false
```

:::caution ध्यान दें कि शून्य के साथ एक रेखा "0" — यह है true
कुछ भाषाएं👅 (उदाहरण के लिए, PHP) स्ट्रिंग को समझें `"0"` जैसा `false`. लेकीन मे JavaScript, यदि स्ट्रिंग खाली नहीं है, तो यह हमेशा है `true`

:::

```javascript
Boolean('0') // true
Boolean(' ') // इसे भी जगह दें true (यदि स्ट्रिंग खाली नहीं है, तो यह हमेशा है true)
```

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## प्रशन:

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

स्ट्रिंग रूपांतरण के लिए आपको किस फ़ंक्शन का उपयोग करना चाहिए?

1.  `String(value)`
2.  `Boolean(value)`
3.  `Number(value)`

टाइपकास्टिंग क्या है?

1. डेटा को एक प्रकार से दूसरे प्रकार में स्थानांतरित करना
2. मूल्यों को एक डेटा प्रकार से दूसरे में परिवर्तित करना
3. एक स्ट्रिंग के रूप में कुछ का प्रतिनिधित्व करना

टाइपकास्टिंग और टाइपकास्टिंग के बीच महत्वपूर्ण अंतर क्या है?

1. टाइप कास्टिंग स्पष्ट है, और प्रकार रूपांतरण निहित है
2. टाइप कास्टिंग निहित है, और प्रकार रूपांतरण स्पष्ट है
3. प्रकार रूपांतरण निहित है, और प्रकार रूपांतरण स्पष्ट और निहित दोनों हो सकता है

किस स्थिति में परिवर्तन का परिणाम होगा `NaN`?

1. जब एक स्ट्रिंग को स्पष्ट रूप से किसी संख्या में नहीं डाला जा सकता है
2. जब किसी संख्या को स्पष्ट रूप से स्ट्रिंग में नहीं डाला जा सकता है
3. जब कोड में कोई त्रुटि हो

परिवर्तित होने पर "खाली" मान क्या बन जाते हैं?

1.  `null`
2.  `true`
3.  `false`

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल।

![Sumerian school](/img/app.jpg)

## कड़ियाँ:

1. [MDN web docs - कास्ट](https://developer.mozilla.org/ru/docs/Словарь/Type_coercion)
2. [ टीन्स के लिए: प्रोग्रामिंग के लिए बिल्कुल सही शुरुआती गाइड, खंड १: Javascript - Jeremy Moritz ](https://www.amazon.com/Code-Teens-Beginners-Programming-Javascript-ebook/dp/B07FCTLVPC)
3. [JavaScript.ru](https://learn.javascript.ru/ifelse#blok-else)
4. [पूर्णांक अंकगणितи](https://maths-public.ru/arithmetic/actions)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<table>
  <tr>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /> <a href="https://github.com/gHashTag/react-native-village/commits?author=gHashTag" title="Documentation">📖</a><a href="#financial-gHashTag" title="Financial">💵</a></td>
    <td align="center"><a href="https://github.com/Resoner2005"><img src="https://avatars1.githubusercontent.com/u/75675814?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Resoner2005</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/issues?q=author%3AResoner2005" title="Bug reports">🐛 🎨 🖋</a></td>
  </tr>
  
</table>

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)

---
id: javascript06
title: स्ट्रिंग्स
sidebar_label: स्ट्रिंग्स
---

import YouTube from 'react-youtube'

![@serverSerrverlesskiy](/img/javascript/headers/06.jpg)

में JavaScript कोई भी पाठ 📜 डेटा तार है। हालांकि, यह मत भूलो कि संख्याओं को एक स्ट्रिंग में भी लिखा जा सकता है। सभी डेटा प्रकारों में से, आप शायद स्ट्रिंग्स का सबसे अधिक उपयोग करेंगे। हम बनाने के सभी विकल्पों का विश्लेषण करेंगे🏗️ नई पंक्ति।

## वीडियो

<YouTube videoId="ocQTm9K2vdo" />

## सिंगल या डबल कोट्स

![quotation marks](https://media.giphy.com/media/7cSTvZ4hI6ABZkcTwk/giphy.gif)

बनाने के लिए🏗️ तार या तो 'सिंगल' या "डबल" कोट्स का उपयोग करते हैं।

```jsx
let single = 'Hello World'
let double = "Hello World" // prettier-ignore
```

आप दोनों का उपयोग कर सकते हैं, मुख्य बात यह है कि यदि आप एक एकल के साथ एक पंक्ति शुरू करते हैं, हालांकि अंदर डबल्स हो सकते हैं, यह भी एक एकल के साथ पूरा होना चाहिए। और, तदनुसार, दोहरे उद्धरण चिह्नों के साथ।

```jsx
let double = "Don't you think so, d'Artagnan?"
let single = '"I think so, indeed!" - cried he.'
```

## बैकस्लैश

![shielding](https://media.giphy.com/media/3og0IPizf4zPR6VMt2/giphy.gif)

यदि समान उद्धरण स्ट्रिंग के अंदर बाहर की तरह उपयोग किए जाते हैं, तो उन्हें बैकस्लैश - तथाकथित "एस्केप कैरेक्टर" का उपयोग करके बच जाना चाहिए। इसे जोड़ा जाता है ➕ एक उद्धृत स्ट्रिंग से पहले `\'`, ताकि यह रेखा के अंत को चिह्नित न करे।
```jsx live
// prettier-ignore
function learnJavaScript() {
  let backticks = 'It\'s not complicated'
  return backticks
}
```

ध्यान दें कि बैकस्लैश `\` दुभाषिया द्वारा केवल स्ट्रिंग के सही पढ़ने के लिए कार्य करता है, लेकिन यह लिखित नहीं है 🖊️ इसे पढ़ने के बाद लाइन में। जब एक स्ट्रिंग को रैम में सहेजा जाता है, तो इसे इसके साथ जोड़ा नहीं जाता है। ➕ प्रतीक `\`. आप निष्कर्षों में इसे स्पष्ट रूप से देख सकते हैं।

## पिछला उद्धरण

![Dollar](https://media.giphy.com/media/26BoCwvDEWXnGlLyM/giphy.gif)

स्ट्रिंग लिखने में, आप बिना बैकस्लैश के \ _ बैक \ _ 'कोट्स का उपयोग करके कर सकते हैं।

सिंगल और डबल कोट्स अनिवार्य रूप से उसी तरह से काम करते हैं, और यदि आप बैक कोट्स का उपयोग करते हैं, तो हम मनमाना इंसर्ट कर सकते हैं  JavaScript घुंघराले ब्रेसिज़ के साथ एक डॉलर के चिह्न में लपेटकर अभिव्यक्तियां `${…}` 👇 :

```jsx live
function learnJavaScript() {
  const sum = (a, b) => a + b // यह एक समारोह है, हम इसे बाद में पता करेंगे
  return `1 + 2 = ${sum(1, 2)}`
}
```

बैकटिक्स का एक और फायदा यह है कि वे एक से अधिक लाइन फैला सकते हैं।

```jsx live
function learnJavaScript() {
  let guestList = `Guests:
    * John
    * Pete
    * Mary
   `
  return guestList
}
```

मल्टी-लाइन स्ट्रिंग्स भी बनाई जा सकती हैं🏗️ तथाकथित "लाइनफ़ीड" वर्ण का उपयोग करते हुए एकल और दोहरे उद्धरण चिह्नों का उपयोग करते हुए, जिसे `\ n` लिखा जाता है। सभी विशेष पात्र Java Script, बैकस्लैश से शुरू करें `\` सच है, हम इसे ब्राउज़र कंसोल में देख सकते हैं(`LIVE EDITOR` सही ढंग से प्रदर्शित नहीं होता है)।

```jsx
let guestList = 'Guests:\n * John\n * Pete\n * Mary'

guestList // बहु-पंक्ति अतिथि सूची
```

![console](/img/javascript/12.png)

## तार अपरिवर्तनीय हैं

![Tree](https://media.giphy.com/media/YxlUxrYGw2w9y/giphy.gif)

लाइन सामग्री JavaScript बदला नहीं जा सकता। आप प्रतीक को बीच में लेकर उसे बदल नहीं सकते। एक बार लाइन बन जाने के बाद🏗️ — वह हमेशा के लिए ऐसी है।
आप बना सकते हैं🏗️ एक नई लाइन और इसे पुराने के बजाय उसी वेरिएबल में लिखें।

```jsx live
function learnJavaScript() {
  let str = 'Hi'
  str = 'P' + str[1] // स्ट्रिंग बदलें
  return str
}
```

## लोकप्रिय स्ट्रिंग विधियां

### दिशा और रेखा

![Length](https://media.giphy.com/media/Y1GK5MEiRa3OSVsxHK/giphy.gif)

संपत्ति `length` रिटर्न🔄 कोड की संख्या📟 स्ट्रिंग में मान।
```jsx live
function learnJavaScript() {
  let str = 'My\n'.length
  return str
}
```

ध्यान दें, `\n` — यह एक विशेष वर्ण है, इसलिए यहां सब कुछ सही है: स्ट्रिंग की लंबाई 3.

### प्रतीकों तक पहुंच

![Door](https://media.giphy.com/media/xUA7aLpVxPVEoEPXji/giphy.gif)

वहाँ दो हैं 2️⃣ एक स्ट्रिंग में एक विशिष्ट चरित्र को पाने का एक तरीका। पहली विधि विधि का उपयोग करती है `charAt()`. प्रथम 1️⃣ चरित्र शून्य की स्थिति में है:

```jsx live
function learnJavaScript() {
  let str = 'cat'.charAt(2)
  return str
}
```

आप वर्गाकार कोष्ठकों का उपयोग करके भी प्रतीक प्राप्त कर सकते हैं:

```jsx live
function learnJavaScript() {
  let str = 'cat'[2]
  return str
}
```

वर्गाकार कोष्ठक चरित्र प्राप्त करने का आधुनिक तरीका है, जबकि `charAt` मुख्य रूप से ऐतिहासिक कारणों से मौजूद है।

### पात्रों का मामला बदलना

![Capital letter](https://media.giphy.com/media/3orifcBbnezczHmU8g/giphy.gif)

स्ट्रिंग के अक्षरों को अपरकेस में बदलने के लिए, विधि का उपयोग करें `toUpperCase()`.

```jsx live
function learnJavaScript() {
  let str = 'Interface'.toUpperCase()
  return str
}
```

लोअरकेस में `toLowerCase()`

```jsx live
function learnJavaScript() {
  let str = 'Interface'.toLowerCase()
  return str
}
```

### एक स्ट्रिंग का संघटन (संयोजन)

![Chain](https://media.giphy.com/media/l3q2EOu4nu1D8uJKU/giphy.gif)

मौजूदा स्ट्रिंग्स से एक स्ट्रिंग बनाने के लिए, प्लस चिह्न का उपयोग करें `+` तार जोड़ने के लिए।

```jsx
let name = 'Mary '
let activity = 'drink tea'
let bio = 'Our guest ' + name + activity + '.'
bio // Our guest Mary drink tea.
```
इसलिए हम सबसे लोकप्रिय डेटा प्रकार से परिचित हुए JavaScript और इसके लिए सबसे अधिक इस्तेमाल की जाने वाली विधियाँ।

<!-- Теперь попробуйте построить строку сами.

```jsx live
function learnJavaScript() {
  let name = 'John'
  let age = '15'
  let country = 'USA'
  let enjoyment = 'trevel'
  let slogan = '"Don\'t worry, be happy!"'
  let bio =
    'My name is ' +
    name +
    '. I am ' +
    age +
    " years old. I'm from " +
    country +
    '. I like ' +
    enjoyment +
    ', and my slogan for life: ' +
    slogan +
    '.'
  bio
  return bio
}
```

И `+=` для присвоения с объединением.

```jsx live
function learnJavaScript() {
  let str = '123'
  str += 456
  return str
}
``` -->

इसलिए हम सबसे लोकप्रिय डेटा प्रकार से परिचित हुए JavaScript और इसके लिए सबसे अधिक इस्तेमाल की जाने वाली विधियाँ।

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## प्रशन:

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

कैसे JavaScript पंक्तियाँ नहीं लिखी हैं?

1. सिंगल कोट्स में
2. बैकस्लैश में
3. बैक कोट्स में

स्ट्रिंग में बैकस्लैश का उपयोग क्यों नहीं किया जाता है?

1. परिरक्षण के लिए
2. विशेष वर्ण लिखने के लिए
3. लाइन खत्म करने के लिए

त्रुटि के साथ रेखा खोजें🙅‍♂️

1. let str = \`It's not complicated\`
2. let str ="'I think so, indeed!' - cried he."
3. let str = 'My slogan: "Don't worry, be happy!"'

"लाइन फीड कैरेक्टर" चुनें

1. `\n`
2. `\`
3. `\*`

यह कौन सा पत्र लौटाएगा `'sport'[3]`?

1. `o`
2. `r`
3. कुछ नहीं लौटाएगा

एक स्ट्रिंग में एक चरित्र को कैसे बदलें JavaScript?

1. लाइन बदलें
2. प्रतीक पर जाएं और इसे बदलें
3. एक नई लाइन बनाएं और इसे पुराने के बजाय उसी वेरिएबल में लिखें

अक्षरों को बड़ा करने के लिए किस विधि का प्रयोग किया जाता है?

1. `'Interface'.toUpperCase()`
2. `'Interface'[0].toLowerCase()`
3. `'Interface'.toLowerCase()`

तारों को जोड़ने के लिए किस वर्ण का प्रयोग किया जाता है?

1. `=`
2. `+`
3. `+=`

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल।

![Sumerian school](/img/app.jpg)

## कड़ियाँ:

1. [MDN web docs](https://developer.mozilla.org/ru/docs/Web/JavaScript/Data_structures)
2. [किशोरों के लिए कोड: प्रोग्रामिंग के लिए एकदम सही शुरुआती गाइड, खंड १: Javascript - Jeremy Moritz ](https://www.amazon.com/Code-Teens-Beginners-Programming-Javascript-ebook/dp/B07FCTLVPC)
3. [JavaScript.ru](https://learn.javascript.ru/types)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/Alena-Maitri"><img src="https://avatars1.githubusercontent.com/u/72432063?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Alena Yanbukhtina</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/commits?author=Alena-Maitri" title="Documentation">📖</a></td>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /><a href="#financial-gHashTag" title="Financial">💵</a></td>
    <td align="center"><a href="https://github.com/Resoner2005"><img src="https://avatars1.githubusercontent.com/u/75675814?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Resoner2005</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/issues?q=author%3AResoner2005" title="Bug reports">🐛 🎨 🖋</a></td>
  </tr>
  
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)

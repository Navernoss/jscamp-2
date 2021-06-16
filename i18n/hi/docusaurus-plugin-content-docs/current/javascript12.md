---
id: javascript12
title: ब्लॉक स्कोप
sidebar_label: ब्लॉक स्कोप
---

![@serverSerrverlesskiy](/img/javascript/headers/12.jpg)

दृश्यता का क्षेत्र (अंग्रेज़ी Scope) - प्रोग्राम का वह भाग जिसमें चर उपयोग के लिए उपलब्ध है।
 बनाते समय🏗️ `.js` फ़ाइल हम बनाते हैं🏗️ संपूर्ण फ़ाइल का दायरा, बनाने के लिए🏗️ आंतरिक दायरा, आपको घोषित करने की आवश्यकता है🗣️ यह घुंघराले ब्रेसिज़ के साथ `{ ... }`.

![file](https://media.giphy.com/media/3o6Ztk7NosfLVRqcpy/giphy.gif)

```jsx
// पहला दायरा
let fruit = 'Banana'
{
  // दूसरा दायरा
  let fruit = 'Apple'
  {
    // तीसरा दायरा
    let fruit = 'Lime'
  }
}
```

इस उदाहरण में, हमने बनाया है🏗️ विभिन्न क्षेत्रों में तीन चर जिनमें चर का अपना संस्करण होता है `fruit`, इसलिए त्रुटियां🙅‍♂️ नहीं होता है, लेकिन अगर आप बनाने की कोशिश करते हैं🏗️ एक ही नाम के दो चर, फिर एक त्रुटि होगी🙅‍♂️.

```jsx
// पहला दायरा
let fruit = 'Banana'
{
  // दूसरा दायरा
  let fruit = 'Apple'
  let fruit = 'Lime' // यहां एक त्रुटि होगी
}
```

बनाते समय🏗️ विभिन्न डिज़ाइन जो आप भी बनाते हैं🏗️ और इस निर्माण का दायरा, क्योंकि आप घुंघराले ब्रेसिज़ के ब्लॉक का उपयोग कर रहे हैं `{ ... }`.

```jsx
if (true) {
  // सशर्त बयान गुंजाइश
}

for (let i = 0; i > 5; i++) {
  // लूप स्कोप
}

function test() {
  // फंक्शन स्कोप
}
```

इन उदाहरणों में, प्रत्येक निर्माण का अपना दायरा होता है।

## वैश्विक कार्यक्षेत्र

![Global](https://media.giphy.com/media/l0MYPsBLOYyFqSDte/giphy.gif)

जब हम ग्लोबल स्कोप कहते हैं, तो हमारा मतलब है कि अन्य सभी स्कोप इसी के बच्चे हैं। वैश्विक दायरे में घोषित चर शामिल हैं🗣️ सभी कार्यों के बाहर⚙️ और ब्लॉक।

```jsx
// वैश्विक कार्यक्षेत्र
let fruit = 'Banana'
```

परिवर्तनशील 🔔 वैश्विक दायरे में निर्मित को कहा जाता है `वैश्विक चर` 🔔 . वैश्विक चर 🔔 सभी बाल क्षेत्रों में इस्तेमाल किया जा सकता है।

```jsx live
function learnFavaScript() {
  // परिवर्तनशील fruit वैश्विक है
  let fruit = 'Banana'
  function showFruit() {
    // इसलिए, हम इसे फ़ंक्शन के अंदर उपयोग कर सकते हैं
    return fruit
  }
  return showFruit()
}
```

## स्थानीय दायरा

![Local](https://media.giphy.com/media/VFwRCi6WKBUk08fliV/giphy.gif)

स्थानीय दायरे में घोषित चर शामिल हैं🗣️ कोड के एक निश्चित भाग में📟 . उदाहरण के लिए, बनाए गए चर🏗️ लूप के अंदर स्थानीय होगा।

```jsx
for (let i = 0; i > 5; i++) {
  // परिवर्तनशील i स्थानीय है
}
```

स्थानीय चर का प्रयोग करें 🔔 केवल उस ब्लॉक के अंदर संभव है जिसमें उन्हें घोषित किया गया था।

```jsx
function learnFavaScript() {
  function showFruit() {
    // परिवर्तनशील fruit स्थानीय है
    let fruit = 'Banana'
  }
  // इसलिए, हम इसे फ़ंक्शन के बाहर उपयोग नहीं कर सकते।
  return fruit
}

// ReferenceError: fruit is not defined
```

## के उदाहरण

![Math](https://media.giphy.com/media/xT1Ra5h24Eliux3UVq/giphy.gif)

दो चर का उपयोग करना 🔔 विभिन्न क्षेत्रों में एक ही नाम के साथ। समारोह `otherFruit()` एक चर देता है 🔔 `fruit` उस दायरे से जिसमें इसे प्रारंभ किया गया है `Lime`

```jsx live
function learnJavaScript() {
  let fruit = 'Banana'
  function otherFruit() {
    let fruit = 'Lime'
    return fruit
  }
  return otherFruit() + ' and ' + fruit
}
```

अगर हम छीन लेते हैं `let` समारोह से `otherFruit()`, फिर एक चर बनाने के बजाय 🔔 हम इसे फिर से लिखते हैं 🖊️.

```jsx live
function learnJavaScript() {
  let fruit = 'Banana'
  function otherFruit() {
    fruit = 'Lime'
    return fruit
  }
  return otherFruit() + ' and ' + fruit
}
```

क्या होगा यदि हम स्थानीय चर को कॉल करने का प्रयास करें 🔔 माता-पिता के दायरे में? इस तथ्य के कारण त्रुटि उत्पन्न होती है कि हम वैश्विक दायरे में एक चर को कॉल करने का प्रयास कर रहे हैं 🔔 , जो हमने नहीं बनाया।

```javascript
function learnJavaScript() {
  let num
  for (let i = 0; i != 5; i++) {
    num += i
  }
  return i
}

//ReferenceError: i is not defined
```

![Primer](https://media.giphy.com/media/M33UV4NDvkTHa/giphy.gif)

## पर प्रतिबंध var

![eye](https://media.giphy.com/media/PKl9JTqnoiKtO/giphy.gif)

लेख [खुले पैसे](https://react-native-village.github.io/docs/javascript03) हमने आपको इस्तेमाल करने के लिए कहा था `var` हम नहीं करेंगे, यह सिर्फ दायरे से जुड़ा है।

1. यदि एक ही दायरे में आप दो चर बनाते हैं 🔔 एक कीवर्ड का उपयोग करके एक नाम के साथ `let` या `const`, तब दुभाषिया एक त्रुटि प्रदर्शित करके हमें इसके बारे में चेतावनी देता है।

```jsx
function learnJavaScript() {
  let fruit = 'Banana'
  let fruit = 'Lime'
  return fruit
  // SyntaxError: Identifier 'fruit' has already been declared
}
```

लेकिन, अगर उपयोग कर रहे हैं `var` आप चर बनाएंगे 🔔 उसी नाम से, वह उसे फिर से सौंप देगा।

```jsx live
function learnJavaScript() {
  var fruit = 'Banana'
  var fruit = 'Lime'
  return fruit
}
```

त्रुटियां🙅‍♂️ उत्पन्न नहीं होता, क्योंकि `var` चर को अधिलेखित कर दिया `fruit`

2. एक वैश्विक चर बनाकर 🔔 के जरिए `var` हम इसे एक और चर बनाकर स्थानीय दायरे से बदल सकते हैं 🔔 एक ही नाम का उपयोग कर `var`. क्षेत्र `var` किसी फ़ंक्शन या स्क्रिप्ट तक सीमित।

```jsx live
function learnJavaScript() {
  var fruit = 'Lime'
  {
    var fruit = 'Banana'
  }
  return fruit
}
```

3. चर 🔔 के साथ बनाया गया `var` स्क्रिप्ट लॉन्च की शुरुआत से ही घोषित माना जाता है, भले ही घोषणा कहां स्थित हो।

```jsx live
function learnJavaScript() {
  fruit = 'Banana'
  var fruit
  return fruit
}
```

4. में JavaScript इससे पहले ES6 कोई ब्लॉक स्कोप नहीं थे। वो। कीवर्ड का उपयोग करके बनाया गया कोई भी चर `var` ब्लॉक के अंदर और उसके बाहर दिखाई देगा।

```javascript
if (true) {
  var fruit = 'Apple' // वेरिएबल इस ब्लॉक के बाहर दिखाई देगा
}
console.log(fruit) // "Apple"
```

![javascript](/img/javascript/28.jpg)

```javascript
if (true) {
  let fruit = 'Apple' // वेरिएबल इस ब्लॉक के बाहर दिखाई नहीं देगा
}
console.log(fruit) // "Apple"
```

![javascript](/img/javascript/29.jpg)

सूचीबद्ध कारणों से, डेवलपर्स ने उपयोग करने से इनकार कर दिया `var`

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या टेलीग्राम [चैट](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## सवाल और जवाब

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

हम सबसे पहला दायरा कब बनाते हैं?

1. चक्र बनाते समय
2. फ़ाइल बनाते समय
3. ब्लॉक बनाते समय

एक सशर्त बयान बनाते समय, एक नया दायरा बनाया जाता है?

1. हाँ
2. नहीं

स्थानीय चर कहाँ बनाया गया है?

1. कोड के एक निश्चित भाग में
2. सभी ब्लॉकों के बाहर

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल में।

![Sumerian school](/img/app.jpg)

## लिंक

1. [JavaScript Scope](https://css-tricks.com/javascript-scope-closures/)
2. [Learn JavaScript](https://learn.javascript.ru/closure)
3. [MDN Web Docs](https://developer.mozilla.org/ru/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr> 
    <td align="center"><a href="https://github.com/IIo3iTiv"><img src="https://avatars1.githubusercontent.com/u/72025062?v=4?s=200" width="200px;" alt=""/><br /><sub><b>IIo3iTiv</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/commits?author=IIo3iTiv" title="Documentation">📖</a></td>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /><a href="#financial-gHashTag" title="Financial">💵</a></td>
    <td align="center"><a href="https://github.com/Resoner2005"><img src="https://avatars1.githubusercontent.com/u/75675814?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Resoner2005</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/issues?q=author%3AResoner2005" title="Bug reports">🐛 🎨 🖋</a></td>
    <td align="center"><a href="https://github.com/Navernoss"><img src="https://avatars0.githubusercontent.com/u/75784137?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Navernoss</b></sub></a><br /><a href="#content-Navernoss" title="Content">🖋 🐛 🎨 </a></td>
  </tr>
  
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)

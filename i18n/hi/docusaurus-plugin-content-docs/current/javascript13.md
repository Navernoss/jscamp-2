---
id: javascript13
title: डिफ़ॉल्ट पैरामीटर
sidebar_label: डिफ़ॉल्ट पैरामीटर
---

![@serverSerrverlesskiy](/img/javascript/headers/25.jpg)

डिफ़ॉल्ट पैरामीटर आपको फ़ंक्शन के पैरामीटर सेट करने की अनुमति देते हैं⚙️ डिफ़ॉल्ट मान यदि फ़ंक्शन⚙️ को तर्कों के बिना कहा जाता है, या यदि पैरामीटर स्पष्ट रूप से एक मान पारित किया गया है `undefined`.

![Teacher](https://media.giphy.com/media/3ohc10nduj1irsuzgA/giphy.gif)

में JavaScript फ़ंक्शन पैरामीटर⚙️, जो कॉल किए जाने पर पास किए गए मान नहीं हैं, डिफ़ॉल्ट मान लेते हैं
`undefined`. हालाँकि, कुछ मामलों में भिन्न डिफ़ॉल्ट मान सेट करना उपयोगी हो सकता है। यह वह जगह है जहाँ डिफ़ॉल्ट विकल्प का इरादा है।

## वाक्य - विन्यास

![book](https://media.giphy.com/media/l0HlOBZcl7sbV6LnO/giphy.gif)

```jsx live
function learnJavaScript() {
  const multiply = (a, b = 1) => {
    //डिफ़ॉल्ट मान у b समान रूप से 1
    return a * b
  }
  //यदि एक b होगा undefined, तो इसे एक डिफ़ॉल्ट मान सौंपा जाएगा
  return multiply(5, 2) // अल्पविराम हटा दें, दूसरा तर्क और प्राप्त करें 5 + 1
}
```

### अन्य "झूठे" मान पास करना

![basketball](https://media.giphy.com/media/3oEdv5e5Zd2gsczAhG/giphy.gif)

यदि के अलावा कोई मूल्य `undefined`, इनमें से एक सहित "गलत" मान, जैसे कि false ❎ , `0`, `""`, `''`,`null`, `NaN`, इस मामले में, डिफ़ॉल्ट मान पैरामीटर को असाइन नहीं किया जाएगा। इस मामले में, आपको खुद को निर्धारित करने की आवश्यकता है 🖊️ कोड जो इन्हें पकड़ लेगा "झूठे मूल्य".

## के उदाहरण

![Math](https://media.giphy.com/media/xT1Ra5h24Eliux3UVq/giphy.gif)

डिफ़ॉल्ट मापदंडों में, आप पिछले (सूची में बाईं ओर स्थित) मापदंडों के मूल्यों का उपयोग कर सकते हैं:

```jsx live
function learnJavaScript() {
  const greet = (name, greeting, message = greeting + ' ' + name) => {
    return [name, greeting, message]
  }

  return greet('David ', 'Hi ')
}
```

डिफ़ॉल्ट पैरामीटर के साथ और बिना फ़ंक्शन का एक उदाहरण 👇 :

```jsx live
function learnJavaScript() {
  const withDefaults = (a = 1, b = 3, c = 2) => {
    //डिफ़ॉल्ट मापदंडों के साथ कार्य
    return [a, b, c]
  }
  const withoutDefaults = (a, b, c) => {
    //डिफ़ॉल्ट मापदंडों के बिना कार्य
    if (a == undefined) {
      a = 1
    }
    if (b == undefined) {
      b = 3
    }
    if (c == undefined) {
      c = 2
    }
    return [a, b, c]
  }

  return withDefaults()
}
```

परिणाम वही होगा, लेकिन डिफ़ॉल्ट पैरामीटर के बिना, कोड📟 काफ़ी बड़ा हो सकता है।

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## प्रशन:

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

यदि फ़ंक्शन पैरामीटर⚙️ कोई मूल्य पारित नहीं हुआ, वे डिफ़ॉल्ट रूप से किस मूल्य को स्वीकार करते हैं?

1. `null`
2. `undefined`
3. `NaN`

क्या डिफ़ॉल्ट पैरामीटर झूठे मानों को "पकड़" लेते हैं?

1. हाँ
2. नहीं

क्या डिफ़ॉल्ट मापदंडों में सूची के बाईं ओर स्थित मापदंडों के मूल्यों का उपयोग करना संभव है?

1. हाँ
2. नहीं

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल।

![Sumerian school](/img/app.jpg)

## कड़ियाँ:

1.  [MDN web docs](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Functions/Default_parameters)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/FELiX-RN"><img src="https://avatars0.githubusercontent.com/u/72006627?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Philipp Dvinyaninov</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/commits?author=FELiX-RN" title="Documentation">📖</a></td>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /><a href="#financial-gHashTag" title="Financial">💵</a></td>
    <td align="center"><a href="https://github.com/Resoner2005"><img src="https://avatars1.githubusercontent.com/u/75675814?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Resoner2005</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/issues?q=author%3AResoner2005" title="Bug reports">🐛 🎨 🖋</a></td>
    <td align="center"><a href="https://github.com/Navernoss"><img src="https://avatars0.githubusercontent.com/u/75784137?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Navernoss</b></sub></a><br /><a href="#content-Navernoss" title="Content">🖋 🐛 🎨 </a></td>
  </tr>
  
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)

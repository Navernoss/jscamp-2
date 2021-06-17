---
id: javascript15
title: डिज़ाइन switch case
sidebar_label: डिज़ाइन switch case
---

![@serverSerrverlesskiy](/img/javascript/headers/14.jpg)

डिज़ाइन `switch` विभिन्न विकल्पों के साथ समानता के लिए मूल्यों की तुलना करने के लिए उपयोग किया जाता है।

इस मामले में, ऑपरेटर के अर्थ में समानता निहित है सख्त समानता `===`, रेगेक्स या जो कुछ भी के साथ तुलना करें `switch` नही सकता। अर्थात् समानता धारण करने के लिए मान एक ही प्रकार के होने चाहिए।

![comparison](https://media.giphy.com/media/icJA0VF7ntoEL18Jez/giphy.gif)

यदि स्थिति मेल खाती है, तो कोड ब्लॉक निष्पादित किया जाता है📟 , संबंधित के साथ जुड़े `case`. यदि कोई भी शर्त मेल नहीं खाती है, तो कोड निष्पादित किया जाता है📟 , ब्लॉक में निर्दिष्ट `default`, अगर वह है। निर्माण से बाहर निकलने के लिए, कमांड का उपयोग करें `break`. यदि आप इसे निर्दिष्ट नहीं करते हैं, तो कोड ब्लॉक स्वचालित रूप से निष्पादित हो जाएगा।📟 अगले में `case` आदि। इसलिये `break` हम इसे अपनी लिपियों में उपयोग करते हैं, ताकि दुभाषिया को पूरी तरह से न चलाया जा सके `case` जिससे स्क्रिप्ट का प्रदर्शन कम हो जाता है।

## वाक्य - विन्यास

![Syntax](https://media.giphy.com/media/yR4xZagT71AAM/giphy.gif)

डिज़ाइन `switch` एक या अधिक ब्लॉक हैं `case` और एक वैकल्पिक ब्लॉक `default`.

यह इस तरह दिख रहा है:

```jsx
switch (n) {
  case 1:
    // कोड ब्लॉक 1;
    break
  case 2:
    // कोड ब्लॉक 2;
    break
  // .......
  // अन्य विकल्प  case
  // .......
  default:
  // कोड का ब्लॉक यदि कोई भी शर्त मेल नहीं खाती;
}
```

`n` - यह बूलियन है [boolean](https://react-native-village.github.io/docs/javascript08) स्थिति।

## के उदाहरण

![Math](https://media.giphy.com/media/xT1Ra5h24Eliux3UVq/giphy.gif)

आइए सबसे सरल उदाहरण देखें 👇 :

```jsx live
function learnJavaScript() {
  let a = 4
  let str
  switch (a) {
    case 3:
      str = 'थोड़ा सा'
      break
    case 4:
      str = 'बिल्कुल सही!'
      break
    case 5:
      str = 'पाशविक बल'
      break
    default:
      str = 'मैं ऐसे मूल्यों को नहीं जानता'
  }
  return str
}
```

यहाँ ऑपरेटर `switch` लगातार तुलना करें `a` से सभी विकल्पों के साथ `case`.
प्रथम `3`, तब - चूंकि कोई मेल नहीं है – `4`. एक मैच मिला, इस विकल्प को लाइन से निष्पादित किया जाएगा `str = 'बिल्कुल सही!'` और आगे, निकटतम के लिए `break`, जो निष्पादन को रोक देगा।

![Wow](https://media.giphy.com/media/3oriO13KTkzPwTykp2/giphy.gif)

इस उदाहरण पर विचार करें 👇 :

```jsx live
function learnJavaScript() {
  let a = 'Apples'
  let str
  switch (a) {
    case 'Apples':
      str = 'I love ' + a
      break
    case 'Oranges':
      str = 'I love ' + a
      break
    case 'Bananas':
      str = 'I love ' + a
      break
    default:
      str = 'I like other fruits'
  }
  return str
}
```

यहाँ ऑपरेटर `switch` लगातार तुलना करें `a` से सभी विकल्पों के साथ `case`. लेकिन यह संख्याओं की तुलना नहीं है, बल्कि तारों की है। यह किसी भी डेटा प्रकार के साथ किया जा सकता है, जब तक कि समान डेटा प्रकारों की तुलना की जाती है।

## प्रतिस्थापन `if`

भी `Switch` एकाधिक को बदलने के लिए उपयोग किया जाता है `if`.

उदाहरण के लिए, आप इस कोड को बदल सकते हैं 👇 :

```jsx live
function learnJavaScript() {
  let number = 2
  let str
  if (number === 0) {
    str = 'आपने नंबर दर्ज किया 0'
  }

  if (number === 1) {
    str = 'आपने नंबर दर्ज किया 1'
  }

  if (number === 2 || number === 3) {
    str = 'आपने नंबर 2 दर्ज किया है, या शायद 3'
  }
  return str
}
```

उस पर 👇 :

```jsx live
function learnJavaScript() {
  let number = 2
  let str
  switch (number) {
    case 0:
      str = 'आपने नंबर दर्ज किया 0'
      break

    case 1:
      str = 'आपने नंबर दर्ज किया 1'
      break

    case 2:
    case 3:
      str = 'आपने नंबर दर्ज किया 2, हो सकता है 3'
      break
  }
  return str
}
```

परिणाम वही होगा, लेकिन कोड📟 अधिक पठनीय और काम करने में आसान हो जाएगा।

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

Пишите в [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## सवाल और जवाब:

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

क्या यह मदद से संभव है `switch` नियमित अभिव्यक्तियों के साथ कुछ तुलना करें?

1. हाँ
2. नहीं

कौन सा तुलना ऑपरेटर उपयोग कर रहा है `switch`?

1. `=`
2. `===`
3. `==`

कौन सा कीवर्ड तुलना प्रक्रिया को रोकता है `switch`?

1. `break`
2. `stop`
3. `default`

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल।

![Sumerian school](/img/app.jpg)

## कड़ियाँ:

1.  [MDN web docs](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Statements/switch)
2.  [Learn JavaScript](https://learn.javascript.ru/switch)
3.  [निर्देशिका JavaScript](https://javascript.ru/switch)

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

---
id: javascript14
title: नियमित अभिव्यक्ति
sidebar_label: नियमित अभिव्यक्ति
---

![@serverSerrverlesskiy](/img/javascript/headers/13.jpg)

नियमित अभिव्यक्ति (अंग्रेज़ी _regular expressions_) — औपचारिक भाषा👅 टेक्स्ट में स्ट्रिंग्स को खोजना और उनमें हेरफेर करना 📜 , मेटाकैरेक्टर के उपयोग के आधार पर।

नियमित अभिव्यक्ति आपको इसकी अनुमति देती है:

- एक स्ट्रिंग में टेक्स्ट खोजें
- सबस्ट्रिंग को एक स्ट्रिंग में बदलें
- एक स्ट्रिंग से जानकारी निकालें

![search](https://media.giphy.com/media/l46Cy1rHbQ92uuLXa/giphy.gif)

JavaScript, साथ ही साथ Perl, यह भाषाओं में से एक है👅 प्रोग्रामिंग जिसमें नियमित अभिव्यक्तियों के लिए समर्थन सीधे भाषा में बनाया जाता है👅.

## उपयोग करने में कठिनाई

![the complexity of using](https://media.giphy.com/media/5XYsIwzY00ONq/giphy.gif)

रेगुलर एक्सप्रेशन का नुकसान यह है कि वे अक्सर अजीब और डराने वाले लगते हैं। यह अधिक जटिल टेम्पलेट्स के लिए विशेष रूप से सच है।

```jsx
let regExp = /^[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/
```

## नियमित अभिव्यक्तियों को परिभाषित करना

![search](https://media.giphy.com/media/RMwYOO5e8pr1lhL8K7/giphy.gif)

रेगुलर एक्सप्रेशन की परिभाषा क्रिएशन है🏗️ वह टेम्प्लेट जिसके आधार पर स्ट्रिंग्स के साथ काम होगा। में JavaScript नियमित अभिव्यक्ति एक वस्तु है जिसे दो तरीकों से परिभाषित किया जा सकता है।

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs
defaultValue="literal"
values={[
{label: 'शाब्दिक', value: 'literal'},
{label: 'डिज़ाइन', value: 'construction'},
]
}>
<TabItem value="literal">

शाब्दिक का उपयोग करके नियमित अभिव्यक्तियों को परिभाषित करना। रेगुलर एक्सप्रेशन के लिए, स्लैश शाब्दिक हैं`/ ... /`, वे कोष्ठक के समान भूमिका निभाते हैं `' ... '` बनाते समय🏗️ लाइनें।

```jsx
let regExp = /टेम्पलेट/
```

यदि आप बनाने का निर्णय लेते हैं🏗️ शाब्दिक का उपयोग करते हुए नियमित अभिव्यक्ति, तो यह ध्यान में रखना चाहिए कि बनाने की ऐसी विधि🏗️ _गतिशील रूप से बदलते_ सेटपॉइंट की अनुमति नहीं देता है। यह इस तथ्य के कारण है कि जब स्क्रिप्ट को पार्स किया जाता है तो नियमित अभिव्यक्ति अक्षर _precompilation_ का कारण बनते हैं।

  </TabItem>
  <TabItem value="construction">

एक कंस्ट्रक्टर का उपयोग करके नियमित अभिव्यक्तियों को परिभाषित करना।

```jsx
let regExp = new RegExp('टेम्पलेट')
```

बनाई गई नियमित अभिव्यक्ति का संकलन🏗️ कंस्ट्रक्टर का उपयोग उस समय होता है जब स्क्रिप्ट निष्पादित होती है। बनाने का यह तरीका🏗️ यदि आपका रेगेक्स बनाया जा रहा है तो इसका उपयोग करने लायक है🏗️ गतिशील रूप से जेनरेट की गई स्ट्रिंग से।

  </TabItem>
</Tabs>

## का उपयोग करते हुए

![pressing the button](https://media.giphy.com/media/12hhLP67q6PqCs/giphy.gif)

आइए एक उदाहरण का उपयोग करके नियमित अभिव्यक्तियों के उपयोग को देखें:

```jsx
let regExp = /banana/
```

इस कोड के साथ📟 हमने बनाया🏗️ सरल रेगेक्स जो एक स्ट्रिंग की खोज करता है `banana`. रेगुलर एक्सप्रेशन का परीक्षण करने के लिए, आप विधि का उपयोग कर सकते हैं `.test(string)`, विधि का परिणाम है `boolean` मूल्य।

```jsx live
function learnJavaScript() {
  let regExp = /banana/,
    str = 'fanana ranana banana'
  return regExp.test(str) ? 'मिल गया' : 'नहीं न'
}
```

उदाहरण में, रेगेक्स एक सबस्ट्रिंग की खोज करता है `banana` इन - लाइन `str`.

## एंकर

![anchor](https://media.giphy.com/media/3ohze1LSWrEGCML02Y/giphy.gif)

एंकर एक पैटर्न को एक लाइन की शुरुआत या अंत में बाँधते हैं। एक पंक्ति की शुरुआत से जुड़ने के लिए, उपयोग करें - `^`, और अंत तक - `$`.

```jsx live
function learnJavaScript() {
  let regExp = /^banana/,
    str = 'lime banana orange'
  return regExp.test(str) ? 'मिल गया' : 'नहीं न'
}
```

इस तरह के एक टेम्पलेट का उपयोग करना `/banana/` आप देख रहे होंगे `banana` पूरी लाइन में। यदि आपको टेम्पलेट के साथ स्ट्रिंग के पूर्ण मिलान की जांच करने की आवश्यकता है, तो आपको एंकर का उपयोग करने की आवश्यकता है `/^banana$/`. तरीका `.test()` वापसी करेंगे `true` ✅ केवल अगर पूरी लाइन है `banana`.

## झंडे

![Flag](https://media.giphy.com/media/ihRmRCxJuIi3pCORTL/giphy.gif)

नियमित अभिव्यक्ति खोजों का विस्तार करने के लिए झंडे का उपयोग किया जाता है।

- `g` - खोजते समय, सभी मिलानों की खोज करता है;
- `i` - खोज केस असंवेदनशील है `[Z-z]`;
- `m` - मल्टीलाइन मोड;
- `s` - मोड चालू करता है **dotall**, किस बिंदु पर `.` एक लाइन फीड कैरेक्टर से मेल खा सकता है;
- `y` - संपत्ति की स्थिति पर चरित्र से शुरू होने वाली खोजें **lastindex** वर्तमान रेगेक्स;
- `u` - समर्थन शामिल है **Unicode**.

विभिन्न निर्माण विधियों के साथ झंडे का उपयोग करना🏗️ रेगेक्स पैटर्न
<Tabs
defaultValue="literal"
values={[
{label: 'शाब्दिक', value: 'literal'},
{label: 'डिज़ाइन', value: 'construction'},
]
}>
<TabItem value="literal">

```jsx
let regExp = /टेम्पलेट/झंडा // prettier-ignore
```

कृपया ध्यान दें कि झंडे हैं **अभिन्न अंग** नियमित अभिव्यक्ति। झंडे को बाद में जोड़ा या हटाया नहीं जा सकता। साथ ही झंडे भी जोड़े जा सकते हैं।

```jsx live
function learnJavaScript() {
  let regExp = /banana/i,
    str = 'faNana RanaNA BaNanA'
  return regExp.test(str) ? 'मिल गया' : 'नहीं न'
}
```

ध्वज को हटाने का प्रयास करें `i` उदाहरण से।
</TabItem>
<TabItem value="construction">

```jsx
let regExp = new RegExp('टेम्पलेट', 'झंडा')
```

कृपया ध्यान दें कि झंडे हैं **अभिन्न अंग** नियमित अभिव्यक्ति। झंडे को बाद में जोड़ा या हटाया नहीं जा सकता। साथ ही झंडे भी जोड़े जा सकते हैं।

```jsx live
function learnJavaScript() {
  let regExp = new RegExp('banana', 'i'),
    str = 'faNana RanaNA BaNanA'
  return regExp.test(str) ? 'मिल गया' : 'नहीं न'
}
```

ध्वज को हटाने का प्रयास करें `i` उदाहरण से। खोज अब केस-संवेदी है।
</TabItem>
</Tabs>

## संपूर्ण

विषय बहुत व्यापक है और हमारे द्वारा विकास में शायद ही कभी उपयोग किया जाता है, इसलिए यदि आप रुचि रखते हैं, तो आप इसके बारे में अधिक विस्तार से जान सकते हैं। [यहां,](https://learn.javascript.ru/regular-expressions)[ यहां](https://developer.mozilla.org/ru/docs/Web/JavaScript/Guide/Regular_Expressions)[ और यहाँ।](https://tuhub.ru/frontend/js-regexp)

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)
s

## सवाल और जवाब

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

रेगुलर एक्सप्रेशन किसके लिए हैं?

1. टेम्प्लेट बनाना
2. स्ट्रिंग हेरफेर
3. तार संपादित करना

रेगुलर एक्सप्रेशन को शाब्दिक रूप से बनाने के लिए किस वर्ण का उपयोग किया जाता है?

1. स्लैश `/`
2. बैकस्लैश `\`
3. वर्ग कोष्ठक `[]`

एक नियमित अभिव्यक्ति बनाने का तरीका क्या है जो दिए गए मूल्यों में और गतिशील परिवर्तन की अनुमति नहीं देता है?

1. शाब्दिक में
2. कंस्ट्रक्टर में
3. किसी भी विधि के साथ, गतिशील परिवर्तन की अनुमति है

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) उस विषय के बारे में हमारे कोला में।

![Sumerian school](/img/app.jpg)

## लिंक

1. [Learn JavaScript](https://learn.javascript.ru/regular-expressions)
2. [MDN Web Docs](https://developer.mozilla.org/ru/docs/Web/JavaScript/Guide/Regular_Expressions)
3. [JS RegExp](https://tuhub.ru/frontend/js-regexp)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<table>
  <tr> 
    <td align="center"><a href="https://github.com/IIo3iTiv"><img src="https://avatars1.githubusercontent.com/u/72025062?v=4?s=200" width="200px;" alt=""/><br /><sub><b>IIo3iTiv</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/commits?author=IIo3iTiv" title="Documentation">📖</a></td>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /><a href="#financial-gHashTag" title="Financial">💵</a></td>
    <td align="center"><a href="https://github.com/Resoner2005"><img src="https://avatars1.githubusercontent.com/u/75675814?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Resoner2005</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/issues?q=author%3AResoner2005" title="Bug reports">🐛 🎨 🖋</a></td>
    <td align="center"><a href="https://github.com/Navernoss"><img src="https://avatars0.githubusercontent.com/u/75784137?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Navernoss</b></sub></a><br /><a href="#content-Navernoss" title="Content">🖋 🐛 🎨 </a></td>
  </tr>
  
</table>

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)

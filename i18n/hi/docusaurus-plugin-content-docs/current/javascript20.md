---
id: javascript20
title: सरणियों और वस्तुओं को नष्ट करना
sidebar_label: सरणियों और वस्तुओं को नष्ट करना
---

![@serverSerrverlesskiy](/img/javascript/headers/30.jpg)

में विनाशकारी JavaScript यह एक असाइनमेंट सिंटैक्स है जो आपको एक पंक्ति में सरणियों और वस्तुओं से डेटा को आसानी से निकालने की अनुमति देता है।

## विनाशकारी वस्तुएं

![object](https://media.giphy.com/media/3o85xx7Yll3UyNVQf6/giphy.gif)

```jsx live
function learnJavaScript() {
  // एक वस्तु बनाएँ `fruit`
  let fruit = {
    title: 'banana',
    group: 'tropical',
    quantity: 5
  }

  // किसी वस्तु को नष्ट करना `fruit`
  let { title, group, quantity } = fruit

  // प्रदर्शित `title`
  return title
}
```

गुण `title`, `group` तथा `quantity`, वस्तु की संरचना को दोहराएं `fruit` और उनके मूल्यों को समान चर में कॉपी करें 🔔 में स्थित `{...}`. इसलिए, यदि आप चर बदलते हैं 🔔 में `{...}` स्थानों में, तो कोड ठीक उसी तरह काम करेगा, ऊपर के उदाहरण में चर बदलने का प्रयास करें 🔔 स्थान।

### नेस्टेड वस्तु

![bookmark](https://media.giphy.com/media/3og0IDyqVFNH7qFpAI/giphy.gif)

हम नेस्टेड वस्तु को भी नष्ट कर सकते हैं।

```jsx live
function learnJavaScript() {
  let fruit = {
    title: 'banana',
    group: 'tropical',
    quantity: {
      store: 5,
      storeHaus: 99
    }
  }

  let {
    title,
    quantity: { store: s1, storeHaus: s2 }
  } = fruit

  return title + ', ' + parseFloat(s1 + s2)
}
```

### दुसरे नाम

यदि आपको चर नामों का उपयोग करने की आवश्यकता है 🔔 गुणों के नाम से अलग, निम्नलिखित सिंटैक्स काम करेगा:

```jsx live
function learnJavaScript() {
  let fruit = {
    title: 'banana',
    group: 'tropical',
    quantity: 5
  }
  // title -> a; group -> b; quantity -> c
  let { title: a, group: b, quantity: c } = fruit

  return a
}
```

### डिफॉल्ट मान

मैं फ़िन `{...}` आप एक चर लिखेंगे 🔔 गुण जो नहीं मिलेंगे, फिर उसे मान दिया जाएगा `undefined`. एक चर निर्दिष्ट करने के लिए 🔔 डिफ़ॉल्ट मान, यह मान इसे असाइन किया जा सकता है। यदि आप किसी चर को मान निर्दिष्ट करने का प्रयास करते हैं 🔔 जिसके गुण पाए जाते हैं, तो उसे संपत्ति का मूल्य सौंपा जाएगा। आइए एक उदाहरण देखें।

![Dafault](https://media.giphy.com/media/3oEduLzte7jSNmq4z6/giphy.gif)

```jsx live
function learnJavaScript() {
  let fruit = {
    title: 'banana'
  }
  let { title = 'lime', group, quantity = 5 } = fruit

  return title + ', ' + group + ', ' + quantity
}
```

में `title` संपत्ति का मूल्य प्रदर्शित होता है, न कि वह जो हम उसे सौंपते हैं। गुण `group` सुविधा में `fruit` मौजूद नहीं है, लेकिन चर 🔔 हमने कोई मान निर्दिष्ट नहीं किया। गुण `quantity` भी मौजूद नहीं है, लेकिन परिवर्तनशील 🔔 हमने मान असाइन किया है `5`.

### शेष

![octatok](https://media.giphy.com/media/hvddF1vHatFIgQspUB/giphy.gif)

यदि आपको किसी वस्तु से एक चर प्राप्त करने की आवश्यकता है 🔔 , और बाकी को किसी अन्य ऑब्जेक्ट में समूहित करें, फिर उपयोग करें `...` चर से पहले 🔔 जिससे शेष गुणों वाली वस्तु बनाई जाएगी।

```jsx live
function learnJavaScript() {
  let fruit = {
    title: 'banana ',
    group: 'tropical ',
    quantity: 5
  }
  let { group, ...prop } = fruit

  return prop.title + group
}
```

## विनाशकारी सरणियाँ

किसी सरणी का विनाश किसी वस्तु के समान ही होता है। अंतर केवल इतना है कि सरणी तत्वों का मान चर को सौंपा जाएगा 🔔 जिस क्रम में तत्वों को परिभाषित किया गया है।

![Take](https://media.giphy.com/media/IuBlckSD7dQv6/giphy.gif)

```jsx live
function learnJavaScript() {
  // एक सरणी बनाएं `fruit`
  let fruit = ['banana', 'tropical', 5]

  // सरणी को नष्ट करना `fruit`
  let [title, group, quantity] = fruit

  // प्रदर्शित
  return `${title}, ${group}, ${quantity}`
}
```

### शेष

वस्तुओं के सादृश्य से, शेष कार्य करता है।

```jsx live
function learnJavaScript() {
  let fruit = ['banana ', 'tropical ', 5]

  let [name, ...prop] = fruit

  return `${name}, ${prop}`
}
```

### ऐरे कॉपी

सृजन का उदाहरण🏗️ सरणी की प्रतियां।

![Copia](https://media.giphy.com/media/GI1KnTxySlrCE/giphy.gif)

```jsx live
function learnJavaScript() {
  let fruit = ['banana ', 'tropical ', 5]

  let _fruit = [...fruit]

  return _fruit
}
```

### सरणियों का संयोजन

![add](https://media.giphy.com/media/3gMrhfFtWHq9XxtqPy/giphy.gif)

सरणियों को एक में मिलाने का एक उदाहरण।

```jsx live
function learnJavaScript() {
  let name = ['banana '],
    prop = ['tropical ', 5],
    fruit = [...name, ...prop]

  return fruit
}
```

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## प्रशन

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

विध्वंसक है?

1. समारोह
2. वाक्य रचना
3. वस्तु

क्या किसी वस्तु को नष्ट करते समय चरों को उसी क्रम में रखना आवश्यक है जिसमें वे वस्तु में हैं?

1. हाँ
2. नहीं

यदि वस्तु में कोई समान गुण नहीं मिलता है तो एक चर को क्या सौंपा जाएगा?

1. `error`
2. `undefined`
3. `unknown`

क्या किसी वस्तु के नष्ट होने पर तत्वों का क्रम महत्वपूर्ण है?

1. हाँ
2. नहीं

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल में।

![Sumerian school](/img/app.jpg)

## Ссылки

1. [Learn JavaScript](https://learn.javascript.ru/destructuring-assignment)
2. [MDN Web Docs](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
3. [में विनाशकारी ES6](https://medium.com/@stasonmars/деструктуризация-в-es6-полное-руководство-b865bb71f376)

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

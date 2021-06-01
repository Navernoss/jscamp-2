---
id: javascript08
title: सही या गलत?
sidebar_label: सही या गलत?
---

![@serverSerrverlesskiy](/img/javascript/headers/08.jpg)

इस अध्याय में बहुत सी नई चीजें होंगी, लेकिन यह बहुत कठिन नहीं होना चाहिए: आखिरकार, सामान्य तौर पर, सब कुछ एक साधारण विचार के इर्द-गिर्द घूमता है - सही या गलत?

अब तक, हमने हमेशा केवल आदिम डेटा प्रकारों - संख्याओं और स्ट्रिंग्स के साथ व्यवहार किया है।
क्या आपने पहले प्रोग्रामिंग में "आदिम" शब्द देखा है? यदि नहीं, तो मैं समझाता हूँ: "आदिम" (वे "सरल" भी कहते हैं) का अर्थ है कि यह डेटा प्रकार एक वस्तु नहीं है (हम इस बिंदु पर वापस आएंगे) और इसमें काम के अंतर्निहित तरीके नहीं हैं (वह है, कार्य⚙️).

![True](https://media.giphy.com/media/gLWLC3fjwG56p3H4uC/giphy.gif)

जिस डेटा प्रकार की आपको निश्चित रूप से आवश्यकता होगी उसे बूलियन कहा जाता है। `boolean`, या तार्किक। बूलियन प्रकार हमेशा या तो मायने रखता है `true` ✅ - सच या `false` ❎ - असत्य। और केवल इस तरह, और कुछ नहीं! वह या तो झूठ बोल रहा है या सच कह रहा है - पैन करें या गायब हो जाएं, रोशनी चालू है या बंद है, या है या नहीं। आपने या तो अपना होमवर्क किया या आपने नहीं किया। सिर्फ दो 2️⃣ जिसका अर्थ है `true` ✅ या `false`.

## समानता संचालक

![Operator](https://media.giphy.com/media/9r1n7HzkPT9sM1Wp0G/giphy.gif)

बूलियन तब काम आते हैं जब हमें जावास्क्रिप्ट में किसी चीज़ की तुलना करने की आवश्यकता होती है। जब जरूरत होती है, हम तुरंत तुलना ऑपरेटरों को बुलाते हैं।
अब हम सभी आठ तुलना ऑपरेटरों का क्रमिक रूप से अध्ययन करेंगे, लेकिन बात यह है कि उनमें से प्रत्येक के परिणामस्वरूप, हमें परवाह नहीं है
हम हमेशा एक बूलियन मान के साथ रहेंगे - या तो `true` ✅ , या `false` ❎ .

### समान रूप से `==`

![Justice](https://media.giphy.com/media/3o85xDf6hr7ajhVL9K/giphy.gif)

बराबर ऑपरेटर पहले ऑपरेंड को एक ही प्रकार में रखता है, और फिर सख्त तुलना लागू करता है। यदि दोनों ऑपरेंड ऑब्जेक्ट हैं, तो JavaScript आंतरिक संदर्भों की तुलना करता है जो समान हैं यदि वे स्मृति में एक ही वस्तु को संदर्भित करते हैं।

वाक्य - विन्यास📖:

```javascript
x == y
```

उदाहरण:

```javascript
1 == 1 // सच
'1' == 1 // सच
1 == '1' // सच
3 == 5 // असत्य
0 == false // सच
'foo' == 'bar' // असत्य
```

वेरिएबल में एक-एक करके उदाहरण दर्ज करें 🔔 `bool` हमारी `LIVE EDITOR`

```jsx live
function learnJavaScript() {
  let bool = 1 == 1
  return bool.toString()
}
```

### बराबर नहीं `!=`

![Equals](https://media.giphy.com/media/xT8qBit7YomT80d0M8/giphy.gif)

ऑपरेटर वापस नहीं आता🔄 `true` ✅ यदि ऑपरेंड बराबर नहीं हैं। यह समानता ऑपरेटर के समान है, तुलना करने से पहले ऑपरेंड को उसी प्रकार में परिवर्तित करता है। यदि दोनों ऑपरेंड ऑब्जेक्ट हैं, JavaScript आंतरिक संदर्भों की तुलना करता है जो समान नहीं हैं यदि वे स्मृति में विभिन्न वस्तुओं को संदर्भित करते हैं।

वाक्य - विन्यास📖:

```javascript
x != y
```

उदाहरण:

```javascript
1 != 2 // सच
1 != '1' // असत्य
1 != '1' // असत्य
1 != true // असत्य
0 != false // असत्य
'foo' != 'bar' // सच
```

चर में एक-एक करके उदाहरण दर्ज करें 🔔 `bool` हमारी `LIVE EDITOR`

```jsx live
function learnJavaScript() {
  let bool = 1 != 2
  return bool.toString()
}
```

### कड़ाई से बराबर `===`

![equality](https://media.giphy.com/media/4W0ZwRP8y7pQtcUMyQ/giphy.gif)

ऑपरेटर रिटर्न🔄 सच है अगर ऑपरेंड सख्ती से बराबर हैं। बराबर ऑपरेटर के विपरीत, यह ऑपरेटर उसी प्रकार के ऑपरेंड को नहीं डालता है।

वाक्य - विन्यास📖:

```javascript
x === y
```

के उदाहरण:

```javascript
3 === 3 // सच
3 === '3' // असत्य
'foo' === 'foo' // सच
```

ऑपरेटर सुनिश्चित करता है कि मूल्य और प्रकार दोनों सख्ती से समान हैं। के मामले में `3 === '3'` मूल्य, निश्चित रूप से, समान है, लेकिन प्रकार नहीं है: आखिरकार, पहला एक संख्या है, और दूसरा एक स्ट्रिंग है।

चर में एक-एक करके उदाहरण दर्ज करें 🔔 `bool` हमारी `LIVE EDITOR`

```jsx live
function learnJavaScript() {
  let bool = 3 === 3
  return bool.toString()
}
```

### कड़ाई से बराबर नहीं `!==`

![ruler](https://media.giphy.com/media/tPK9Fyl1gyIkU6XbZv/giphy.gif)

सख्ती से समान नहीं ऑपरेटर रिटर्न🔄 सच है अगर ऑपरेंड बराबर नहीं हैं, या उनके प्रकार एक दूसरे से भिन्न हैं।

वाक्य - विन्यास📖:

```javascript
x !== y
```

के उदाहरण:

```javascript
3 !== '3' // सच
4 !== 3 // सच
```

चर में एक-एक करके उदाहरण दर्ज करें 🔔 `bool` हमारी `LIVE EDITOR`

```jsx live
function learnJavaScript() {
  let bool = 3 === 3
  return bool.toString()
}
```

उपयोग क्यों नहीं करें `==` तथा `!=`? लेकिन क्योंकि, सामान्य तौर पर, ऐसी आवश्यकता कभी नहीं होती है। जब भी आप उनका उपयोग कर सकते हैं, आप हमेशा सख्त का उपयोग कर सकते हैं `===` तथा `!==`. यदि आप अपने उत्तर में अधिक लचीलापन चाहते हैं (कहते हैं, ताकि इसे समान रूप से स्वीकार किया जाए) `1`, तो और `'1'` या `true` ✅ ), तो आप बस कोड में ही वांछित उत्तर विकल्प शामिल कर सकते हैं📟 (बिना बदले `===`).

:::info बस नियम समझो
कभी उपयोग न करो `==` या `!=`
:::

## तुलना ऑपरेटर

### अधिक `>`

![not equal](https://media.giphy.com/media/jPfQcPdmI9bTXpa7hi/giphy.gif)

ऑपरेटर अधिक लौटाता है🔄 सच है अगर बाएं ऑपरेंड का मूल्य दाएं से अधिक है।

वाक्य - विन्यास📖:

```javascript
x > y
```

उदाहरण:

```javascript
4 > 3 // सच
1 > 5 // असत्य
```

चर में एक-एक करके उदाहरण दर्ज करें 🔔 `bool` में `LIVE EDITOR`

```jsx live
function learnJavaScript() {
  let bool = 4 > 3
  return bool.toString()
}
```

### कम `<`

![small](https://media.giphy.com/media/82tNeaMTlEsdW/giphy.gif)

कम ऑपरेटर, रिटर्न🔄 सही है अगर बाईं ओर के ऑपरेंड का मान दाईं ओर के ऑपरेंड के मान से कम है।

वाक्य - विन्यास📖:

```javascript
x < y
```

उदाहरण:

```javascript
3 < 4 // सच
5 < 2 // असत्य
```

चर में एक-एक करके उदाहरण दर्ज करें 🔔 `bool` हमारी `LIVE EDITOR`

```jsx live
function learnJavaScript() {
  let bool = 3 < 4
  return bool.toString()
}
```

### अधिक या बराबर `>=`

![comparison operator](https://media.giphy.com/media/icJA0VF7ntoEL18Jez/giphy.gif)

ऑपरेटर से बड़ा या उसके बराबर, रिटर्न🔄 सही है यदि बाईं ओर ऑपरेंड का मान दाईं ओर ऑपरेंड के मान से अधिक या उसके बराबर है।

वाक्य - विन्यास📖:

```javascript
x >= y
```

उदाहरण:

```javascript
4 >= 3 // सच
3 >= 3 // सच
```

चर में एक-एक करके उदाहरण दर्ज करें 🔔 `bool` 👇 :

```jsx live
function learnJavaScript() {
  let bool = 4 >= 3
  return bool.toString()
}
```

### कम या बराबर `<=`

![less](https://media.giphy.com/media/UQbDc6dyK6WjpCXMvt/giphy.gif)

कम या बराबर ऑपरेटर, रिटर्न🔄 सही है यदि बाईं ओर के ऑपरेंड का मान दाईं ओर के ऑपरेंड के मान से कम या उसके बराबर है।

वाक्य - विन्यास📖:

```javascript
x <= y
```

Примеры:

```javascript
3 <= 4 // सच
3 <= 3 // सच
```

चर में एक-एक करके उदाहरण दर्ज करें 🔔 `bool` 👇 :

```jsx live
function learnJavaScript() {
  let bool = 3 < 4
  return bool.toString()
}
```

## सशर्त निर्माण

![boolean](https://media.giphy.com/media/12W5Sg2koWYnwA/giphy.gif)

आप सोच रहे होंगे, "ठीक है, यह सब बूलियन लॉजिक चीज़ बहुत आसान थी ... वे शायद बहुत बेकार हैं और बहुत बार उपयोग नहीं की जाती हैं।" कैसी भी हो! बूलियन मानों का उपयोग प्रोग्रामिंग में हर समय से अधिक और अक्सर सशर्त (या अभिव्यक्ति) के रूप में किया जाता है।

### और "सशर्त निर्माण" क्या है"?

![thoughtful](https://media.giphy.com/media/IyyGGEMZhZIZwAxnUS/giphy.gif)

अच्छा प्रश्न! एक सशर्त एक खंड है जिसका उपयोग कोड के कुछ ब्लॉक चलाने के लिए किया जाता है।📟 निर्दिष्ट शर्त के अनुसार। स्थिति (उदाहरण के लिए, तुलना करते समय `x === y`) हमेशा लौटता है🔄 बूलियन - या तो `true` ✅ , या `false` ❎ . तदनुसार, यदि मान `true` ✅ , तो कोड चलाया जाना चाहिए, अन्यथा कोड ब्लॉक📟 छोड़ दिया जाना चाहिए। आइए कुछ उदाहरण देखें।

### के साथ सशर्त अभिव्यक्तियाँ `if`

![Instruction manual](https://media.giphy.com/media/2mDSs3gPUyrcMqtheg/giphy.gif)

डिज़ाइन `if` पूरा `निर्देश1`, अगर शर्त `true` ✅, अगर शर्त `false` ❎, फिर इसे निष्पादित किया जाता है `निर्देश २`.

वाक्य - विन्यास📖:

```javascript
if (स्थिति) {
  निर्देश1
} else {
  निर्देश2
}
```

`स्थिति` -
एक अभिव्यक्ति जो या तो सत्य है या असत्य।

`инструкция1` -
निष्पादित करने का निर्देश यदि मान `स्थिति` सच में `true` ✅ . नेस्टेड सहित कोई भी निर्देश हो सकता है `if`. जब कोई कार्रवाई की आवश्यकता नहीं होती है तो एक खाली कथन का उपयोग किया जा सकता है।

`निर्देश २` -
निष्पादित करने का निर्देश यदि मान `स्थिति` झूठा `false`❎ . नेस्टेड निर्देशों सहित कोई भी निर्देश हो सकता है `if`. निर्देशों को एक ब्लॉक में भी समूहीकृत किया जा सकता है। वर्ष को एक चर में बदलें 🔔 `whatIsTheYearNow` और आउटपुट पर ध्यान दें।

```jsx live
function learnJavaScript() {
  let whatIsTheYearNow = 2021

  if (whatIsTheYearNow === 2021) {
    whatIsTheYearNow = true
  } else {
    whatIsTheYearNow = false
  }

  return whatIsTheYearNow.toString()
}
```

### `if` न केवल बूलियन

![No](https://media.giphy.com/media/ftqLysT45BJMagKFuk/giphy.gif)

सशर्त अभिव्यक्तियाँ न केवल बूलियन मानों के साथ काम कर सकती हैं, अर्थात उनके साथ जो सटीक नहीं हैं `true` ✅ या `false` ❎ तो हम, सामान्य रूप से, उन्हें सुरक्षित रूप से कोष्ठक, साथ ही बूलियन मानों में उपयोग कर सकते हैं।

- शून्य को छोड़कर सभी पूर्णांक — `true` ✅
- कम से कम एक वर्ण वाली स्ट्रिंग `true` ✅
- एक खाली स्ट्रिंग है `false` ❎

आइए कोशिश करें, मूल्यों को एक चर में डालें 🔔 `bool` 👇 :

```jsx live
function learnJavaScript() {
  let bool = 1

  if (bool) {
    bool = true
  } else {
    bool = false
  }

  return bool.toString()
}
```

### के साथ भावों में तुलना ऑपरेटरों `if`

![made for each other](https://media.giphy.com/media/6yxIP39EMwP7IlIA28/giphy.gif)

अब तक, हमने तुलनाओं या शर्तों के साथ निपटा है `if`, लेकिन अब तक हमने उन्हें एक साथ इस्तेमाल नहीं किया है, लेकिन वे सिर्फ बनाया था🏗️ एक दूसरे के लिए!

```jsx live
function learnJavaScript() {
  let year = 2021

  let output

  if (year < 2020) {
    output = 'कम से 2020'
  } else {
    output = 'अधिक 2020'
  }
  return output
}
```

### कई शर्तें `else if`

कभी-कभी, आपको किसी शर्त के कई रूपों की जांच करने की आवश्यकता होती है। ऐसा करने के लिए, ब्लॉक का उपयोग करें `else if`. वर्ष बदलें और आउटपुट देखें।

```jsx live
function learnJavaScript() {
  let year = 2021

  let output

  if (year < 2020) {
    output = 'कम से 2020'
  } else if (year > 2020) {
    output = 'अधिक 2020'
  } else {
    output = 'समान रूप से 2020'
  }
  return output
}
```

### सशर्त (टर्नरी) ऑपरेटर `?`

![question mark](https://media.giphy.com/media/wH4rY2nPnEnp6/giphy.gif)

में एकमात्र ऑपरेटर operator JavaScript, तीन ऑपरेंड स्वीकार करना: `स्थिति`, उसके बाद एक प्रश्न चिह्न `?`, तब फिर `की अभिव्यक्ति`, जो सच है अगर शर्त सच है, उसके बाद एक कोलन `:`, और अंत में `की अभिव्यक्ति`, जो सच है अगर शर्त झूठी है। यह अक्सर सशर्त बयान के लिए एक आशुलिपि के रूप में प्रयोग किया जाता है `if`.

वाक्य - विन्यास📖:

```javascript
स्थिति ? अभिव्यक्ति1 : अभिव्यक्ति २
```

मापदंडों:

`स्थिति` - अभिव्यक्ति एक मूल्य पर ले रही है `true` ✅ या `false` ❎ .

`अभिव्यक्ति1`, `अभिव्यक्ति २` - वे भाव जिनके मान किसी भी प्रकार के हो सकते हैं।

उदाहरण 👇 :

```jsx live
function learnJavaScript() {
  let age = 20
  let output = age > 18 ? 'हाँ' : 'नहीं'

  return output
}
```

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## सवाल और जवाब:

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

बराबर ऑपरेटर के लिए सिंटैक्स क्या है?

1. `x == y`
2. `x = y`
3. `x -- y`

किस मामले में ऑपरेटर बराबर रिटर्न नहीं देता है `true`?

1. यदि ऑपरेंड बराबर नहीं हैं
2. यदि ऑपरेंड बराबर हैं
3. यदि दोनों ऑपरेंड ऑब्जेक्ट हैं

ऑपरेटर बराबर बराबर से अलग कैसे है?

1. कड़ाई से बराबर एक ही प्रकार के ऑपरेंड नहीं डालता है
2. कड़ाई से समान कास्ट एक ही प्रकार के ऑपरेंड करते हैं
3. कड़ाई से सुनिश्चित करता है कि मान समान है, लेकिन प्रकार नहीं है

ऑपरेटर का सिंटैक्स सख्ती से बराबर नहीं है?

1. `!=`
2. `!==`
3. `==!`

किस मामले में ऑपरेटर अधिक झूठी वापसी करता है?

1. यदि बाएं ऑपरेंड का मान दाएं से अधिक है
2. यदि दाएँ संकार्य का मान बाएँ के मान से अधिक है
3. यदि ऑपरेंड का मान समान है

से बड़ा या उसके बराबर ऑपरेटर के लिए सिंटैक्स क्या है?

1. `>=`
2. `> =>`
3. `> <=`

कम या बराबर ऑपरेटर किस उदाहरण में सही होगा?

1. `4 <= 5`
2. `5 <= 4`
3. `3 <= 2`

एक शर्त क्या है?

1. अनुदेश
2. की अभिव्यक्ति
3. मूल्य

किस ब्लॉक का प्रयोग किसी शर्त के कई रूपों का परीक्षण करने के लिए किया जाता है

1. `else if`
2. `if`
3. `for`

कौन सा ऑपरेटर 3 ऑपरेंड लेता है?

1. सशर्त (टर्नरी) ऑपरेटर
2. इससे बड़ा या बराबर
3. कम या बराबर

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल।

![Sumerian school](/img/app.jpg)

## लिंक:

1. [MDN web docs - तुलना ऑपरेटर](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/Операторы_сравнения)
2. [किशोरों के लिए कोड: प्रोग्रामिंग के लिए एकदम सही शुरुआती गाइड, खंड १: Javascript - Jeremy Moritz ](https://www.amazon.com/Code-Teens-Beginners-Programming-Javascript-ebook/dp/B07FCTLVPC)

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<table>
  <tr>
    <td align="center"><a href="https://fullstackserverless.github.io/"><img src="https://avatars0.githubusercontent.com/u/6774813?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Dmitriy Vasilev</b></sub></a><br /> <a href="https://github.com/gHashTag/react-native-village/commits?author=gHashTag" title="Documentation">📖</a><a href="#financial-gHashTag" title="Financial">💵</a></td>
    <td align="center"><a href="https://github.com/Resoner2005"><img src="https://avatars1.githubusercontent.com/u/75675814?v=4?s=200" width="200px;" alt=""/><br /><sub><b>Resoner2005</b></sub></a><br /><a href="https://github.com/gHashTag/react-native-village/issues?q=author%3AResoner2005" title="Bug reports">🐛 🎨 🖋</a></td>
  </tr>
  
</table>

[![Become a Patron!](/img/logo/patreon.jpg)](https://www.patreon.com/bePatron?u=31769291)

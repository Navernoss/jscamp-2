---
id: javascript17
title: सरणियों
sidebar_label: सरणियों
---

![@serverSerrverlesskiy](/img/javascript/headers/18.jpg)

भंडारण के लिए 📦 आदेशित संग्रह में एक विशेष डेटा संरचना होती है जिसे एक सरणी कहा जाता है `Array`.

![Storage](https://media.giphy.com/media/3orif6FORJ98Z11xzq/giphy.gif)

`सरणी` - डेटा का एक आदेशित संग्रह जिसमें 1, 2, 3 आइटम आदि शामिल हैं। उदाहरण के लिए, हमें भंडारण के लिए इसकी आवश्यकता होगी 📦 किसी चीज़ की सूची: उपयोगकर्ता, उत्पाद, साइट तत्व, आदि।

## जंतु

![create](https://media.giphy.com/media/3oEduXdm2gjnrsJBOo/giphy.gif)

वहाँ दो हैं 2️⃣ बनाने का विकल्प🏗️ खाली सरणी:

```javascript
let arr = new Array(5)
// new Array(5) - एक सरणी बनाता है जिसमें कोई तत्व नहीं होता है (जिसे उसी तरह एक्सेस नहीं किया जा सकता है), लेकिन दी गई लंबाई के साथ।
let arr = []
```

दूसरा विकल्प लगभग हमेशा उपयोग किया जाता है। 2️⃣ वाक्य - विन्यास📖. कोष्ठक में, हम तत्वों के प्रारंभिक मूल्यों को इंगित कर सकते हैं:

```jsx live
function learnJavaScript() {
  let fruits = ['ऐप्पल ',' ऑरेंज ',' प्लम']

  return fruits.toString()
}
```

ऐरे तत्वों को शून्य से शुरू करके क्रमांकित किया जाता है 0️⃣ .

हम वर्ग कोष्ठक में उसकी संख्या निर्दिष्ट करके एक वस्तु प्राप्त कर सकते हैं 👇 :

```jsx live
function learnJavaScript() {
  let fruits = ['सेब ',' नारंगी ',' बेर']

  return fruits[0]
}
```

हम बदल सकते हैं 🖊️ तत्त्व:

```javascript
fruits[2] = 'नाशपाती' // अब ["ऐप्पल", "ऑरेंज", "नाशपाती"]
```

... या जोड़ें 🆕 मौजूदा सरणी के लिए नया 👇 :

```jsx live
function learnJavaScript() {
  let fruits = ['ऐप्पल ',' ऑरेंज ',' प्लम ']
  fruits[2] = 'नाशपाती '
  fruits[3] = 'नींबू '// अब ["सेब", "नारंगी", "नाशपाती", "नींबू"]

  return fruits
}
```

## length

सरणी तत्वों की कुल संख्या इसकी संपत्ति में निहित है `.length`:

```jsx live
function learnJavaScript() {
  let fruits = ['ऐप्पल ',' ऑरेंज ',' प्लम']

  return fruits.length
}
```

संपत्ति `length` सरणी बदलने पर स्वचालित रूप से अपडेट हो जाता है। सटीक होने के लिए, यह सरणी में तत्वों की संख्या नहीं है, बल्कि सबसे बड़ा संख्यात्मक सूचकांक प्लस वन है।

![Update](https://media.giphy.com/media/FP47IFqWyXfdKYU6VG/giphy.gif)

उदाहरण के लिए, एक बड़े सूचकांक वाला एकमात्र वास्तविक तत्व सबसे लंबी संभव सरणी लंबाई देता है 👇 :

```jsx live
function learnJavaScript() {
  let fruits = []
  fruits[155] = 'सेब'

  return fruits.length // 156
}
```

ध्यान दें कि हम आमतौर पर इस तरह से सरणियों का उपयोग नहीं करते हैं।

संपत्ति के बारे में एक और दिलचस्प तथ्य `length` – इसे अधिलेखित किया जा सकता है।

अगर हम मैन्युअल रूप से बढ़ाते हैं ➕ उसे, कुछ भी दिलचस्प नहीं होगा। लेकिन अगर हम इसे कम करते हैं, तो सरणी छोटी हो जाएगी। यह प्रक्रिया अपरिवर्तनीय है, जैसा कि हम उदाहरण से समझ सकते हैं 👇 :

```jsx live
function learnJavaScript() {
  let arr = [1, 2, 3, 4, 5]

  arr.length = 2 // दो तत्वों को छोटा करें
  //console.log( arr )  // [1, 2]

  arr.length = 5 // वापसी length जैसा था
  //console.log( arr[3] )  // undefined: मूल्यों को बहाल नहीं किया गया है!
  return 'वास्तविक सरणी को छोटा कर दिया गया है:' + arr
}
```

तो किसी सरणी को साफ़ करने का सबसे आसान तरीका है `arr.length = 0` .

## आइटम प्रकार

![Storage](https://media.giphy.com/media/2sYaePC3iVWYBNxaVj/giphy.gif)

सरणी स्टोर कर सकते हैं 📦 किसी भी प्रकार के तत्व - संख्या, बूलियन, तार, वस्तुएं, या संपूर्ण कार्य⚙️:

उदाहरण के लिए 👇 :

```jsx live
function learnJavaScript() {
  let arr = [
    'सेब',
    { name: 'निकिता' },
    true,
    function () {
      return 'नमस्ते'
    }
  ]
  // सूचकांक 1 पर तत्व प्राप्त करें {एक वस्तु} और फिर इसकी संपत्ति पढ़ें
  let x = arr[1].name // नाम निकिता
  // इंडेक्स 3 (फ़ंक्शन) के साथ तत्व प्राप्त करें और इसे निष्पादित करें
  let result1 = arr[3] // समारोह स्वयं
  let result2 = arr[3]() // 'नमस्ते'

  return 'तीसरे सूचकांक के साथ चौथे तत्व का मान: ' + result2
  // + '. समारोह स्वयं: ' + result1
}
```

ध्यान दें `result1 = arr[3]` पाठ शामिल करें 📜 कार्यों⚙️, लेकिन अ `result2 = arr[3]()` निष्पादित फ़ंक्शन का परिणाम⚙️ - `()` हम इसे चलाते हैं।

## तरीकों `push/pop`

![binarycode](https://media.giphy.com/media/fV0oSDsZ4UgdW/giphy.gif)

`ढेर` - डेटा संरचनाओं के रूप में सरणियों का उपयोग करने का एक प्रकार।

वह दो का समर्थन करती है 2️⃣ संचालन के प्रकार:

- `push` जोड़ता ➕ अंत तक तत्व।

![Add](https://media.giphy.com/media/Yqo5mjWTLGlVOIP8Dc/giphy.gif)

- `pop` हटा देगा ➖ अंतिम तत्व।

![Delete](https://media.giphy.com/media/VD4Bt6FyYWcWj0LzDK/giphy.gif)

इस प्रकार, नए तत्व हमेशा "अंत" से जोड़े या हटाए जाते हैं।

स्टैक का एक उदाहरण आमतौर पर एक पिरामिड होता है: नए छल्ले शीर्ष पर रखे जाते हैं और ऊपर से भी लिए जाते हैं।

कतार एक सरणी के लिए सबसे आम उपयोगों में से एक है। कंप्यूटर के क्षेत्र में🖥️ विज्ञान तत्वों के एक क्रमबद्ध संग्रह का नाम है

## किसी सरणी के अंत के साथ काम करने के तरीके:

### push

![Add to](https://media.giphy.com/media/21ODeWspDCgZNAoCIp/giphy.gif)

जोड़ता ➕ सरणी के अंत में तत्व 👇 :

```jsx live
function learnJavaScript() {
  let fruits = [' सेब ',' ऑरेंज']

  fruits.push(' नाशपाती')

  return 'सरणी: ' + fruits // सेब, संतरा, नाशपाती
}
```

### pop

![Delete](https://media.giphy.com/media/26ybwwiZmci3DJdYs/giphy.gif)

हटा देगा ➖ सरणी से अंतिम तत्व और इसे लौटाता है 👇 :

```jsx live
function learnJavaScript() {
  let fruits = [' सेब ',' संतरा ',' नाशपाती']

  let delFruits = fruits.pop() // "नाशपाती" को हटा दें और इसे चर पर लौटा दें delFruits

  return 'हटाई गई वस्तु = ' + delFruits + '. सरणी बाएँ: ' + fruits // सेब, संतरा
}
```

## सरणी की शुरुआत के साथ काम करने के तरीके:

![start](https://media.giphy.com/media/QJvwBSGaoc4eI/giphy.gif)

### shift

हटा देगा ➖ पहले सरणी से और रिटर्न🔄 उसके:

![delete](https://media.giphy.com/media/4Z1XJumqDgvI9b1VZJ/giphy.gif)

```jsx live
function learnJavaScript() {
  let fruits = ['सेब ',' संतरा ',' नाशपाती ']
  fruits.shift() // सेब को हटा दें

  return fruits
}
```

### unshift

जोड़ता ➕ सरणी की शुरुआत में तत्व:

![Plus](https://media.giphy.com/media/LgC9OQ53v5mFi/giphy.gif)

```jsx live
function learnJavaScript() {
  let fruits = ['सेब ',' संतरा ',' नाशपाती ']
  fruits.unshift('खुबानी ')

  return fruits
}
```

तरीकों `push` तथा `unshift` जोड़ सकते हैं ➕ एक साथ कई तत्व 👇 :

```jsx live
function learnJavaScript() {
  let fruits = ['सेब']

  fruits.push('नारंगी ',' नाशपाती')
  fruits.unshift('अनानास, नींबू')

  return 'एक सरणी में ' + fruits.length + ' तत्वों. ' + ' सरणी: ' + fruits // ["अनानास, नींबू, सेब", "नारंगी "," नाशपाती "]
}
```

## नारंगी "," नाशपाती "]

![cupboard](https://media.giphy.com/media/b90TnygrKqYqk/giphy.gif)

Arrays एक विशेष प्रकार की वस्तुएँ हैं। किसी संपत्ति तक पहुँचने के लिए उपयोग किए जाने वाले वर्गाकार कोष्ठक `arr[0]` – यह अनिवार्य रूप से सामान्य वाक्यविन्यास है📖 कुंजी पहुंच जैसे `obj[key],` भूमिका में कहाँ `obj` अपने पास `arr`, और कुंजी एक संख्यात्मक सूचकांक है।

सरणी डेटा के आदेशित संग्रह के साथ-साथ संपत्ति के साथ काम करने के लिए विशेष तरीके प्रदान करके वस्तुओं का विस्तार करती है `length.` लेकिन यह अभी भी एक वस्तु पर आधारित है।

यह याद रखना चाहिए कि में JavaScript एक सरणी एक वस्तु है और इसलिए एक वस्तु की तरह व्यवहार करती है।

उदाहरण के लिए, सरणी को संदर्भ द्वारा कॉपी किया गया है 👇 :

```jsx live
function learnJavaScript() {
  let fruits = [' नींबू']

  let copy = fruits // संदर्भ द्वारा कॉपी किया गया (दो चर एक ही सरणी को देखें)

  copy.push(' नाशपाती') // एक कमांड के संदर्भ में सरणियों को बदल दिया जाता है

  return '1 सरणी: ' + fruits + ' 2 सरणी: ' + copy // नींबू, नाशपाती - अब दो तत्व
}
```

जो चीज वास्तव में सरणियों को विशेष बनाती है वह है उनका आंतरिक प्रतिनिधित्व। यन्त्र JavaScript एक सरणी के तत्वों को स्मृति के सन्निहित क्षेत्र में एक-एक करके संग्रहीत करने का प्रयास करता है। ऐसे अन्य अनुकूलन हैं जो सरणियों को बहुत तेज़ बनाते हैं।

लेकिन वे सभी अप्रभावी हो जाते हैं यदि हम "डेटा के आदेशित संग्रह" के रूप में एक सरणी के साथ काम करना बंद कर देते हैं और इसे एक नियमित वस्तु की तरह उपयोग करना शुरू कर देते हैं।

उदाहरण के लिए, हम तकनीकी रूप से निम्न कार्य कर सकते हैं:

```javascript
let fruits = [] // एक खाली सरणी बनाएँ

fruits[99999] = 5 // सरणी की आवश्यक लंबाई से बहुत अधिक एक अनावश्यक अनुक्रमणिका के साथ एक संपत्ति बनाएं

fruits.age = 25 // एक मनमाना नाम के साथ एक संपत्ति बनाएँ
```

यह संभव है क्योंकि सरणी किसी वस्तु पर आधारित है। हम इसके लिए कोई भी गुण असाइन कर सकते हैं।

:::note सरणी दुरुपयोग विकल्प!

- एक गैर-संख्यात्मक संपत्ति जोड़ना (सूचकांक test), जैसे: arr.test = 5
- "छेद" का निर्माण, उदाहरण के लिए: जोड़ना arr[0], तब फिर arr[1000] (उनके बीच कुछ भी नहीं है)
- उदाहरण के लिए, सरणी को उल्टे क्रम में भरना: arr[1000], arr[999] आदि।

:::

एक विशेष संरचना के रूप में एक सरणी पर विचार करें जो आपको ऑर्डर किए गए डेटा के साथ काम करने की अनुमति देता है। यदि आपको मनमानी चाबियों की आवश्यकता है, तो यह बहुत संभव है कि एक नियमित वस्तु बेहतर हो। {}.

## दक्षता

![Fast](https://media.giphy.com/media/3oriNYQX2lC6dfW2Ji/giphy.gif)

तरीकों `push/pop` तेज़ हैं, और तरीके `shift/unshift` – धीमा।

इसकी शुरुआत की तुलना में किसी सरणी के अंत के साथ काम करना तेज़ क्यों है? आइए देखें कि रनटाइम पर क्या होता है:

```javascript
fruits.shift() // शुरुआत से पहले तत्व को हटा दें
```

केवल संख्या 0 वाले तत्व को लेना और निकालना पर्याप्त नहीं है। बाकी तत्वों को भी फिर से क्रमांकित किया जाना चाहिए।

ऑपरेशन `shift` चाहिए 3 चरणों का पालन करें:

- अनुक्रमणिका के साथ आइटम निकालें 0

![Delete](https://media.giphy.com/media/VIzs0jgs8KmgVeTknN/giphy.gif)

- सभी तत्वों को बाईं ओर ले जाएं, उन्हें फिर से नंबर दें, प्रतिस्थापित करें `1` पर `0`, `2` पर `1` आदि।

![Move](https://media.giphy.com/media/jSQcEjcwG53WooptHz/giphy.gif)

- संपत्ति अपडेट करें `length`

सरणी में जितने अधिक तत्व होंगे, उन्हें स्थानांतरित करने में उतना ही अधिक समय लगेगा, स्मृति संचालन उतना ही अधिक होगा।

हटाने के बारे में क्या `pop`? उसे कुछ भी हिलने-डुलने की जरूरत नहीं है। किसी सरणी के अंत में किसी तत्व को निकालने के लिए, विधि `pop` सूचकांक को साफ करता है और मूल्य घटाता है `length`. शेष तत्व समान सूचकांकों के साथ रहते हैं।

```javascript
fruits.pop() // एक तत्व को अंत से हटा दें
```

तरीका `pop` हिलने की आवश्यकता नहीं है। इसलिए यह बहुत तेज दौड़ता है।

विधि एक समान तरीके से काम करती है `push`.

## तत्वों पर पुनरावृति

![Object](https://media.giphy.com/media/26gs9kSN6d5PxSsQU/giphy.gif)

सरणी तत्वों पर पुनरावृति करने के सबसे पुराने तरीकों में से एक लूप है `for( )` डिजिटल सूचकांकों द्वारा 👇 :

```jsx live
// prettier-ignore
function learnJavaScript() {
  let result = ''
  let arr = ['सेब ',' संतरा ',' कीवी']
  
  for (let i = 0; i < arr.length; i++) // तत्वों के माध्यम से जाता है for( )
  result += arr[i] + ' '

  return result // सेब, संतरा, कीवी
}
```

लेकिन सरणियों के लिए, लूप का दूसरा संस्करण भी संभव है।, `for..of` 👇 :

```jsx live
function learnJavaScript() {
  let result = ''
  let fruits = ['ऐप्पल ',' ऑरेंज ',' प्लम']

  for (let fruit of fruits) {
    // मूल्यों के माध्यम से जाता है `for..of`
    result += fruit + ' '
  }
  return result // सेब, संतरा, बेर
}
```

चक्र `for..of` वर्तमान तत्व की संख्या तक पहुंच प्रदान नहीं करता है, केवल इसके मूल्य तक, लेकिन ज्यादातर मामलों में यह पर्याप्त से अधिक है, और यह छोटा भी है।

## बहुआयामी सरणियाँ

![Matryoschka](https://media.giphy.com/media/XuPaGVKyJ6eyI/giphy.gif)

सरणी में ऐसे तत्व हो सकते हैं जो सरणी भी हैं। इसे बनाने के लिए इस्तेमाल किया जा सकता है🏗️ बहुआयामी सरणियाँ, उदाहरण के लिए, भंडारण के लिए 📦 मैट्रिक्स:

```jsx live
function learnJavaScript() {
  let matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
  ]

  return matrix[1][1] // 5, केंद्रीय तत्व
}
```

## संपूर्ण

![remember](https://media.giphy.com/media/l4pTfqyI6TCjUW4Yo/giphy.gif)

एक सरणी एक विशेष प्रकार की वस्तु है जिसे तत्वों के क्रमबद्ध सेट के साथ काम करने के लिए डिज़ाइन किया गया है।

विज्ञापन🗣️:

```javascript
// वर्ग कोष्ठक (आमतौर पर)
let arr = [item1, item2...]

// new Array (शायद ही कभी)
let arr = new Array(item1, item2...)
```

कॉल `new Array(number)` बनाता है🏗️ दी गई लंबाई के साथ एक सरणी, लेकिन कोई तत्व नहीं।

संपत्ति `length` सरणी की लंबाई को दर्शाता है।

हम निम्नलिखित कार्यों का उपयोग करके एक सरणी को एक डेक के रूप में उपयोग कर सकते हैं:

- `push(...items)` जोड़ता ➕ items सरणी के अंत तक।
- `pop()` हटा देगा ➖सरणी के अंत में तत्व और इसे वापस कर देता है।
- `unshift(...items)` जोड़ता ➕ items सरणी की शुरुआत के लिए।

किसी सरणी के तत्वों पर पुनरावृति करने के लिए:

- `for (let i=0 i<arr.length i++)` – पुराने ब्राउज़र के साथ संगत, सबसे तेज़ काम करता है।
- `for (let item of arr)` – आधुनिक वाक्य रचना📖 केवल तत्व मूल्यों के लिए (सूचकांक तक पहुंच नहीं)।
- `for (let i in arr)` – सरणी के लिए कभी भी उपयोग न करें!

## समस्या?

![Problem](https://media.giphy.com/media/xTiTnGeUsWOEwsGoG4/giphy.gif)

को लिखना [Discord](https://discord.gg/6GDAfXn) या तार [बातचीत](https://t.me/jscampapp), और हमारे को भी सब्सक्राइब करें [समाचार](https://t.me/javascriptapp)

## सवाल और जवाब

![Question](https://media.giphy.com/media/l0HlRnAWXxn0MhKLK/giphy.gif)

एक सरणी है ...

1. "डेटा के आदेशित संग्रह" के साथ वस्तुओं का उपप्रकार
2. आंतरिक कार्य
3. "डेटा के अनियंत्रित संग्रह" के साथ वस्तुओं का उपप्रकार

एक खाली सरणी बनाई गई है:

1. `let arr1 = [ ]`
2. `let arr2 = { }`
3. `let arr3 = ( )`

सरणी की लंबाई संपत्ति द्वारा निर्धारित की जा सकती है:

1. `pop()`
2. `push()`
3. `length`

सरणी तत्वों को संग्रहीत कर सकती है:

1. कोई भी प्रकार
2. संख्यात्मक
3. स्ट्रिंग

सरणी के अंत में एक तत्व जोड़ना:

1. `push()`
2. `pop()`
3. `shift()`

किसी सरणी की शुरुआत में किसी तत्व को हटाना:

1. `pop()`
2. `shift()`
3. `unshift()`

यह समझने के लिए कि आपने यह पाठ कितना सीखा है, इसमें परीक्षा दें [मोबाइल एप्लिकेशन](http://onelink.to/njhc95) इस विषय पर हमारे स्कूल।

![Sumerian school](/img/app.jpg)

## लिंक

1. [लेख "सरणी"](https://learn.javascript.ru/array)
2. [MDN web doc. लेख "सरणी"](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Array)
3. [लेख "JavaScript सरणियों"](https://basicweb.ru/javascript/js_array.php)
4. [किशोरों के लिए कोड: प्रोग्रामिंग के लिए एकदम सही शुरुआती गाइड, खंड 1: Javascript - Jeremy Moritz ](https://www.amazon.com/Code-Teens-Beginners-Programming-Javascript-ebook/dp/B07FCTLVPC)

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
### toString
Массивы по-своему реализуют метод toString, который возвращает список элементов, разделённых запятыми.

Например:
```javascript
let arr = [1, 2, 3]

console.log( arr )  // 1,2,3
console.log( String(arr) === '1,2,3' )  // true
```

Давайте теперь попробуем следующее:
```javascript
console.log( [] + 1 )  // "1"
console.log( [1] + 1 )  // "11"
console.log( [1,2] + 1 )  // "1,21"
```

Массивы не имеют ни Symbol.toPrimitive, ни функционирующего valueOf, они реализуют только преобразование toString, таким образом, здесь [] становится пустой строкой, [1] становится "1", а [1,2] становится "1,2".

Когда бинарный оператор плюс "+" добавляет что-либо к строке, он тоже преобразует это в строку, таким образом:
```javascript
console.log( "" + 1 )  // "1"
console.log( "1" + 1 )  // "11"
console.log( "1,2" + 1 )  // "1,21"
```
-->

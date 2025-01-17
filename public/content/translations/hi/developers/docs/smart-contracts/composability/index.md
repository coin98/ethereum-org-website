---
title: स्मार्ट अनुबंध कम्पोज़ेबिलिटी
description:
lang: hi
incomplete: true
---

## एक संक्षिप्त परिचय {#a-brief-introduction}

स्मार्ट अनुबंध एथेरियम पर सार्वजनिक हैं और इन्हें खुले API के रूप में माना जा सकता है। डैप डेवलपर बनने के लिए आपको अपना खुद का स्मार्ट अनुबंध लिखने की जरूरत नहीं है, आपको बस यह जानना होगा कि उनके साथ कैसे इंटरैक्ट किया जाए। उदाहरण के लिए, आप अपने ऐप में सभी टोकन स्वैप लॉजिक को संभालने के लिए [Uniswap](https://uniswap.exchange/swap) नामक एक विकेन्द्रीकृत एक्सचेंज के मौजूदा स्मार्ट अनुबंध का उपयोग कर सकते हैं - आपको प्रारंभ से शुरू करने की आवश्यकता नहीं होती है। उनके कुछ [v2](https://github.com/Uniswap/uniswap-v2-core/tree/master/contracts) और [v3](https://github.com/Uniswap/uniswap-v3-core/tree/main/contracts) अनुबंधों की जाँच करें।

## कम्पोज़ेबिलिटी क्या है? {#what-is-composability}

कम्पोज़ेबिलिटी नए सिस्टम या आउटपुट बनाने के लिए अलग-अलग घटकों का संयोजन कर रही है। सॉफ़टवेयर के विकास में, कम्पोज़ेबिलिटी का मतलब है कि डेवलपर्स नए एप्लिकेशन के निर्माण के लिए मौजूदा सॉफ़्टवेयर के घटकों का फिर से उपयोग कर सकते हैं। कम्पोज़ेबिलिटी को समझने का एक अच्छा तरीका लेगो ब्लॉक के रूप में कंपोज़ेबल तत्वों के बारे में सोचना है। प्रत्येक लेगो को दूसरे के साथ जोड़ा जा सकता है, जिससे आप विभिन्न लेगो को मिलाकर जटिल संरचनाएं बना सकते हैं।

एथेरियम में, प्रत्येक स्मार्ट अनुबंध एक प्रकार का लेगो है - आप अपनी परियोजना के लिए बिल्डिंग ब्लॉक के रूप में अन्य परियोजनाओं से स्मार्ट अनुबंधों का उपयोग कर सकते हैं। इसका मतलब है कि आपको पहिया या इमारत को शुरुआत से फिर से बनाने में समय बिताने की ज़रूरत नहीं है।

## कम्पोज़ेबिलिटी कैसे काम करती है? {#how-does-composability-work}

एथेरियम स्मार्ट अनुबंध सार्वजनिक API की तरह हैं, इसलिए कोई भी अनुबंध के साथ बातचीत कर सकता है या अतिरिक्त कार्यक्षमता के लिए उन्हें डैप्स में इंटीग्रेट कर सकता है। स्मार्ट अनुबंध कम्पोज़ेबिलिटी आम तौर पर तीन सिद्धांतों से काम करती है: प्रतिरूपकता, स्वायत्तता और खोज क्षमता:

**1. मॉड्यूलेरिटी**: यह एक विशिष्ट कार्य करने के लिए व्यक्तिगत घटकों की क्षमता है। एथेरियम में, प्रत्येक स्मार्ट अनुबंध का एक विशिष्ट उपयोग मामला होता है (जैसा कि Uniswap उदाहरण में दिखाया गया है)।

**2. स्वायत्तता**: कंपोज़ेबल घटकों को स्वतंत्र रूप से संचालित करने में सक्षम होना चाहिए। एथेरियम में हर स्मार्ट अनुबंध अपने-आप लागू होता है और सिस्टम के अन्य भागों पर भरोसा किए बिना कार्य कर सकता है।

**3. खोज योग्यता**: डेवलपर्स बाहरी अनुबंधों को कॉल नहीं कर सकते हैं या सॉफ़्टवेयर लाइब्रेरी को एप्लिकेशंस में एकीकृत नहीं कर सकते हैं यदि पुराने वाले सार्वजनिक रूप से उपलब्ध नहीं हैं। डिज़ाइन के अनुसार, स्मार्ट अनुबंध खुले स्रोत हैं; कोई भी स्मार्ट अनुबंध कह सकता है या कोडबेस फ़ोर्क कर सकता है।

## रचना के लाभ {#benefits-of-composability}

### छोटा विकास चक्र {#shorter-development-cycle}

कम्पोज़ेबिलिटी उस काम को कम करती है जो डेवलपर्स को [डैप्स](/dapps/#what-are-dapps) बनाते समय करना पड़ता है। [जैसा कि नवल रविकांत कहते हैं:](https://twitter.com/naval/status/1444366754650656770) "ओपन सोर्स का मतलब है कि हर समस्या को एक बार हल किया जाना चाहिए।"

अगर कोई स्मार्ट अनुबंध है जो एक समस्या को हल करता है, तो अन्य डेवलपर्स इसका पुन: उपयोग कर सकते हैं, इसलिए उन्हें उसी समस्या को हल करने की आवश्यकता नहीं है। इस तरह, डेवलपर्स मौजूदा सॉफ़्टवेयर लाइब्रेरी ले सकते हैं और नए डेप बनाने के लिए अतिरिक्त कार्यक्षमता जोड़ सकते हैं।

### अधिक से अधिक इनोवेशन {#greater-innovation}

कम्पोज़ेबिलिटी इनोवेशन और प्रयोग को प्रोत्साहित करती है, क्योंकि डेवलपर्स वांछित परिणाम पाने के लिए ओपन-सोर्स कोड का फिर से उपयोग, संशोधन, डुप्लिकेट या एकीकृत करने के लिए स्वतंत्र हैं। परिणामस्वरूप, विकास दल बुनियादी कार्यक्षमता पर कम समय बिताते हैं और नई सुविधाओं के साथ प्रयोग करने में अधिक समय आवंटित कर सकते हैं।

### बेहतर उपयोगकर्ता अनुभव {#better-user-experience}

एथेरियम इकोसिस्टम के घटकों के बीच इंटरऑपरेबिलिटी उपयोगकर्ता अनुभव को बेहतर बनाती है। उपयोगकर्ता अधिक कार्यक्षमता का उपयोग कर सकते हैं जब डैप्स एक खंडित पारिस्थितिकी तंत्र की तुलना में बाहरी स्मार्ट अनुबंधों को एकीकृत करते हैं जहां एप्लिकेशन कम्युनिकेट नहीं कर सकते।

हम इंटरऑपरेबिलिटी के लाभों को स्पष्ट करने के लिए आर्बिट्रेज ट्रेडिंग से एक उदाहरण का उपयोग करेंगे:

यदि कोई टोकन `exchange B` की तुलना में `exchange A` पर अधिक ट्रेडिंग कर रहा है, तो आप लाभ कमाने के लिए मूल्य अंतर का लाभ उठा सकते हैं। हालाँकि, आप केवल तभी ऐसा कर सकते हैं जब आपके पास लेन-देन को निधि देने के लिए पर्याप्त पूंजी हो (यानी, `exchange B` से टोकन खरीदना और इसे `exchange A` पर बेचना)।

ऐसे परिदृश्य में जहां आपके पास व्यापार को कवर करने के लिए पर्याप्त धन नहीं है, एक फ़्लैश लोन आदर्श हो सकता है। [फ्लैश ऋण](/defi/#flash-loans) अत्यधिक तकनीकी हैं, लेकिन मूल विचार यह है कि आप एसेट उधार ले सकते हैं (संपार्श्विक के बिना) और _एक_ लेनदेन के भीतर वापस कर सकते हैं।

हमारे प्रारंभिक उदाहरण पर वापस जा रहे हैं, एक आर्बिट्रेज व्यापारी एक बड़ा फ्लैश ऋण ले सकता है, `exchange B` से टोकन खरीद सकता है, उन्हें `exchange A` पर बेच सकता है, पूंजी + ब्याज का भुगतान कर सकता है, और उसी लेनदेन के भीतर लाभ रख सकता है। इस जटिल तर्क के लिए कई अनुबंधों में कॉल के संयोजन की आवश्यकता होती है, जो स्मार्ट अनुबंधों में इंटरऑपरेबिलिटी की कमी होने पर संभव नहीं होगा।

## एथेरियम में कम्पोज़ेबिलिटी के उदाहरण {#composability-in-ethereum}

### टोकन स्वैप {#token-swaps}

अगर आप एक डैप बनाते हैं जिसके लिए ETH में लेनदेन का भुगतान करने की आवश्यकता होती है, तो आप टोकन स्वैप तर्क को इंटीग्रेट करके उपयोगकर्ताओं को अन्य ERC-20 टोकन में भुगतान करने की अनुमति दे सकते हैं। अनुबंध द्वारा कॉल किए गए फ़ंक्शन को लागू करने से पहले कोड स्वचालित रूप से उपयोगकर्ता के टोकन को ETH में बदल देगा।

### गवर्नेंस {#governance}

[डीएओ](/dao/) के लिए बिस्पोक गवर्नेंस सिस्‍टम का निर्माण महंगा और समय लेने वाला हो सकता है। इसके बजाय, आप एक ओपन-सोर्स गवर्नेंस टूलकिट जैसे [Aragon क्लाइंट](https://client.aragon.org/) का उपयोग कर अपने डीएओ को बूटस्ट्रैप करने के लिए जल्दी से एक गवर्नेंस फ्रेमवर्क बना सकते हैं।

### पहचान प्रबंधन {#identity-management}

कस्टम ऑथेंटिकेशन सिस्टम बनाने या केंद्रीकृत प्रदाताओं पर भरोसा करने के बजाय, आप उपयोगकर्ताओं के लिए प्रमाणीकरण प्रबंधित करने के लिए विकेन्द्रीकृत पहचान (DID) उपकरणों को इंटीग्रेट कर सकते हैं। एक उदाहरण है [SpruceID](https://www.spruceid.com/), एक ओपन-सोर्स टूलकिट जो "एथेरियम के साथ साइन इन करें" कार्यक्षमता प्रदान करता है जो उपयोगकर्ताओं को एथेरियम वॉलेट के साथ पहचान प्रमाणित करने देता है।

## संबंधित ट्यूटोरियल {#related-tutorials}

- [create-eth-app के साथ अपने डैप फ्रंटएंड डेवलपमेंट को किकस्टार्ट करें](/developers/tutorials/kickstart-your-dapp-frontend-development-with-create-eth-app/) _– आधुनिक लोकप्रिय स्मार्ट अनुबंध वाले ऐप्स बनाने के लिए create-eth-app का उपयोग करने का अवलोकन।_

## अग्रिम पठन {#further-reading}

_एक सामुदायिक संसाधन के बारे में जानें, जिसने आपकी मदद की? इस पृष्ठ को संपादित करें और इसे जोड़ें!_

- [कम्पोज़ेबिलिटी इनोवेशन है](https://future.a16z.com/how-composability-unlocks-crypto-and-everything-else/)
- [Web3 के लिए कम्पोज़ेबिलिटी क्यों मायने रखती है](https://hackernoon.com/why-composability-matters-for-web3)
- [कम्पोज़ेबिलिटी क्या है?](https://blog.aragon.org/what-is-composability/#:~:text=Aragon,connect%20to%20every%20other%20piece.)
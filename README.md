# Translators_Comparsion 
## Comparsion of the Translator's(Google Translator and AI4Bharat Translator) based on the BLUE Score and STS Score 

### **Problem Statement :**

In light of Google Translator's inefficiencies with low-resource and certain Indian languages, can we find more effective alternatives to Google Translator?How do these alternatives compare in terms of accuracy and contextual meaning, aiming to deliver superior translations in diverse linguistic contexts?

<p align="center">
  <img src="https://i.imgur.com/pDtiiou.png" alt="Your Image Alt Text" width="120">
  <img src="https://i.imgur.com/0JSSL2o.png" alt="Your Image Alt Text" width="130">
</p>


### **Dataset :** 

Here the dataset was taken from the kaggle which was uploaded by IIT Bombay containing of 10 lakh records of both hindi and english.

### **Methodology :**

The hindi records were passed to two different translators and then translated them into english and then compared the records with the original english texts which were already in the dataset and got the STS Score and then finally picking up the best translator for translating indic to english.
          
### **Google Translator -> NEURAL MACHINE TRANSLATION (NMT) :**

The core technology behind Google Translate is NMT. NMT uses artificial neural networks trained on massive amounts of bilingual text data. These networks learn the relationships between words and phrases across languages, allowing them to generate translations that are more natural and accurate than traditional methods.

### **Google Translator's NMT Architecture :**

<p align="center">
  <img src="https://i.imgur.com/OelpDRU.png" alt="Your Image Alt Text" width="600">
</p>


### **Translation Done Using Google Translator :**

| Hindi                                               | English                                              | Translated Text (Google)                            |
| --------------------------------------------------- | ---------------------------------------------------- | --------------------------------------------------- |
| ऐ मेरे बन्दों! आज न तुम्हें कोई भय है और न तुम शोकाकुल होगे। | "O My servants, today no fear is on you, neither do you sorrow" | O my prisoners! Today you have no fear nor you will be heartbroken |
| "वही है जो आकाशों में भी पूज्य है और धरती में भी पूज्य है और वह तत्वदर्शी, सर्वज्ञ है" | "And it is He who in heaven is God and in earth is God; He is the All-wise, the All-knowing." | "He is the one who is also revered in the sky and is also revered in the earth and he is a philosopher, omnisc." |
| "रहे वे लोग जिन्होंने इनकार किया, तो उनके लिए तबाही है। और उनके कर्मों को अल्लाह ने अकारथ कर दिया" | "But as for the unbelievers, ill chance shall befall them! He will send their works astray." | "Those who refused, so there is havoc for them. And Allah made their deeds unconscious" |
| फिर कैसी रही मेरी यातना और मेरे डरावे?                    | How then were My chastisement and My warnings?        | Then how was my torture and my scared?               |

### **AI4Bharat -> Indic-Trans :**

This model is built on the robust Transformer architecture, initially designed for Google Translate and meticulously adapted for Indic languages. It leverages parallelized processing and attention mechanisms, resulting in efficient training and superior performance. Trained on an extensive dataset encompassing all 22 scheduled Indic languages and English, the model adeptly captures language relationships, ensuring precise translations. IndicTrans2 optimizes lexical sharing by employing script unification when possible, seamlessly converting diverse scripts, such as those used in Kashmiri, Manipuri, and Sindhi, to a common script like Devanagari before translation, and reverting them post-translation.


### **Ai4Bharat Indic-Trans Encoder-Decoder Architecture :**

<p align="center">
  <img src="https://i.imgur.com/oaxPIK1.png" alt="Your Image Alt Text">
</p>

### **Translation Done Using Ai4Bharat Translator :**

| Hindi                                               | English                                              | Translated Text (AI4Bharat)                        |
| --------------------------------------------------- | ---------------------------------------------------- | -------------------------------------------------- |
| ऐ मेरे बन्दों! आज न तुम्हें कोई भय है और न तुम शोकाकुल होगे। | "O My servants, today no fear is on you, neither do you sorrow" | O My servants! Today you will have no fear nor will you grieve |
| "वही है जो आकाशों में भी पूज्य है और धरती में भी पूज्य है और वह तत्वदर्शी, सर्वज्ञ है" | "And it is He who in heaven is God and in earth is God; He is the All-wise, the All-knowing." | He is the one who is God in the heavens and God on the earth. He is the Wise and the All Knowing. |
| "रहे वे लोग जिन्होंने इनकार किया, तो उनके लिए तबाही है। और उनके कर्मों को अल्लाह ने अकारथ कर दिया" | "But as for the unbelievers, ill chance shall befall them! He will send their works astray." | "But as for those who disbelieve, for them is perdition. And He will waste their deeds." |
| फिर कैसी रही मेरी यातना और मेरे डरावे?                    | How then were My chastisement and My warnings?        | How [terrible] were My punishment and My warnings!   |

### **Comparsion Metrics -> Semantic Textual Similarity (STS) Scores :**

STS scores quantify the semantic similarity between two text sentences. Measures how closely the meaning of two sentences aligns. STS scores typically range between 0 and 1, representing the degree of semantic similarity between two text pieces.


0     :    No semantic similarity.


0.5   :    Moderate level of similarity.


1     :    Perfect semantic similarity, indicating the two texts convey the same meaning.


<p align="center">
  <img src="https://i.imgur.com/eBAxmSq.png" alt="Your Image Alt Text" width="250">
</p>

### **Final Results :**

| English                                                                                     | Eng_Trans                                                                      | AI4_Bharat_trans                                                              | Score_for_google_trans | Score_for_AI4bharat | Blue_Score_google_trans | Blue_Score_AI4bharat |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ---------------------- | -------------------- | ----------------------- | --------------------- |
| "O My servants, today no fear is on you, neither do you sorrow"                             | O my prisoners! Today you have no fear nor you will be heartbroken             | O My servants! Today you will have no fear nor will you grieve                  | 0.2912                 | 0.5101               | 0.002569                | 0.015894              |
| "And it is He who in heaven is God and in earth is God; He is the All - wise, the All - knowing." | "He is the one who is also revered in the sky and is also revered in the earth and he is a philosopher, omnisc." | He is the one who is God in the heavens and God on the earth. He is the Wise and the All Knowing. | 0.0531                 | 0.9191               | 0.005474                | 0.009825              |
| "But as for the unbelievers, ill chance shall befall them! He will send their works astray." | "Those who refused, so there is havoc for them.And Allah made their deeds unconscious" | "But as for those who disbelieve, for them is perdition. And He will waste their deeds." | 0                      | 0.7391               | 0                       | 0.056637              |
| How then were My chastisement and My warnings?                                               | Then how was my torture and my scared?                                         | How [terrible] were My punishment and My warnings!                             | 0                      | 0.2606               | 0                       | 0.003874              |




          
          
          

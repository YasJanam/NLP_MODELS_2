## Labratory_5

**Encoder-Architecture :**
Embedding ⟶ LSTM ⟶ Dropout ⟶  LayerNorm 

Dataset : **"manu/wnut_17"**

Tokenizer : **"bert-based-uncased"**

Data-Augmentation : **Entity-Replacement** + **Patterns-Based-Generation**

num-epochs : 15  

num-trained-epochs : 9 (early-stopping)

#### نتایج ارزیابی مدل روی داده های Test

| Entity     | Precision  | Recall     | F1         | تعداد (Number)       |
| ------------- | ---------- | ---------- | ---------- | -------------------- |
| corporation   | 0.0769     | 0.0758     | 0.0763     | 66                   |
| creative-work | 0.0000     | 0.0000     | 0.0000     | 142                  |
| group         | 0.0471     | 0.0242     | 0.0320     | 165                  |
| location      | 0.0940     | 0.0733     | 0.0824     | 150                  |
| person        | 0.2291     | 0.0956     | 0.1349     | 429                  |
| product       | 0.0200     | 0.0079     | 0.0113     | 127                  |
| **Overall**   | **0.1155** | **0.0575** | **0.0767** | **Accuracy: 0.9150** |

#### مقایسه نتایج

| Precision | Recall | F1-score | CODE | new-item     |
| --------- | ------ | -------- | ------------------- |------ |
| 0.1155 | 0.0575 | 0.0767 | Labratory_TinyNERModel_5 | dataAugmentation |
| 0.117     | 0.032  | 0.051    | Labratory_TinyNERModel_3 | skip-connection + Conv1D |
| 0.137     | 0.038  | 0.060    | TinyNERModel_2 | - |

###### در این کد معاری مدل را دوباره دستکاری کردم و کانولوشن و اسکیپ کانکشن رو حذف کردم. چون lstm خالی نتایج بهتری میداد. با DataAugmentation هم داده اموزش را از 3394 تا به 32760 تا افزایش دادم. تکنیک های افزایش دیتای به کار رفته همان هایی هستند که در کد DataAugmentation_4 توضیح داده شده اند. میبینیم که نتایج تغییر کرده، اما نه تغییری آنچنانی، دیتای افزایش داده را چند بار تغییر دادم. نتیجه بدست امده چندادن فرقی نمیکرد. پس به تغییری در معماری مدل احتیاج داریم. احتمالا این مدل بیشتر از این ظرفیت یادگیری ندارد.

## Labratory
یک سری تغییرات در معماری انکودر انجام شده و مدل دوباره اموزش دیده

**Encoder-Architecture** (New) :

Embedding ⟶ LSTM ⟶ Dropout ⟶ Projection(Linear-Layer) ⟶ Skip-Connection ⟶ LayerNorm ⟶ Conv1D(kenelr-size=3) ⟶ LayerNorm

Dataset: **"manu/wnut_17"**

Tokenizer: **"bert-base-uncased"**

num_epochs : **5**

#### نتایج عملکرد مدر روی داده های تست


| Entity / Metric      | Precision | Recall | F1-score | Number of Instances |
| -------------------- | --------- | ------ | -------- | ------------------- |
| corporation          | 0.000     | 0.000  | 0.000    | 66                  |
| creative-work        | 0.000     | 0.000  | 0.000    | 142                 |
| group                | 0.063     | 0.006  | 0.011    | 165                 |
| location             | 0.107     | 0.080  | 0.092    | 150                 |
| person               | 0.147     | 0.049  | 0.073    | 429                 |
| product              | 0.083     | 0.008  | 0.014    | 127                 |
| **Overall**          | 0.117     | 0.032  | 0.051    | -                   |
| **Overall Accuracy** | -         | -      | -        | 0.920               |





#### مقایسه نتایج 
| Entity / Metric      | Precision | Recall | F1-score | CODE |
| -------------------- | --------- | ------ | -------- | ------------------- |
| **Overall**          | 0.117     | 0.032  | 0.051    | Labratory_TinyNERModel_3 |
| **Overall**          | 0.137     | 0.038  | 0.060    | TinyNERModel_2 |

همانطور که میبینیم نتایج مدل قبلی (2) بهتر است!! علتش چیست ؟؟
###### حتی با مقایسه نتایج ارزیابی روی دیتای validation , Test متوجه **اورفیت** شده ایم، در حقیقت احتمالا مدل اورفیت شده است. دلیل این اورفیت احتمالا **کم بودن دیتا** است. باید دیتای آموزش را افزلیش دهیم. توجه کنید که تعداد ایپاک آموزشی این کد (3) از کد 2 کمتر است.

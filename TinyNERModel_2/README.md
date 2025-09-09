## TinyNERModel_2
Model-Architecture :  **Encoder** ( Embedding + LSTM )  ----> **LinearClassifier** ( Linear-Layer )

Dataset : __"manu/wnut_17"__

Tokenizer : **"bert-base-uncased"**

num_epochs : **6**

### نتایج عملکرد مدل روی داده های تست

| Entity / Metric      | Precision | Recall | F1-score | Number of Instances |
| -------------------- | --------- | ------ | -------- | ------------------- |
| corporation          | 0.000     | 0.000  | 0.000    | 66                  |
| creative-work        | 0.000     | 0.000  | 0.000    | 142                 |
| group                | 0.167     | 0.006  | 0.012    | 165                 |
| location             | 0.082     | 0.067  | 0.074    | 150                 |
| person               | 0.199     | 0.070  | 0.103    | 429                 |
| product              | 0.000     | 0.000  | 0.000    | 127                 |
| **Overall**          | 0.137     | 0.038  | 0.060    | -                   |
| **Overall Accuracy** | -         | -      | -        | 0.920               |


###### خب همینطور که میبینم نتایج اصلا جالب نیستند. اینکه  accuracy برابر 92 درصده به دلیل عملکرد خوب مدل نیست !! به این دلیل هستش که بیشتر label ها 'O' هستند و در حقیقت مدل یاد گرفته که 'O' ها رو خوب تشخیص بده !!

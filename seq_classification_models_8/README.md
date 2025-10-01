## seq_classification_models_8
کدِ seq_classification_models_7 همراه با پیاده سازی MultiHeadAttention.  
لینک کد seq_classification_models_7 :  
https://github.com/YasJanam/NLP_MODELS_2/tree/main/seq_classification_models_7
#### خلاصه ای از کد
پیاده سازی سه attention هیبریدی و ۴ بلاک feedforward برای ساخت ترنسفورمر.  
پیاده سازی MultiHeadAttention.    
ماژولاریتی در کد رعایت شده و با کلاس CustomTransformer به راحتی میشود هر اتنشن و هر ffn ای را سرِ هم کرد و یک ترنسفورمر جدید ساخت.  
با کلاس Model میتوان با هر لیستی از ترنسفورمر ها یک مدل طبقه بندی متن ساخت.  
به جز پیاده سازی MultiHeadAttention، عملکرد هر چهار اتنشن موجود در کد بر هر سه دیتاست sst,imdb و ۲۰ کلاسه، بررسی شده.
#### عملکرد چهار attention بر سه دیتاست
##### 🟢 دیتاست ها:
-  دیتاست imdb
-  دیتاست sst
-  دیتاست 20 کلاسه (https://github.com/YasJanam/NLP_MODELS_2/tree/main/sentiment_analysis_model_6/dataset(20_classes))
##### 🟡 attentions:
-  standard attention
-  gru_Attention (استفاده از خروجی **آخرین لایه پنهان** شبکه بازگشتی)
-  gru_Attention_2 (استفاده از خروجی شبکه بازگشتی)
-  conv_Attention

##### 🔵 table
| Attention | sst5-accuracy | imdb-accuracy | 20-classes-dataset-accuracy |
|--------|------|-------|-------|
| standard attention | 0.403 | 0.879 | 0.287 |
| gru_Attention_2 | 0.407 | 0.881 | 0.299 |
| gru_Attention | 0.375 | 0.808 | 0.260 |
| conv_Attention | 0.438 | 0.890 | 0.310 |

##### 🔴 نکات قابل توجه در مورد نتایج جدول
- برای هر سه دیتاست، conv_Attention از بقیه بهتر عمل کرد.    
- از بین دو اتنشن gru_Attention , gru_Attention_2 مکانیزم gru_Attention_2 بهتر بود، برخلاف تصور که انتظار میرفت gru_Attention برای تسک طبقه بندی متن بهتر باشه. به این علت که gru_Attention از آخرین لایه پنهان gru ها استفاده میکرد. آخرین لایه پنهان gru حاوی اطلاعاتی در مورد کل تکست ورودی هست، انتظار میره بیشتر در طبقه بندی متن بدرد بخوره!! در حالی که gru_Attention_2 از خروجی gru استفاده میکنه . خروجی gru توکن بعدی رو پیش بینی میکنه، تصور میشه که زیاد در تسک طبقه بندی متن بکار نیاد!! ولی خب در عمل اینطور نبود.   
- مکانیزم gru_Attention از همه بدتر بود. در حقیقت قبل از مشاهده نتایج تصورم این بود که gru_Attention به طور چشمگیر از همه بهتر باشه (چون از خروجی آخرین لایه پنهان gru استفاده میکرد).    
- تنها آزمایش های انجام شده اجراهای توی کد نیستند، خیلی بیشتر از 12 اجرای توی کد عملکرد این چهار attention رو بررسی کردم. 12 اجرای توی کد خلاصه ای بسیار ساده و واضح از مقایسه عملکرد attention ها است.

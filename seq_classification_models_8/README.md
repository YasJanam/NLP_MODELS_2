## seq_classification_models_8
کدِ seq_classification_models_7 همراه با پیاده سازی MultiHeadAttention.  
لینک کد seq_classification_models_7 :  
https://github.com/YasJanam/NLP_MODELS_2/blob/main/seq_classification_models_7/view_seq_classification_models_7.ipynb
#### خلاصه ای از کد
پیاده سازی سه attention هیبریدی و ۴ بلاک feedforward برای ساخت ترنسفورمر.  
پیاده سازی MultiHeadAttention.    
ماژولاریتی در کد رعایت شده و با کلاس CustomTransformer به راحتی میشود هر اتنشن و هر ffn ای را سرِ هم کرد و یک ترنسفورمر جدید ساخت.  
با کلاس Model میتوان با هر لیستی از ترنسفورمر ها یک مدل طبقه بندی متن ساخت.  
به جز پیاده سازی MultiHeadAttention، عملکرد هر چهار اتنشن موجود در کد بر هر سه دیتاست sst,imdb و ۲۰ کلاسه، بررسی شده.

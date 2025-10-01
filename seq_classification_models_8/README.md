## seq_classification_models_8
کدِ seq_classification_models_7 همراه با پیاده سازی MultiHeadAttention. 
#### خلاصه ای از کد
پیاده سازی ۳ attention هیبریدی و ۴ بلاک feedforward برای ساخت ترنسفورمر.  
ماژولاریتی در کد رعایت شده و با کلاس CustomTransformer به راحتی میشود هر اتنشن و هر ffn ای را سرِ هم کرد و یک ترنسفورمر جدید ساخت.  
با کلاس Model میتوان با هر لیستی از ترنسفورمر ها یک مدل طبقه بندی متن ساخت.  
همچنین MultiHeadAttention در این کد پیاده شده است.  
به جز پیاده سازی MultiHeadAttn، عملکرد هر چهار اتنشن موجود در کد بر هر سه دیتاست sst,imdb و ۲۰ کلاسه، بررسی شده.

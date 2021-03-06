# araugment

[![PyPI package](https://img.shields.io/badge/pip%20install-araugment-brightgreen)](https://pypi.org/project/araugment/) [![version number](https://img.shields.io/pypi/v/araugment?color=green&label=version)](https://github.com/ashaheedq/araugment/releases) [![Actions Status](https://github.com/ashaheedq/araugment/workflows/Test/badge.svg)](https://github.com/ashaheedq/araugment/actions) [![License](https://img.shields.io/github/license/ashaheedq/araugment)](https://github.com/ashaheedq/araugment/blob/main/LICENSE)

Augment Arabic data for deep learning tasks

## There are two methods in this library 
- back_translate: Translate text to a foreign language then translate back to original language to augment data
- markov: This method uses Markov chains to string together n new sequences of words based on previous sequences.

Installation
====
```
pip install araugment
```
***
  
  
Usage
=====
### Back Translate
```python
from araugment import back_translate
text = "بلغت العربية بفضل القرآن من الاتساع مدىً لا تكاد تعرفه أي لغة أخرى من لغات الدنيا"

#default value for original is "ar" which stands for Arabic
print(back_translate(text, original="ar", target="en"))
-> 'اللغة العربية بفضل القرآن من التوسع لا تحدد تقريبا بأي لغة أخرى'

```

### Markov Chains
```python
from araugment import markov
text = pd.read_csv('test.tsv', sep="\t", encoding='utf-8')
doc = text.loc[text.Target == "Neutral", 'Text'].tolist()
print(markov(doc, 5))
-> ['الخاص مليان سنين دون فاءده اتصلوا علي العملاء بلاغ رقم ومتاكده بلاغي مو اول واحد',
 'السلام عليكم عندي مشكله لي اسبوع رافعه طلب و لم يتم حل المشكله و البلاغ الحين ضمن البلاغات المغلقه',
 'و الله دخلته كذا بس مع هيك تعودنا نمد السلام',
 'سواق يمني جده توصيل مشاوير الحويه الطايف مكه جده وضواحيهابسعار مخفضه لتواصل خاص او واتساب',
 'ازمه كورونا يارب رحمتك بس']

```
***

License
====
araugment is licensed under the MIT License. The terms are as follows:  

```
MIT License  

Copyright (c) 2021 ashaheedq  

Permission is hereby granted, free of charge, to any person obtaining a copy  
of this software and associated documentation files (the "Software"), to deal  
in the Software without restriction, including without limitation the rights  
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell  
copies of the Software, and to permit persons to whom the Software is  
furnished to do so, subject to the following conditions:  

The above copyright notice and this permission notice shall be included in all  
copies or substantial portions of the Software.  

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR  
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,  
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE  
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER  
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,  
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE  
SOFTWARE.  
```
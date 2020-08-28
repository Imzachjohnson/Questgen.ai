# Questgen AI
Questgen AI is focused on developing Question generation algorithms using state-of-the-art Natural Language Processing models. It provides easy to use classes and enables you to be one call away from generating questions out of any given parapgraph in your required format, be it MCQ, Single word, Boolean type or Paraphrasing.

*Currently we are focused on generating questions that are gramatically correct and semantically meaningful in nature using Text-to-Text Transfer Transformers (T5).*

<img src= './quest.gif' >

### Various formats of Questions generated by the library are:- 
<pre>
  -- Normal Questions :     (What,Where,Who,how,When etc) <br>
  -- MCQ Questions :        Generate Questions with answers and similar options <br>
  -- Boolean Questions :    (Is,Did,Does etc) Output is expected either True/False <br>
  -- Paraphrase Questions : Generate similar but different questions from a given question <br>
  -- Answering :            Any question can be answered provided with a context.
</pre>

### Prerequisites
```
pip install -r requirements.txt
pip install git+https://github.com/boudinfl/pke.git
python -m nltk.downloader universal_tagset
python -m spacy download en 
```
### Using the library
```
pip install git+https://github.com/ramsrigouthamg/Questgen.ai
wget https://github.com/explosion/sense2vec/releases/download/v1.0.0/s2v_reddit_2015_md.tar.gz
tar -xvf  s2v_reddit_2015_md.tar.gz
```

**For MCQ, Short Question and Paraphrasing Question generation**
```
import Questgen
generator= main.QGen()                          #instance of QGen class

payload={
    "input_text" :   'Text',
    "max_questions" : 5                         #Default 4
    }
    
output1= generator.predict_mcq(payload)         #For MCQ generation       
output2= generator.predict_shortq(payload)      #For Short Answers' Question generaiton
output3= generator.paraphrase(payload)          #For paraphrasing questions
```


**For Boolean question generation**
```
import Questgen
generator= main.BoolQGen()                      #instance of BoolQGen class

payload={
    "input_text" :   'Text',
    "max_questions" : 5                         #Default 4
    }

output= generator.predict_boolq(payload)
```


**For Answer prediction from a given question**
```
import Questgen
generator= main.AnswerPredictor()

payload={
    "input_text" :   'Text',
    "input_question" : 'Question'                         
    }

output= generator.predict_answer(payload)
```

### Colab Demo
<a href="https://colab.research.google.com/drive/144vAp5UVFHqPWLEXtBX4gaAPeVZumlzK?usp=sharing">Google Colab </a>

### NLP models used

For maintaining meaningfulness in Questions, Questgen uses Three T5 models, one for Boolean Question generation, one for MCQ, Short Questions, Paraphrasing and one for Answer generation.

### Online Demo website
Under development...
https://questgen.ai/

# Human evaluation studies

This folder contains human evaluation studies.

## Evaluation of chatbot models:
directory: model-evaluation

Chatbot models were evaluated by 10 human evaluators by question-answer pairs where the answer was generated by the models. Original answers by humans also included. 

Three metrics were used:
1. Intelligible (Ymmärrettävyys): the answer is an understandable sentence in some context
2. Coherence (Johdonmukaisuus): sentence answers the question
3. Grammar (Kielioppi): the sentence is the grammatically correct form in context of conversational Finnish.

The standard scale from 1 (very poor) to 5 (very good) was used. 

Files: 
- QA-pairs : Questions and generated answers.
- Evaluation-survey.pdf : Survey we used to collect the evaluation.
- QA-pair-evaluation-results.xlsx : Results.


## Evaluation of hits@1/10 set
directory: hits-at-10

hits@1/10 set is used to automatically evaluate models. The set contains 300 questions and 10 answers for each question. One of the answers is correct and other 9 are randomly picked from FinChat evaluation set. Questions were automatically generated, therefore questions with no clear answer were filtered out by hand resulting set of 226 questions.

The filtered set was evaluated by humans guessing the correct answer for each question.

Files:
- topX_gen_r_at_k.ipynb : Notebook to generate eval_topX_recall_at_10_415.csv
- eval_topX_recall_at_10_415.csv : Contains questions and answers.
- human_evaluation_recall10.py : Script for evaluation. See more details in the beginning of the file.
- answers*.txt : Evaluation results from each participants. Each participant had different set of questions.
  - Each row has the row number of the question and 1 for correct answer, 0 for incorrect answer.

### How to read the topX files

- the separator for the different fields is ¤
- the separator for the different possible sentences is |
- TEXT is the question sentence
- CHOICE SENTENCES are the answer sentences. The first is the correct. Rest are false, and separated with |.
- <MS> (message sent) marks when the user sent multiple messages in a row.
  example: first message <MS> second message <MS> third message.



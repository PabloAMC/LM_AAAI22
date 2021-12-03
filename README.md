<div align="center">   

  # How General-Purpose Is a Language Model? Usefulness and Safety with Human Prompters in the Wild

  [![Conference](http://img.shields.io/badge/AAAI-2022-4b44ce.svg)]() 
 </div>

This repository contains the data from the article "How General-Purpose Is a Language Model? Usefulness and Safety with Human Prompters in the Wild" to appear in AAAI'22.



## To read the data use
```
import json
import pandas as pd
df = pd.io.json.read_json('./with_GPT3.json')
df.head()
```
or 

```
df3 = pd.io.json.read_json('./without_GPT3.json')
df.head()
```

## Data description

The file `with_GPT3.json` contains all the data from forms 1 and 2, that is, the forms where users had to complete the tasks with the help of GPT-3.
The columns labelled as `form_1_...` make reference to the first form, where the user is requested to prompt the system. Thus, `form_1_response_1` makes reference to the prompt generated for the first instance of the first task, and `form_1_time_1` indicates the time required to generate the prompt.
Remember that there are 4 tasks each with 3 instances each, so `form_1_...` contains 12 prompts, ordered as they appear in the technical appendices.

Similarly, `gpt3_answer_...` makes reference to the answer generated by GPT-3. The columns `form_2_...` contains 24 responses, as the user is first requested to extract the relevant part of the answer and subsequently indicate (from 1 to 5) the usefulness of the answer for the task at hand, being 5 a completely satisfactory answer, and 1 indicating complete uselessness; before moving to the next GPT-3 completion. The time for each answer is also measured. Finally demographic data is also included:
- `age`.
- `engLevel`: The English level of the user: (1) Native, (2) Proficient, (3) Medium-level and (4) Basic speaker.
- `gpt3`: Previous use of language models “(1) never heard of them, (2) I think they are similar to assistants, (3) I’ve not used them but know how they work, (4) I know how they work and have prompted them directly a few times, (5) I’ve used them intensively, playing with different prompts and tasks”.
- `assistants`: Previous use of virtual assistants: (yes/no).

On the other hand, `without_GPT3.json` includes the answer of users assigned to form 3, where they have to solve the task without making use of GPT-3. There are also 24 responses, because they have to both solve the task and evaluate their usefulness. Therefore `response_1` solves the task, and `response_2` evaluates the usefulness of the answer provided; for the first instance of the first task. Demographic data (`age` and `engLevel` is also collected).

# How General-Purpose Is a Language Model? Usefulness and Safety with Human Prompters in the Wild
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

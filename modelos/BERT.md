# Modelo BERT

> O **BERT (Bidirectional Encoder Representations from Transformers)** é um modelo de linguagem natural criado pelo Google AI Research, projetado para compreender o contexto de palavras em uma frase de forma bidirecional. Ele foi introduzido em 2018 no artigo ["BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding"](https://arxiv.org/abs/1810.04805).

---
## 🔍 Características Principais

- **Criador:** Google AI Research
- **Arquitetura:** Baseada em Transformers, com camadas de codificadores (encoders) que processam as entradas bidirecionalmente.
- **Treinamento:** Pré-treinado em grandes corporações de texto, como Wikipedia e BookCorpus.
- **Objetivos de Treinamento:**
  - *Masked Language Model (MLM):* Predição de palavras mascaradas no texto.
  - *Next Sentence Prediction (NSP):* Predição de frases.

---
## 🧪 Desempenho em Benchmarks

O BERT foi avaliado em diversos benchmarks e mostrou resultados de ponta em várias tarefas de Processamento de Linguagem Natural (NLP).

| **Benchmark**         | **Tarefa**                    | **Métrica**       | **Resultado** | **Fonte**                                                                |
|------------------------|-------------------------------|-------------------|---------------|-------------------------------------------------------------------------|
| SQuAD 1.1             | Respostas a perguntas         | Exatidão          | 93.2%         | [Artigo Original](https://arxiv.org/abs/1810.04805)                      |
| GLUE                  | Classificação de sentenças    | Pontuação média   | 80.5          | [GLUE Leaderboard](https://gluebenchmark.com/leaderboard)                |
| CoLA                  | Aceitabilidade linguística    | Matthews Corr.    | 60.5          | [Resultados em CoLA](https://nyu-mll.github.io/CoLA/)                    |
| MNLI                  | Inferência textual            | Exatidão          | 84.6%         | [MNLI Benchmark](https://cims.nyu.edu/~sbowman/multinli/)                |
| SST-2                 | Análise de sentimentos        | Exatidão          | 94.9%         | [SST-2 Dataset](https://nlp.stanford.edu/sentiment/treebank.html)        |
| RACE                  | Compreensão de leitura        | Taxa de acerto    | 65.0%         | [RACE Dataset](http://www.cs.cmu.edu/~glai1/data/race/)                  |
| QNLI                  | Questões naturais             | Exatidão          | 91.2%         | [QNLI Benchmark](https://gluebenchmark.com/tasks)                        |

---
## 📚 Pesquisas Relevantes

- **Fine-Tuning de Tarefas Específicas:** Pesquisas demonstram que o BERT pode ser ajustado para várias tarefas, incluindo classificação de texto, tradução e análise de sentimentos.
- **Impacto em Modelos Posteriores:** O BERT influenciou a criação de modelos avançados como RoBERTa, DistilBERT e ALBERT.

---
## 📥 Versões

| Versão     | Camadas | Cabeças de Atenção | Dimensões Ocultas | Dimensões Feed-Forward | Parâmetros    |
|------------|---------|--------------------|-------------------|------------------------|---------------|
| **BERT base** | 12      | 12                 | 768               | 3072                   | 110 milhões  |
| **BERT large**| 24      | 16                 | 1024              | 4096                   | 340 milhões  |

---
## 💻 Requisitos Recomendados

| Versão       | Memória RAM          | VRAM          | Processador                      | Observações                            |
|--------------|----------------------|---------------|-----------------------------------|----------------------------------------|
| **BERT base**  | 16 GB               | 6 GB          | CPU com 4 núcleos (ex. i7 ou Ryzen 5) | Ideal para tarefas moderadas de NLP    |
| **BERT large** | 32 GB               | 10 GB         | CPU com 8 núcleos (ex. i9 ou Ryzen 7) | Necessita de maior poder computacional |

---
## ✅ Prós
1. **Compreensão do Contexto**: Altamente eficaz em entender o contexto completo de uma frase;
2. **Processamento Bidirecional**: O BERT processa o texto de maneira bidirecional (ambos os lados do texto), proporcionando maior precisão nas respostas;
3. **Ideal para classificação de texto**: O BERT foi projetado para compreensão e classificação de texto.

---
## ❌ Contras
1. **Pesado**: O BERT, especialmente nas versões maiores como a Large, é pesado e requer grande poder computacional;
2. **Tempo de Inferência alto**: Devido à sua arquitetura bidirecional, o tempo de processamento é demorado;
3. **Limite de Caracteres em uma frase**: O BERT tem um limite de tamanho de sequência (geralmente 512 tokens);
4. **Não é ideal para geração de texto**: O BERT foi projetado para compreensão e classificação de texto, não para geração.

---
## 🚀 Como Usar o BERT

### 1. **Instalação**
Certifique-se de ter o Python instalado e instale a biblioteca `transformers`:
```bash
pip install transformers
```

### 2. **Carregar o Modelo e o Tokenizer**
```python
from transformers import AutoTokenizer, BertModel
import torch

tokenizer = AutoTokenizer.from_pretrained("google-bert/bert-base-uncased")
model = BertModel.from_pretrained("google-bert/bert-base-uncased")

inputs = tokenizer("Hello, my dog is cute", return_tensors="pt")
outputs = model(**inputs)

last_hidden_states = outputs.last_hidden_state
```

### 3. **Tokenização**
```python
from transformers import BertConfig, BertModel

# Initializing a BERT google-bert/bert-base-uncased style configuration
configuration = BertConfig()

# Initializing a model (with random weights) from the google-bert/bert-base-uncased style configuration
model = BertModel(configuration)

# Accessing the model configuration
configuration = model.config
```

### 4. **Multiplas Escolhas**
```python
from transformers import AutoTokenizer, TFBertForMultipleChoice
import tensorflow as tf

tokenizer = AutoTokenizer.from_pretrained("google-bert/bert-base-uncased")
model = TFBertForMultipleChoice.from_pretrained("google-bert/bert-base-uncased")

prompt = "In Italy, pizza served in formal settings, such as at a restaurant, is presented unsliced."
choice0 = "It is eaten with a fork and a knife."
choice1 = "It is eaten while held in the hand."

encoding = tokenizer([prompt, prompt], [choice0, choice1], return_tensors="tf", padding=True)
inputs = {k: tf.expand_dims(v, 0) for k, v in encoding.items()}
outputs = model(inputs)  # batch size is 1

# the linear classifier still needs to be trained
logits = outputs.logits
```

### 5. **Classificação de Inputs**
> O BERT é frequentemente usado como modelo em tarefas de classificação, como análise de sentimentos.

```python
import torch
from transformers import AutoTokenizer, BertForSequenceClassification

tokenizer = AutoTokenizer.from_pretrained("textattack/bert-base-uncased-yelp-polarity")
model = BertForSequenceClassification.from_pretrained("textattack/bert-base-uncased-yelp-polarity")

inputs = tokenizer("Hello, my dog is cute", return_tensors="pt")

with torch.no_grad():
    logits = model(**inputs).logits

predicted_class_id = logits.argmax().item()
model.config.id2label[predicted_class_id]

# To train a model on `num_labels` classes, you can pass `num_labels=num_labels` to `.from_pretrained(...)`
num_labels = len(model.config.id2label)
model = BertForSequenceClassification.from_pretrained("textattack/bert-base-uncased-yelp-polarity", num_labels=num_labels)

labels = torch.tensor([1])
loss = model(**inputs, labels=labels).loss
round(loss.item(), 2)
```

### 6. Perguntas e Respostas

```python
from transformers import AutoTokenizer, TFBertForQuestionAnswering
import tensorflow as tf

tokenizer = AutoTokenizer.from_pretrained("ydshieh/bert-base-cased-squad2")
model = TFBertForQuestionAnswering.from_pretrained("ydshieh/bert-base-cased-squad2")

question, text = "Who was Jim Henson?", "Jim Henson was a nice puppet"

inputs = tokenizer(question, text, return_tensors="tf")
outputs = model(**inputs)

answer_start_index = int(tf.math.argmax(outputs.start_logits, axis=-1)[0])
answer_end_index = int(tf.math.argmax(outputs.end_logits, axis=-1)[0])

predict_answer_tokens = inputs.input_ids[0, answer_start_index : answer_end_index + 1]
tokenizer.decode(predict_answer_tokens)
```

---

## 📜 Fontes

- [Artigo Original do BERT](https://arxiv.org/abs/1810.04805)
- [Documentação do Hugging Face](https://huggingface.co/docs/transformers/en/model_doc/bert)
- [Resultados em Benchmarks](https://gluebenchmark.com/leaderboard)
- [Benchmarking BERT-based Models](https://medium.com/@kefactor/benchmarking-bert-based-models-for-text-classification-7182db4df89a)
- [SQuAD Dataset](https://rajpurkar.github.io/SQuAD-explorer/)
- [CoLA Dataset](https://nyu-mll.github.io/CoLA/)
- [RACE Dataset](http://www.cs.cmu.edu/~glai1/data/race/)
- [MNLI Benchmark](https://cims.nyu.edu/~sbowman/multinli/)
- [SST-2 Dataset](https://nlp.stanford.edu/sentiment/treebank.html)
- [QNLI Benchmark](https://gluebenchmark.com/tasks)


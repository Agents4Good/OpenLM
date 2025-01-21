# Modelo BERT

> O **BERT (Bidirectional Encoder Representations from Transformers)** é um modelo de linguagem natural criado pelo Google AI Research, projetado para compreender o contexto de palavras em uma frase de forma bidirecional. Ele foi introduzido em 2018 no artigo ["BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding"](https://arxiv.org/abs/1810.04805).

---
## 🔍 Características Principais

- **Criador:** Google AI Research
- **Arquitetura:** Baseada em Transformers, com camadas empilhadas de codificadores (encoders) que processam as entradas bidirecionalmente.
- **Treinamento:** Pré-treinado em grandes corpora de texto, como Wikipedia e BookCorpus.
- **Objetivos de Treinamento:**
  - *Masked Language Model (MLM):* Predição de palavras mascaradas no texto.
  - *Next Sentence Prediction (NSP):* Predição se uma frase segue outra em um par.

---
## 🧪 Desempenho em Benchmarks

O BERT foi avaliado em diversos benchmarks e mostrou resultados de ponta em várias tarefas de Processamento de Linguagem Natural (NLP).

| **Benchmark**         | **Tarefa**                    | **Métrica**       | **Resultado** | **Fonte**                                                                 |
|------------------------|-------------------------------|-------------------|---------------|---------------------------------------------------------------------------|
| SQuAD 1.1             | Respostas a perguntas         | Exatidão          | 93.2%         | [Artigo Original](https://arxiv.org/abs/1810.04805)                        |
| GLUE                  | Classificação de sentenças    | Pontuação média   | 80.5          | [GLUE Leaderboard](https://gluebenchmark.com/leaderboard)                |
| CoLA                  | Aceitabilidade linguística    | Matthews Corr.    | 60.5          | [Resultados em CoLA](https://nyu-mll.github.io/CoLA/)                    |

---

## 📚 Pesquisas Relevantes

- **Fine-Tuning de Tarefas Específicas:** Pesquisas demonstram que o BERT pode ser ajustado para várias tarefas, incluindo classificação de texto, tradução e análise de sentimentos.
- **Impacto em Modelos Posteriores:** O BERT influenciou a criação de modelos avançados como RoBERTa, DistilBERT e ALBERT.

---
## 🚀 Como Usar o BERT

### 1. **Instalação**
Certifique-se de ter o Python instalado e instale a biblioteca `transformers`:
```bash
pip install transformers
```

### 2. **Carregar o Modelo e o Tokenizer**
```python
from transformers import BertTokenizer, BertModel

# Carregar tokenizer e modelo pré-treinado
tokenizer = BertTokenizer.from_pretrained("bert-base-uncased")
model = BertModel.from_pretrained("bert-base-uncased")
```

### 3. **Tokenização**
```python
# Entrada de exemplo
texto = "O BERT é incrível para NLP!"

# Tokenizar entrada
tokens = tokenizer(texto, return_tensors="pt")
print(tokens)
```

### 4. **Inferência**
```python
# Passar tokens pelo modelo
output = model(**tokens)

# Representação dos tokens
print(output.last_hidden_state)
```

---

## 📜 Artigos

- [Artigo Original do BERT](https://arxiv.org/abs/1810.04805)
- [Documentação do Hugging Face](https://huggingface.co/docs/transformers/en/model_doc/bert)
- [Resultados em Benchmarks](https://gluebenchmark.com/leaderboard)

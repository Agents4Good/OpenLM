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
## ✅ Prós
1. Compreensão do Contexto: Altamente eficaz em entender o contexto completo de uma frase;
2. Processamento Bidirecional: O BERT processa o texto de maneira bidirecional (ambos os lados do texto), proporcionando maior precisão nas respostas;
3. Ideal para classificação de texto: O BERT foi projetado para compreensão e classificação de texto.

---
## ❌ Contras
1. Pesado: O BERT, especialmente nas versões maiores como a Large, é pesado e requer grande poder computacional;
2. Tempo de Inferência alto: Devido à sua arquitetura bidirecional, o tempo de processamento é demorado;
3. Limite de Caracteres em uma frase: O BERT tem um limite de tamanho de sequência (geralmente 512 tokens);
4. Não é ideal para geração de texto: O BERT foi projetado para compreensão e classificação de texto, não para geração.

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

### 5. **Classificação de Inputs**
> O BERT é frequentemente usado como modelo em tarefas de classificação, como análise de sentimentos.

```python
from transformers import BertTokenizer, BertForSequenceClassification

# Carregar tokenizer e modelo pré-treinado para classificação
tokenizer = BertTokenizer.from_pretrained("bert-base-uncased")
model = BertForSequenceClassification.from_pretrained("bert-base-uncased", num_labels=2)

# Texto de entrada
texto = "Este produto é excelente!"

# Tokenizar entrada
inputs = tokenizer(texto, return_tensors="pt")

# Realizar previsão
outputs = model(**inputs)

# Logits (saídas brutas)
logits = outputs.logits
print(logits)

# Predição final (0 ou 1, dependendo do mapeamento de rótulos)
predicao = torch.argmax(logits, dim=1)
print(f"Sentimento: {'Positivo' if predicao == 1 else 'Negativo'}")
```

### 6. Perguntas e Respostas

```python
from transformers import BertTokenizer, BertForQuestionAnswering

# Carregar tokenizer e modelo para perguntas e respostas
tokenizer = BertTokenizer.from_pretrained("bert-large-uncased-whole-word-masking-finetuned-squad")
model = BertForQuestionAnswering.from_pretrained("bert-large-uncased-whole-word-masking-finetuned-squad")

# Contexto e pergunta
contexto = "A inteligência artificial tem muitos usos no mundo moderno, incluindo NLP."
pergunta = "Quais são os usos da inteligência artificial?"

# Preparar entrada
inputs = tokenizer.encode_plus(pergunta, contexto, return_tensors="pt")

# Obter respostas do modelo
outputs = model(**inputs)
start_scores = outputs.start_logits
end_scores = outputs.end_logits

# Identificar tokens da resposta
start_index = torch.argmax(start_scores)
end_index = torch.argmax(end_scores)

# Decodificar resposta
resposta = tokenizer.decode(inputs.input_ids[0][start_index:end_index + 1])
print(f"Resposta: {resposta}")
```

---

## 📜 Artigos

- [Artigo Original do BERT](https://arxiv.org/abs/1810.04805)
- [Documentação do Hugging Face](https://huggingface.co/docs/transformers/en/model_doc/bert)
- [Resultados em Benchmarks](https://gluebenchmark.com/leaderboard)

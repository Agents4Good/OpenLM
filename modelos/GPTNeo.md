# Modelo GPT Neo

> O **GPT Neo** é um modelo de linguagem baseado em transformadores, desenvolvido pela EleutherAI, projetado para geração de texto coerente e natural.
> Ele foi introduzido como uma alternativa de código aberto aos modelos GPT da OpenAI.

---
## 🔍 Características Principais

- **Criador:** EleutherAI
- **Arquitetura:** Baseada em Transformers, utilizando camadas de decodificadores (decoders) com atenção unidirecional.
- **Treinamento:** Pré-treinado em grandes corporações de texto, como The Pile, que inclui diversas fontes de dados.
- **Capacidades:**
  - Geração de texto coerente e criativo;
  - Completar frases e parágrafos;
  - Suporte para tarefas como tradução, resumo e perguntas e respostas.

---
## 🧪 Desempenho em Benchmarks

O GPT Neo é avaliado principalmente em tarefas de geração de texto e NLP.
> Fonte: [Artigo - Medium](https://medium.com/georgian-impact-blog/gpt-neo-vs-gpt-3-are-commercialized-nlp-models-really-that-much-better-f4c73ffce10b)

| **Modelo**          | **0-shot (%)** | **1-shot (%)** | **4-shot (%)** | **8-shot (%)** | **Custo 0-shot** | **Custo 8-shot** | **Acurácia Geral (%)** |
|----------------------|----------------|----------------|----------------|----------------|------------------|------------------|-------------------------|
| GPT-Neo 1.3B         | 56.9          | 84.4           | 83.5           | 78.1           | $0               | $0               | 84.4                   |
| GPT-Neo 2.7B         | 6.97          | 73.1           | 84.4           | 68.0           | $0               | $0               | 84.4                   |
| GPT-3 ada (2.7B)     | 47.6          | 60.8           | 72.6           | 62.5           | $0.04/run        | $0.44/run        | 88.4                   |
| GPT-3 curie (13B)    | 45.1          | 83.4           | 89.3           | 86.1           | $0.33/run        | $3.35/run        | 95.1                   |
| GPT-3 davinci (175B) | 36.7          | 85.8           | 94.3           | 95.1           | $3.26/run        | $33.43/run       | 95.1                   |
| SMART-RoBERTa Large  | -             | -              | -              | -              | -                | -                | 97.5                   |

---
## 📚 Pesquisas Relevantes

- Confira diversos artigos feitos pela **EleutherAI**: https://www.eleuther.ai/research

---
## 📥 Versões

| **Versão**         | **Camadas** | **Cabeças de Atenção** | **Dimensões Ocultas** | **Dimensões Feed-Forward** | **Parâmetros** |
|---------------------|-------------|------------------------|------------------------|----------------------------|----------------|
| GPT Neo 125M       | 12          | 12                     | 768                    | 3072                       | 125 milhões    |
| GPT Neo 1.3B       | 24          | 16                     | 2048                   | 8192                       | 1,3 bilhões    |
| GPT Neo 2.7B       | 32          | 20                     | 2560                   | 10240                      | 2,7 bilhões    |

---
## 💻​ Requisitos Recomendados

| **Versão**         | **Memória RAM** | **Memória da GPU** | **Armazenamento** |
|---------------------|-----------------|--------------------|-------------------|
| GPT Neo 125M       | 8 GB            | 4 GB               | 500 MB            |
| GPT Neo 1.3B       | 16 GB           | 12 GB              | 2 GB              |
| GPT Neo 2.7B       | 32 GB           | 24 GB              | 5 GB              |

---
## ✅ Prós
1. **Acessibilidade**: Código aberto, permitindo customizações e integrações diversas;
2. **Escalabilidade**: Disponível em tamanhos variados, adequados para diferentes aplicações;
3. Eficiência para tarefas de **geração de texto**: Altamente eficaz em criar textos criativos e coerentes.

---
## ❌ Contras
1. Requer **hardware robusto**: Modelos maiores exigem GPUs ou TPUs para treinamento e inferência;
2. **Menor desempenho** em comparação com GPT proprietários: Resultados ligeiramente inferiores aos modelos mais avançados da OpenAI;
3. **Limitação de contexto**: Restrições no comprimento de entrada devido ao design da arquitetura.

---
## 🚀 Como Usar o GPT Neo

### 1. **Instalação**
Certifique-se de ter o Python instalado e instale a biblioteca `transformers`:
```bash
pip3 install transformers

git clone https://github.com/EleutherAI/GPTNeo
cd GPTNeo
pip3 install -r requirements.txt
```

### 2. **Configurar com Parâmetros**
```python
from transformers import GPTNeoConfig, GPTNeoModel

# Initializing a GPTNeo EleutherAI/gpt-neo-1.3B style configuration
configuration = GPTNeoConfig()

# Initializing a model (with random weights) from the EleutherAI/gpt-neo-1.3B style configuration
model = GPTNeoModel(configuration)

# Accessing the model configuration
configuration = model.config
```

### 3. **Uso de Tokens**
```python
from transformers import AutoTokenizer, GPTNeoModel
import torch

tokenizer = AutoTokenizer.from_pretrained("EleutherAI/gpt-neo-1.3B")
model = GPTNeoModel.from_pretrained("EleutherAI/gpt-neo-1.3B")

inputs = tokenizer("Hello, my dog is cute", return_tensors="pt")
outputs = model(**inputs)

last_hidden_states = outputs.last_hidden_state
```

### 4. **Geração de Texto**
```python
from transformers import GPTNeoForCausalLM, GPT2Tokenizer

model = GPTNeoForCausalLM.from_pretrained("EleutherAI/gpt-neo-1.3B")
tokenizer = GPT2Tokenizer.from_pretrained("EleutherAI/gpt-neo-1.3B")

prompt = (
    "In a shocking finding, scientists discovered a herd of unicorns living in a remote, "
    "previously unexplored valley, in the Andes Mountains. Even more surprising to the "
    "researchers was the fact that the unicorns spoke perfect English."
)

input_ids = tokenizer(prompt, return_tensors="pt").input_ids

gen_tokens = model.generate(
    input_ids,
    do_sample=True,
    temperature=0.9,
    max_length=100,
)
gen_text = tokenizer.batch_decode(gen_tokens)[0]
```

### 5. **Ajuste Fino (Fine-Tuning)**
O GPT Neo pode ser ajustado para tarefas específicas utilizando datasets customizados. O ajuste fino é realizado com bibliotecas como `transformers` e `datasets`:
```python
from transformers import Trainer, TrainingArguments

# Configurações do treinamento
training_args = TrainingArguments(
    output_dir="./results",
    per_device_train_batch_size=2,
    num_train_epochs=3,
    logging_dir="./logs",
    save_steps=10_000,
)

trainer = Trainer(
    model=model,
    args=training_args,
    train_dataset=seu_dataset_treino,
    eval_dataset=seu_dataset_validacao
)

trainer.train()
```

---
## 📜 Fontes

- [Documentação do GPT Neo](https://huggingface.co/docs/transformers/en/model_doc/gpt_neo)
- [The Pile Dataset](https://arxiv.org/abs/2101.00027)
- [Repositório da EleutherAI](https://github.com/EleutherAI)


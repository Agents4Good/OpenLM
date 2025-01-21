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

| **Benchmark**         | **Tarefa**                    | **Métrica**       | **Resultado** | **Fonte**                                        |
|------------------------|-------------------------------|-------------------|---------------|------------------------------------------------|
| EleutherAI Evaluation | Geração de texto criativo     | Coerência         | Alta          | [Documentação GPT Neo](https://huggingface.co/docs/transformers/en/model_doc/gpt_neo) |
| The Pile Perplexity   | Qualidade do texto gerado     | Perplexidade      | Baixa         | [The Pile Dataset](https://arxiv.org/abs/2101.00027)            |

---
## 📚 Pesquisas Relevantes

- Confira diversos artigos feitos pela **EleutherAI**: https://www.eleuther.ai/research

---
## ✅ Prós
1. Acessibilidade: Código aberto, permitindo customizações e integrações diversas;
2. Escalabilidade: Disponível em tamanhos variados, adequados para diferentes aplicações;
3. Eficiência para tarefas de geração de texto: Altamente eficaz em criar textos criativos e coerentes.

---
## ❌ Contras
1. Requer hardware robusto: Modelos maiores exigem GPUs ou TPUs para treinamento e inferência;
2. Menor desempenho em comparação com GPT proprietários: Resultados ligeiramente inferiores aos modelos mais avançados da OpenAI;
3. Limitação de contexto: Restrições no comprimento de entrada devido ao design da arquitetura.

---
## 🚀 Como Usar o GPT Neo

### 1. **Instalação**
Certifique-se de ter o Python instalado e instale a biblioteca `transformers`:
```bash
pip install transformers
```

### 2. **Carregar o Modelo e o Tokenizer**
```python
from transformers import GPTNeoForCausalLM, AutoTokenizer

# Carregar tokenizer e modelo pré-treinado
modelo = "EleutherAI/gpt-neo-125M"
tokenizer = AutoTokenizer.from_pretrained(modelo)
model = GPTNeoForCausalLM.from_pretrained(modelo)
```

### 3. **Geração de Texto**
```python
# Entrada de exemplo
texto_entrada = "A inteligência artificial está revolucionando"

# Tokenizar entrada
inputs = tokenizer(texto_entrada, return_tensors="pt")

# Gerar texto
outputs = model.generate(inputs.input_ids, max_length=50, do_sample=True)

# Decodificar saída
teste_saida = tokenizer.decode(outputs[0], skip_special_tokens=True)
print(teste_saida)
```

### 4. **Ajuste Fino (Fine-Tuning)**
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


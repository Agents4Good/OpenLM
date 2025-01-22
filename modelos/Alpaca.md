# Modelo Alpaca

> O **Alpaca** é um modelo de linguagem desenvolvido pelo Centro de Pesquisa em Fundamentos de Modelos (CRFM) da Universidade de Stanford. Trata-se de uma versão ajustada do modelo LLaMA 7B da Meta, treinada para seguir instruções de maneira semelhante ao modelo text-davinci-003 da OpenAI.

---

## 🔍 Características Principais

- **Criador:** Centro de Pesquisa em Fundamentos de Modelos (CRFM) da Universidade de Stanford
- **Arquitetura:** Baseada no modelo LLaMA 7B da Meta
- **Treinamento:** Ajustado utilizando um conjunto de 52.000 pares de instrução-resposta gerados pelo modelo text-davinci-003 da OpenAI
- **Capacidades:**
  - Segue instruções de forma eficaz
  - Gera respostas coerentes e informativas
  - Aplicável em tarefas como resumo, tradução e perguntas e respostas

---

## 🧪 Desempenho em Benchmarks

O desempenho do Alpaca foi avaliado utilizando o AlpacaEval, uma ferramenta de avaliação automática baseada em LLMs. Abaixo está uma comparação de desempenho entre diferentes modelos:
> Fonte: https://tatsu-lab.github.io/alpaca_eval/<br>
> GPT-4 foi usado como referência nos testes.


| **Modelo**         | **Score GPT-4 (%)**  | **Desempenho Geral** |
|---------------------|---------------------|-----------------------|
| Alpaca 7B          | 90.2                 | Competitivo em tarefas de seguimento de instruções |
| LLaMA 7B           | 85.6                 | Base do Alpaca, sem ajustes para instruções        |
| text-davinci-003   | 95.8                 | Modelo proprietário da OpenAI                      |

---

## 📚 Pesquisas Relevantes

Confira o Blog da Universidade de Stanford: https://crfm.stanford.edu/blog.html

---

## 📥 Versões

| **Versão** | **Parâmetros** |
|-------------|----------------|
| Alpaca 7B   | 7 bilhões     |

---

## 💻 Requisitos Recomendados

| **Versão** | **Memória RAM** | **Memória da GPU** | **Armazenamento** |
|-------------|-----------------|----------------------|-------------------|
| Alpaca 7B   | 16 GB          | 12 GB               | 2 GB              |

---

## ✅ Prós

1. **Acessibilidade:** Modelo de código aberto, permitindo customizações e integrações diversas.
2. **Eficiência:** Desempenho competitivo em tarefas de seguimento de instruções.
3. **Custo-efetivo:** Treinamento realizado com um conjunto de dados gerado de forma econômica.

---

## ❌ Contras

1. **Dependência de Dados Sintéticos:** O conjunto de dados de treinamento foi gerado por outro modelo de linguagem, o que pode introduzir vieses.
2. **Limitações de Escalabilidade:** Como é baseado no LLaMA 7B, pode não alcançar o desempenho de modelos maiores em tarefas complexas.
3. **Necessidade de Recursos Computacionais:** Embora menor que alguns modelos, ainda requer hardware significativo para treinamento e inferência.

---

## 🚀 Como Usar o Alpaca

### 1. **Instalação**

Certifique-se de ter o Python instalado e clone o repositório oficial:

```bash
git clone https://github.com/tatsu-lab/stanford_alpaca.git
cd stanford_alpaca
pip install -r requirements.txt
```
> Se ocorrer erro ao usar pip, tente pip3

### 2. **Carregar o Modelo**

Utilize a biblioteca `transformers` para carregar o modelo:

```python
from transformers import AutoTokenizer, AutoModelForCausalLM

tokenizer = AutoTokenizer.from_pretrained("WeOpenML/Alpaca-7B-v1")
model = AutoModelForCausalLM.from_pretrained("WeOpenML/Alpaca-7B-v1")
```

### 3. **Geração de Texto**

Gere texto com base em um prompt:

```python
input_text = "Explique a teoria da relatividade de forma simples."
inputs = tokenizer(input_text, return_tensors="pt")
outputs = model.generate(**inputs, max_length=200, do_sample=True)
generated_text = tokenizer.decode(outputs[0], skip_special_tokens=True)
print(generated_text)
```

### 4. **Ajuste Fino (Fine-Tuning)**

Tutorial de ajuste de um Modelo Alpaca: https://www.stochasticbard.com/blog/alpaca-model-communicator/

---

## 📜 Fontes

- [Anúncio Oficial do Alpaca](https://crfm.stanford.edu/2023/03/13/alpaca.html)
- [Repositório no GitHub](https://github.com/tatsu-lab/stanford_alpaca)
- [Comparação entre LLaMA e Alpaca](https://medium.com/@saluem/llama-vs-alpaca-ai-similarities-differences-c793f870aefd)
- [AlpacaEval Leaderboard](https://tatsu-lab.github.io/alpaca_eval/)
- [Modelo Alpaca no Hugging Face](https://huggingface.co/WeOpenML/Alpaca-7B-v1)
- [Como treinar uma Alpaca](https://radekosmulski.com/how-do-you-train-an-alpaca/)

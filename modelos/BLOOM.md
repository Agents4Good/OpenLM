# Modelo BLOOM

> **BLOOM (BigScience Large Open-science Open-access Multilingual Language Model)** é um modelo de linguagem natural desenvolvido pela iniciativa BigScience, projetado para ser acessível, transparente e capaz de lidar com múltiplos idiomas. Ele foi treinado em colaboração com pesquisadores de todo o mundo e apresentado como um marco em ciência aberta e colaboração.

---
## 🔍 Características Principais

- **Criador:** BigScience (iniciativa liderada pela Hugging Face)
- **Arquitetura:** Transformer
- **Idiomas Suportados:** 46 idiomas e 13 linguagens de programação
- **Tamanho do Modelo:** 176 bilhões de parâmetros (maior modelo open-access disponível no momento do lançamento)
- **Treinamento:** Realizado em um supercomputador Jean Zay (França), utilizando recursos de HPC (High-Performance Computing)
- **Objetivos de Treinamento:**
  - Geração de texto em múltiplos idiomas.
  - Apoio a diversas tarefas de NLP, como tradução, resumo e classificação.

---
## 🤓 Distribuição das Linguagens Treinadas

![image](https://github.com/user-attachments/assets/8200135a-8e3c-44c5-ab44-e76a10c178f7)

---
## 🏛️ Arquitetura

![image](https://github.com/user-attachments/assets/1f85c0ac-ab1f-49dc-ad8a-1619ad5679cd)

A arquitetura do modelo BLOOM, conforme detalhado no artigo, inclui diversos aspectos:
- A equipe se concentrou em famílias de modelos escaláveis, com suporte em ferramentas e bases de código disponíveis publicamente.
- Experimentos de ablação foram conduzidos em modelos menores para otimizar componentes e hiperparâmetros.
- A generalização zero-shot foi uma métrica chave para avaliar as decisões arquiteturais.
- O BLOOM é baseado na arquitetura Transformer, especificamente em um modelo causal *decoder-only*.
- Essa abordagem foi validada como a mais eficaz para capacidades de generalização zero-shot em comparação com arquiteturas *encoder-decoder* e outros modelos *decoder-only*.

---
## 🧪 Desempenho em Benchmarks

BLOOM foi avaliado em benchmarks diversos, destacando-se em tarefas de NLP multilinguístico e de programação. Embora não alcance a performance de modelos proprietários como GPT-3 em alguns casos, ele é competitivo em cenários de geração e compreensão de texto.

| **Benchmark**         | **Versão Avaliada** | **Tarefa**                    | **Métrica**         | **Resultado** |
|------------------------|---------------------|--------------------------------|---------------------|---------------|
| WMT'14 EN-FR          | BLOOM-176B         | Tradução de Inglês para Francês | BLEU Score          | 40.98%         |
| XNLI                  | BLOOM-176B         | Inferência Multilíngue         | Exatidão Média (%)  | 76.8%          |
| SuperGLUE             | BLOOM-7.1B         | Classificação e Inferência     | Pontuação Média (%) | 65.2%          |
| TYDI QA               | BLOOM-176B         | Perguntas e Respostas Multilíngues | Exatidão (%)    | 58.0%          |
| LAMBADA               | BLOOM-176B         | Completar Palavras             | Exatidão (%)        | 77.5%          |
| MASSIVE               | BLOOM-7.1B         | Compreensão Multilíngue        | Exatidão Média (%)  | 48.1%          |
| WikiText103           | BLOOM-176B         | Modelagem de Linguagem         | Perplexidade        | 18.2%          |
| MLQA                  | BLOOM-176B         | Perguntas Multilíngues         | Exatidão (%)        | 74.1%          |

> Fontes: [Hugging Face](https://huggingface.co/bigscience/bloom), [Arxiv](https://arxiv.org/abs/2211.05100)

---
## 📚 Pesquisas Relevantes

- [Artigo BLOOM](https://arxiv.org/abs/2211.05100)
- [Papers with Code - BLOOM](https://paperswithcode.com/method/bloom)
- [Artigo Medium](https://medium.com/dair-ai/papers-explained-52-bloom-9654c56cd2)

---
## 📥 Versões

| Versão            | Parâmetros     | Idiomas | Observações                                      |
|-------------------|----------------|---------|-------------------------------------------------|
| **BLOOM 176B**    | 176 bilhões    | 46      | Modelo completo, ideal para grandes tarefas.    |
| **BLOOM 7.1B**    | 7,1 bilhões    | 46      | Variante menor, útil para experimentação.       |
| **BLOOM 560M**    | 560 milhões    | 46      | Variante compacta para aplicações leves.        |

---
## 💻 Requisitos Recomendados

| Versão            | Memória GPU        | Processador                           | Observações                                    |
|-------------------|--------------------|---------------------------------------|-----------------------------------------------|
| **BLOOM 176B**    | 8 GPUs (80GB HBM)  | CPUs com suporte para paralelismo     | Necessário hardware robusto para execução.    |
| **BLOOM 7.1B**    | 2 GPUs (16GB VRAM) | CPU padrão com 4+ núcleos             | Adequado para tarefas médias de NLP.          |
| **BLOOM 560M**    | 1 GPU (8GB VRAM)   | CPU padrão com 2+ núcleos             | Ideal para testes rápidos e aplicações leves. |

---
## ✅ Prós
1. **Acessibilidade:** Primeiro modelo com 176B de parâmetros totalmente open-access.
2. **Multilinguismo Real:** Treinado para gerar texto em uma ampla gama de idiomas, incluindo línguas sub-representadas.
3. **Ciência Aberta:** Foco em transparência, com documentação detalhada e permissões de uso explícitas.

---
## ❌ Contras
1. **Exigências Computacionais Altas:** A versão completa requer recursos significativos, como várias GPUs de alta performance.
2. **Performance em Comparação com Modelos Proprietários:** Embora seja competitivo, BLOOM fica atrás de modelos fechados como GPT-3 em tarefas específicas.
3. **Custos de Treinamento:** Apesar de práticas sustentáveis, o custo computacional para treinar o modelo foi alto.

---
## 🚀 Como Usar o BLOOM

### 1. **Instalação**
Certifique-se de ter o Python instalado e instale a biblioteca `transformers`:
```bash
!pip install transformers -q
```

### 2. **Tokenização**
```python
model = AutoModelForCausalLM.from_pretrained(model_ID, use_cache=True) 
tokenizer = AutoTokenizer.from_pretrained(model_ID)
set_seed(2024)

story_title = 'An Unexpected Journey Through Time' 
prompt = f'This is a creative story about {story_title}.\n'

input_ids = tokenizer(prompt, return_tensors="pt").to(0)

sample = model.generate(**input_ids, 
                        max_length=200, top_k=1, 
                        temperature=0, repetition_penalty=2.0)

generated_story = tokenizer.decode(sample[0], skip_special_tokens=True)

import textwrap  
wrapper = textwrap.TextWrapper(width=80)

formated_story = wrapper.fill(text=generated_story)
print(formated_story)
```

---
## 📜 Fontes

- [Hugging Face: BLOOM](https://huggingface.co/bigscience/bloom)
- [Blog BigScience](https://bigscience.huggingface.co/blog/bloom)
- [Wikipedia: BLOOM](https://en.wikipedia.org/wiki/BLOOM_(language_model))
- [Exploring BLOOM - DataCamp](https://www.datacamp.com/blog/exploring-bloom-guide-to-multilingual-llm)
- [Artigo Acadêmico no Arxiv](https://arxiv.org/abs/2211.05100)
- [Artigo no Medium: Cobus Greyling](https://cobusgreyling.medium.com/bloom-bigscience-large-open-science-open-access-multilingual-language-model-b45825aa119e)
- [AMD Infinity Hub](https://www.amd.com/pt/developer/resources/infinity-hub/bloom-176b.html)
- [Admantium Blog](https://admantium.com/blog/llm04_gen2_gen3_overview_part2/)

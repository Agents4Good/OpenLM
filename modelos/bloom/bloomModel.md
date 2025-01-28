<div align="center">
  <a href="https://huggingface.co/bigscience/bloom" target="_blank">
    <img alt="Hugging Face" src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-BLOOM%20Model-ffc107?color=ffc107&logoColor=white" />
  </a>
</div>

<p align="center">
  <a href="https://arxiv.org/abs/2211.05100"><b>📜 Paper - BLOOM</b></a>
</p>

---
## 1. Visão Geral

**BLOOM** (*BigScience Large Open-science Open-access Multilingual Language Model*) é um modelo de linguagem desenvolvido pela iniciativa colaborativa BigScience.

Destaca-se por seu suporte a **46 idiomas humanos** e **13 linguagens de programação**, oferecendo flexibilidade para tarefas como 
**tradução, geração de texto, e sumarização**.

Seu treinamento foi conduzido de forma aberta, documentada e colaborativa, reforçando a filosofia de ciência aberta.

---
## 2. Características Principais

1. **Multilinguismo Abrangente:** Capacidade de processar línguas amplamente faladas e de baixa representação.
2. **Modelos Escaláveis:** Disponível em cinco tamanhos diferentes, de 560 milhões a 176 bilhões de parâmetros, permitindo uso adaptado à infraestrutura computacional.
3. **Ciência Aberta:** Treinamento transparente e detalhado, documentado pela comunidade global BigScience.
4. **Infraestrutura Avançada:** Treinado no supercomputador **Jean Zay**, localizado na França, utilizando **384 GPUs NVIDIA A100**.

---
## 3. Arquitetura

- **Base:** Arquitetura Transformer *Decoder-Only*, similar ao GPT-3, mas ajustada para multilinguismo.
- **Tamanhos Disponíveis:** Variam de **560M** a **176B** parâmetros, atendendo tanto casos de uso leve quanto de escala massiva.
- **Tokenização:** Utiliza **SentencePiece** com **Byte-Pair Encoding (BPE)** para maior compatibilidade multilinguística.
- **Eficiência:** Customizações foram implementadas para otimizar a memória e lidar com a diversidade de dados linguísticos.

---
## 4. Aplicações

O BLOOM é projetado para uma ampla gama de tarefas de NLP, incluindo:

- **Geração de texto criativo:** Criação de histórias, artigos, ou respostas interativas.
- **Tradução Multilíngue:** Tradução automática entre os 46 idiomas suportados.
- **Resumo de textos:** Condensação de informações em textos mais curtos e compreensíveis.
- **Classificação de Sentimentos:** Análise e categorização de sentimentos em textos.

---
## 5. Benchmarks e Resultados

De acordo com os benchmarks relatados no [artigo do DAIR.AI](https://medium.com/dair-ai/papers-explained-52-bloom-9654c56cd2):

- **Desempenho Geral**: BLOOM alcança desempenho comparável a modelos proprietários em tarefas multilinguísticas.<br>
- **Modelos Menores**: Mesmo versões reduzidas, como BLOOM-560M, superam modelos da mesma escala em tarefas de tradução e classificação.<br>
- **Multilinguismo**: BLOOM é particularmente eficiente em idiomas de baixa representação, superando modelos proprietários que focam em idiomas majoritários.<br>

---
## 6. Modelos Disponíveis no Hugging Face

|       Modelo        |                            Link                             |
|:-------------------:|------------------------------------------------------------|
| **BLOOM 560M**      | [🤗 Hugging Face](https://huggingface.co/bigscience/bloom-560m) |
| **BLOOM 1B**        | [🤗 Hugging Face](https://huggingface.co/bigscience/bloom-1b1)   |
| **BLOOM 3B**        | [🤗 Hugging Face](https://huggingface.co/bigscience/bloom-3b)    |
| **BLOOM 7B**        | [🤗 Hugging Face](https://huggingface.co/bigscience/bloom-7b1)   |
| **BLOOM 176B**      | [🤗 Hugging Face](https://huggingface.co/bigscience/bloom)       |

---
## 7. Fontes

- [Artigo no arXiv - BLOOM](https://arxiv.org/abs/2211.05100)
- [Blog do BigScience](https://bigscience.huggingface.co/blog/bloom)
- [Página no Hugging Face](https://huggingface.co/bigscience/bloom)
- [Guia do DataCamp](https://www.datacamp.com/blog/exploring-bloom-guide-to-multilingual-llm)
- [Documentação no Hugging Face](https://huggingface.co/docs/transformers/en/model_doc/bloom)
- [Explicação no Medium pela Dair.AI](https://medium.com/dair-ai/papers-explained-52-bloom-9654c56cd2)

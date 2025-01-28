<div align="center">
  <a href="https://huggingface.co/docs/transformers/en/model_doc/bert" target="_blank">
    <img alt="Hugging Face" src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-BERT-ff5722?color=ff5722&logoColor=white" />
  </a>
</div>

<p align="center">
  <a href="https://arxiv.org/abs/1810.04805"><b>📜 Paper - BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding</b></a>
</p>

---
## 1. Introdução

BERT (Bidirectional Encoder Representations from Transformers) é um modelo de linguagem desenvolvido pela equipe de pesquisa do Google AI, introduzido em 2018.

Ele foi projetado para capturar o contexto bidirecional de uma frase, fornecendo melhorias significativas na compreensão de textos e na resolução de tarefas
como classificação de sentenças, reconhecimento de entidades nomeadas (NER) e respostas a perguntas.

---
## 2. Arquitetura do Modelo

A arquitetura do BERT é baseada no Transformer, especificamente em sua parte Encoder.
O Transformer utiliza mecanismos de atenção para modelar dependências entre palavras em uma frase, independentemente da distância entre elas.

- **Modelos Disponíveis**:
  - **BERT-base**: 12 camadas (layers), 768 dimensões escondidas (hidden size), 110M parâmetros.
  - **BERT-large**: 24 camadas, 1024 dimensões escondidas, 340M parâmetros.

- **Bidirecionalidade**: Ao contrário de modelos unidirecionais como GPT, o BERT analisa as palavras à esquerda e à direita simultaneamente, o que melhora a compreensão do contexto.

---
## 3. Treinamento

O treinamento do BERT consiste em duas fases principais:

1. **Pré-treinamento**:
   - **Tarefa de Modelagem de Palavras Mascaradas (MLM)**:
     - 15% das palavras no texto são mascaradas aleatoriamente.
     - O objetivo do modelo é prever essas palavras com base no contexto bidirecional.
   - **Tarefa de Predição da Próxima Sentença (NSP)**:
     - Dada uma frase A, o modelo prediz se a frase B é a continuação lógica.

2. **Ajuste Fino (Fine-tuning):**
   - O BERT é adaptado a tarefas específicas adicionando camadas adicionais e re-treinando em pequenos conjuntos de dados.

---
## 4. Benchmarks

> Fonte: [Artigo Medium](https://medium.com/@kefactor/benchmarking-bert-based-models-for-text-classification-7182db4df89a)

Benchmark final para os 5 modelos BERT mais populares:

| **Métricas de Avaliação**        | **RASA Classifier** | **mBERT Classifier** | **DistilBERT Classifier** | **XLM-RoBERTa Classifier** | **LaBSE Classifier** |
|----------------------------------|---------------------|-----------------------|---------------------------|----------------------------|-----------------------|
| **F1-score**                     | 0.7439             | 0.8882               | 0.8865                   | 0.8841                    | 0.8936               |
| **Precisão**                     | 0.7274             | 0.8659               | 0.8966                   | 0.9121                    | 0.8761               |
| **Revocação**                    | 0.7861             | 0.9279               | 0.8927                   | 0.8788                    | 0.9181               |
| **Duração de Treinamento (1 época)** | 15 segundos        | 121 segundos         | 61 segundos              | 67 segundos               | 143 segundos         |
| **Duração de Treinamento (parada antecipada)** | 303 segundos        | 968 segundos         | 488 segundos             | 871 segundos            | 1859 segundos        |
| **RAM no pico**                  | 3250.1758 MB       | 1002.4883 MB         | 714.8125 MB              | 1982.4102 MB              | 3078.3047 MB         |
| **RAM média**                    | 1818.4034 MB       | 436.3266 MB          | 542.4159 MB              | 526.4321 MB               | 171.4741 MB          |
| **RAM da GPU**                   | -                  | 4631 MB              | 2475 MB                  | 6763 MB                   | 11179 MB             |
| **Latência de um exemplo**       | 0.012 segundos     | 0.061 segundos       | 0.034 segundos           | 0.059 segundos            | 0.049 segundos       |
| **RAM no pico (inferência)**     | 748.6952 MB        | 2444.5395 MB         | 1864.9184 MB             | 2989.8129 MB              | 3874.6293 MB         |
| **RAM média (inferência)**       | 746.0741 MB        | 2441.6461 MB         | 1861.3647 MB             | 2986.7031 MB              | 3871.1193 MB         |
| **Uso de CPU**                   | 5427 chamadas      | 9472 chamadas        | 5030 chamadas            | 8799 chamadas             | 9311 chamadas        |

---
## 5. Comparação entre Diferentes Modelos BERT

1. **BERT Base (Bidirectional Encoder Representations from Transformers)**  
   - Modelo original proposto pelo Google.
   - **Vantagens**: Arquitetura bidirecional que captura o contexto completo de palavras, ideal para tarefas de NLP como classificação de texto, perguntas e respostas, e NER.
   - **Desvantagens**: Exige altos recursos computacionais e tempos de treinamento mais longos.

2. **DistilBERT**  
   - Uma versão reduzida e otimizada do BERT, com 40% menos parâmetros e aproximadamente 60% mais rápida.
   - **Vantagens**: Alta eficiência em termos de uso de memória e velocidade, mantendo cerca de 97% do desempenho do BERT original.
   - **Desvantagens**: Menor precisão em tarefas altamente complexas em comparação ao modelo completo.

3. **RoBERTa (Robustly Optimized BERT)**  
   - Uma variante otimizada do BERT com melhorias no pré-treinamento, como maior número de dados, maior tamanho de batch e remoção da tarefa de predição de próxima frase.
   - **Vantagens**: Melhor desempenho em benchmarks de NLP devido a um treinamento mais robusto.
   - **Desvantagens**: Maior consumo de recursos durante o treinamento e inferência.

4. **XLM-RoBERTa (XLM-R)**  
   - Uma versão multilingue do RoBERTa, treinada em mais de 100 idiomas.
   - **Vantagens**: Excelência em tarefas multilingues, como tradução e classificação de texto em diferentes idiomas.
   - **Desvantagens**: Requer mais memória e poder computacional para operar.

5. **mBERT (Multilingual BERT)**  
   - Modelo multilingue original baseado no BERT, treinado em 104 idiomas.
   - **Vantagens**: Funciona bem para aplicações que exigem suporte a vários idiomas.
   - **Desvantagens**: O desempenho em tarefas monolíngues é inferior ao de modelos especializados como RoBERTa.

6. **LaBSE (Language-Agnostic BERT Sentence Embedding)**  
   - Focado em embeddings de sentenças com suporte multilingue.
   - **Vantagens**: Excelente em tarefas que envolvem a similaridade semântica entre sentenças em diferentes idiomas.
   - **Desvantagens**: Desempenho limitado para tarefas de classificação complexas.

7. **TinyBERT**  
   - Um modelo ainda menor que o DistilBERT, projetado para dispositivos de baixa capacidade.
   - **Vantagens**: Extremamente eficiente em termos de uso de memória e processamento.
   - **Desvantagens**: Sacrifica parte da precisão em tarefas mais sofisticadas.

---
## 6. Downloads

O modelo BERT está disponível no Hugging Face:

|         Model         |                                Download                                    |                  
|:---------------------:|--------------------------------------------------------------------------:|
| BERT-base             | [🤗 HuggingFace](https://huggingface.co/bert-base-uncased)                |
| BERT-large            | [🤗 HuggingFace](https://huggingface.co/bert-large-uncased)               |

---
## 7. Requisitos de Sistema

| Versão do Modelo | VRAM (GPU)      | RAM (CPU)     | Armazenamento |
|------------------|-----------------|---------------|---------------|
| BERT-base       | 8GB+            | 16GB+         | 500MB         |
| BERT-large      | 16GB+           | 32GB+         | 1GB           |

---
## 8. Fontes

- [Artigo Original](https://arxiv.org/abs/1810.04805)
- [Documentação Hugging Face](https://huggingface.co/docs/transformers/en/model_doc/bert)
- [Deep Learning Book - Modelo BERT](https://www.deeplearningbook.com.br/modelo-bert-para-processamento-de-linguagem-natural/)
- [Medium - Skillcate](https://medium.com/@skillcate/bert-for-dummies-state-of-the-art-model-from-google-42639953e769)


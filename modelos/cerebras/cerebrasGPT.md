<div align="center">
  <a href="https://huggingface.co/collections/cerebras/cerebras-gpt-66c623297a2370b8e670e0a1" target="_blank">
    <img alt="Hugging Face" src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Cerebras%20GPT-ffc107?color=ffc107&logoColor=white" />
  </a>
</div>

<p align="center">
  <a href="https://arxiv.org/abs/2304.03208"><b>📜 Paper - Cerebras GPT</b></a>
</p>

---
## 1. Introdução

Cerebras Systems, conhecida por seus avanços em hardware para IA, desenvolveu o **Cerebras GPT**, uma família de modelos de linguagem aberta, projetada com foco em eficiência computacional. O artigo intitulado **"Cerebras-GPT: A Family of Open, Compute-Efficient Large Language Models"** detalha os fundamentos e a eficiência desses modelos.

Os modelos Cerebras GPT foram treinados usando arquiteturas de alto desempenho e são otimizados para execução eficiente em sistemas modernos.

**Destaques**:
- Primeiro modelo open-source projetado para eficiência de hardware.
- Focado em reduzir o custo de treinamento e inferência sem comprometer a qualidade.
- Publicado sob a Licença Apache 2.0, permitindo personalização e integração flexível.

---
## 2. Arquitetura do Modelo

Cerebras GPT não é um modelo único, mas sim uma família de modelos projetados para diferentes requisitos computacionais e aplicações.

- **Cerebras GPT-13B**: Equilíbrio entre desempenho e eficiência computacional.
- **Cerebras GPT-6.7B**: Otimizado para tarefas gerais com menor custo.
- **Cerebras GPT-2.7B**: Destinado a dispositivos de borda com recursos limitados.
- **Cerebras GPT-111M**: Versão compacta para aplicações leves e integração embarcada.

Os modelos seguem a arquitetura Transformer, com otimizações específicas para eficiência computacional, como:
- Redução de parâmetros redundantes.
- Melhor balanceamento entre capacidade de inferência e consumo de energia.

---
## 3. Treinamento

### 1. **Abordagem de Treinamento**:
Os modelos Cerebras GPT foram treinados com foco na eficiência, utilizando o sistema **Cerebras Wafer-Scale Engine (WSE)**. Este hardware especializado permite:
- Redução do tempo de treinamento.
- Maior escalabilidade.

### 2. **Dataset**:
Os modelos foram treinados em um corpus massivo de texto, otimizados para cobrir uma ampla gama de tarefas de linguagem natural, incluindo:
- Compreensão de linguagem.
- Tradução.
- Geração de texto.

### 3. **Técnicas de Otimização**:
Os modelos utilizam técnicas modernas de regularização e inicialização para:
- Reduzir o risco de overfitting.
- Melhorar a generalização em tarefas não vistas durante o treinamento.

---
## 4. Downloads

> "GPT" refere-se aos modelos generativos baseados na arquitetura Transformer.<br>
> "Base" indica modelos genéricos para tarefas gerais.<br>
> "Small" refere-se a versões compactas otimizadas para aplicações leves.

### HuggingFace
|        Model        |                            Download                             |
|:-------------------:|----------------------------------------------------------------:|
| Cerebras GPT-13B    | [🤗 HuggingFace](https://huggingface.co/cerebras/cerebras-gpt-13b)    |
| Cerebras GPT-6.7B   | [🤗 HuggingFace](https://huggingface.co/cerebras/cerebras-gpt-6.7b)   |
| Cerebras GPT-2.7B   | [🤗 HuggingFace](https://huggingface.co/cerebras/cerebras-gpt-2.7b)   |
| Cerebras GPT-111M   | [🤗 HuggingFace](https://huggingface.co/cerebras/cerebras-gpt-111m)   |

---
## 5. Benchmarks

Resultados de benchmarks completos estão disponíveis na [documentação oficial](https://cerebras.ai/blog/cerebras-gpt-a-family-of-open-compute-efficient-large-language-models/).

**Métricas principais**:
- **Perplexidade**: Menor do que modelos de tamanho similar.
- **Tempo de Inferência**: Reduzido em até 30% devido à arquitetura otimizadora.

---
## 6. Comparação com Outros Modelos

**Cerebras GPT vs. DeepSeek-R1**

| Métrica              | Cerebras GPT                      | DeepSeek-R1                           |
|-----------------------|-----------------------------------|---------------------------------------|
| Licença              | Apache 2.0                        | MIT                                   |
| Abordagem de Treinamento | Uso de WSE para eficiência computacional | Aprendizado por Reforço Extensivo      |
| Foco Principal        | Eficiência e custo               | Raciocínio Lógico e Resolução de Problemas |

---
## 7. Requisitos de Sistema

| Versão do Modelo | VRAM (GPU)      | RAM (CPU)     | Armazenamento |
|-------------------|-----------------|---------------|---------------|
| Cerebras GPT-111M            | 2GB+           | 4GB+          | 2GB           |
| Cerebras GPT-2.7B            | 8GB+           | 16GB+         | 8GB           |
| Cerebras GPT-6.7B            | 16GB+          | 32GB+         | 25GB          |
| Cerebras GPT-13B             | 32GB+          | 64GB+         | 50GB          |

---
## 8. Fontes

- [Artigo Cerebras GPT](https://arxiv.org/abs/2304.03208)
- [Blog Oficial Cerebras](https://cerebras.ai/blog/cerebras-gpt-a-family-of-open-compute-efficient-large-language-models/)
- [HuggingFace - Cerebras GPT](https://huggingface.co/collections/cerebras/cerebras-gpt-66c623297a2370b8e670e0a1)
- [Site Oficial Cerebras](https://cerebras.ai/)


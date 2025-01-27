<div align="center">
  <a href="https://huggingface.co/ibm-granite" target="_blank">
    <img alt="Hugging Face" src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-IBM%20Granite-ffc107?color=ffc107&logoColor=white" />
  </a>
</div>

<p align="center">
  <a href="https://arxiv.org/abs/2405.04324"><b>📜 Paper - Granite Models</b></a>
</p>

---
## 1. Introdução

Os modelos Granite representam uma família de modelos desenvolvidos pela **IBM**. Lançados em 2024, os Granite são otimizados para desempenho, eficiência e sustentabilidade em aplicações corporativas.

Conforme descrito no artigo “**Granite Models: A Sustainable Foundation for Enterprise AI**” ([arXiv:2405.04324](https://arxiv.org/abs/2405.04324)),
os modelos utilizam técnicas de treinamento avançadas para maximizar eficiência computacional.

Os Granite estão disponíveis em diferentes versões otimizadas para capacidade computacional e aplicações empresariais específicas:

| Tamanho do Modelo | Descrição                                                                 |
|-------------------|---------------------------------------------------------------------------|
| Granite **3B**          | Versão leve, para dispositivos de borda e aplicações locais.                     |
| Granite **8B**            | Equilíbrio entre desempenho e custo computacional.                          |
| Granite **20B**           | Otimizado para tarefas empresariais complexas.                                 |
| Granite **34B**           | Para cenários de alta escalabilidade e integração empresarial.                   |

**Atenção!**  
> Granite não é apenas um modelo específico, mas uma família de modelos, cada um voltado para aplicações empresariais distintas.

---
## 2. Arquitetura do Modelo

- **Granite Code Base**: modelos de fundação básicos para tarefas relacionadas a código.  
- **Granite Code Instruct**: modelos ajustados para seguir instruções, refinados com uma combinação de commits do Git emparelhados com instruções humanas e
conjuntos de dados de instruções de código gerados sinteticamente de código aberto.

| Modelo   | Tamanho do Lote | Comprimento do Contexto | Tamanho Oculto | Tamanho Oculto FFN | Cabeças de Atenção | Cabeças Chave-Valor | Camadas | Normalização | Ativação | Tamanho do Vocabulário |
|----------|------------------|-------------------------|----------------|--------------------|--------------------|----------------------|---------|--------------|----------|------------------------|
| 3B       | 2048             | 2048                   | 2560           | 10240              | 32                 | 32 (MHA)            | 32      | RMSNorm      | swiglu   | 49152                  |
| 8B       | 1024             | 4096                   | 4096           | 14336              | 32                 | 8 (GQA)             | 36      | RMSNorm      | swiglu   | 49152                  |
| 20B      | 576              | 8192                   | 6144           | 24576              | 48                 | 1 (MQA)             | 52      | LayerNorm    | gelu     | 49152                  |
| 34B      | 532              | 8192                   | 6144           | 24576              | 48                 | 1 (MQA)             | 88      | LayerNorm    | gelu     | 49152                  |

---
## 3. Dados

O treinamento dos modelos Granite é projetado para balancear custo, desempenho e sustentabilidade:

1. **Rastreamento e Filtragem de Dados**
   - Os dados de pré-treinamento de código foram obtidos a partir de uma combinação de conjuntos de dados disponíveis publicamente.
   - Os dados brutos foram filtrados para reter uma lista de 116 linguagens de programação, selecionadas dentre mais de 300 linguagens.

2. **Conjuntos de Dados de Linguagem Natural**
   - **Documentos da Web**: StackExchange, CommonCrawl.  
   - **Texto Matemático da Web**: OpenWebMath, StackMathQA.  
   - **Texto Acadêmico**: ArXiv, Wikipedia.  
   - **Conjuntos de Dados para Ajuste por Instrução**: FLAN, HelpSteer.  

3. **Técnicas de Sustentabilidade**:
   - Uso de datacenters energeticamente eficientes.
   - Deduplicação agressiva para otimizar os dados de treinamento.

---
## 4. Treinamento

Os modelos Granite Code são treinados com 3,5 a 4,5 trilhões de tokens de dados de código.

**Fase 1 (treinamento somente com código):**
- Modelos de 3B e 8B são treinados com 4 trilhões de tokens de dados de código, abrangendo 116 idiomas.
- O modelo de 20B parâmetros é treinado com 3 trilhões de tokens de código.
- O modelo de 34B é treinado com 1,4 trilhões de tokens após a ampliação da profundidade, realizada no ponto de verificação de 1,6 trilhões do modelo de 20B.

**Fase 2 (treinamento com código + linguagem):**
- Dados adicionais de alta qualidade e publicamente disponíveis de diversos domínios, incluindo documentos técnicos, matemáticos e da web, são incluídos para melhorar ainda mais o desempenho do modelo em habilidades de raciocínio e resolução de problemas, essenciais para a geração de código.
- Todos os modelos são treinados com 500B tokens (80% de dados de código e 20% de dados de linguagem).

---
## 5. Downloads

| Modelo               | Caminho Hugging Face                                         |
|----------------------|-------------------------------------------------------------|
| Granite-3B-Instruct  | [🤗 HuggingFace](https://huggingface.co/ibm-granite/granite-3.1-3b-a800m-instruct) |
| Granite-3B-Base      | [🤗 HuggingFace](https://huggingface.co/ibm-granite/granite-3.1-3b-a800m-base) |
| Granite-8B-Instruct  | [🤗 HuggingFace](https://huggingface.co/ibm-granite/granite-3.1-8b-instruct) |
| Granite-8B-Base      | [🤗 HuggingFace](http://huggingface.co/ibm-granite/granite-3.1-8b-base)

Veja outros modelos Granite: https://huggingface.co/ibm-granite

---
## 6. Benchmarks

Para resultados detalhados, consulte: [IBM Granite Code Model GitHub](https://github.com/ibm-granite/granite-code-models/blob/main/README.md#evaluation-results).

---
## 7. Requisitos de Sistema

| Versão do Modelo | VRAM (GPU)      | RAM (CPU)     | Armazenamento |
|------------------|-----------------|---------------|---------------|
| Granite **3B**            | 4GB+           | 8GB+          | 5GB           |
| Granite **8B**              | 12GB+          | 16GB+         | 10GB          |
| Granite **20B**             | 24GB+          | 64GB+         | 30GB          |
| Granite **34B**             | 80GB+          | 256GB+        | 120GB         |

---
## 8. Fontes

- [Artigo Granite Models](https://arxiv.org/abs/2405.04324)
- [Artigo Medium](https://ritvik19.medium.com/paper-explained-144-granite-code-models-e1a92678739b)
- [IBM Granite Oficial](https://www.ibm.com/granite)
- [GitHub Granite](https://github.com/ibm-granite/granite-code-models)
- [Blog Red Hat - Granite Models](https://www.redhat.com/en/blog/ibms-granite-foundation-model-detailed-look-its-training-data)
- [Wikipedia - IBM Granite](https://en.wikipedia.org/wiki/IBM_Granite)
- [Documentação Oficial](https://www.ibm.com/granite/docs/)

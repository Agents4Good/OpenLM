<div align="center">
  <a href="https://huggingface.co/blog/falcon2-11b" target="_blank">
    <img alt="Hugging Face" src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Falcon2%20LLM-ffc107?color=ffc107&logoColor=white" />
  </a>
</div>

<p align="center">
  <a href="https://arxiv.org/html/2407.14885v1"><b>📝 Paper - Falcon LLM</b></a>
</p>

---
## 1. Introdução

O **Falcon 2** é uma nova geração de modelos de linguagem de código aberto, oferecendo capacidades multilíngues e multimodais. É o único modelo de IA com capacidade de **visão-para-linguagem (VLM)**, permitindo a interpretação de imagens e sua conversão para texto de maneira eficiente.

O **Falcon 2 11B** superou o **Llama 3 8B** da Meta e apresenta desempenho equivalente ao **Google Gemma 7B**, conforme verificado independentemente pelo **Hugging Face Leaderboard**. O próximo passo da equipe é a implementação de um **Mixture of Experts (MoE)** para ampliar ainda mais as capacidades do Falcon 2.

---
## 2. Arquitetura do Modelo

A arquitetura do **Falcon 2** foi projetada para ser altamente eficiente e escalável, com avanços significativos em comparação à sua versão anterior.

Principais inovações:
- **Multimodalidade**: Suporte nativo para tarefas que combinam visão e linguagem.
- **Eficiência Computacional**: Melhor uso de recursos de hardware e inferência mais rápida.
- **Escalabilidade**: Projetado para ser treinado e executado em larga escala com eficiência.
- **Treinamento Otimizado**: Uso de dados diversificados para melhorar a capacidade de generalização do modelo.

O Falcon 2 será aprimorado no futuro com a adição do **Mixture of Experts (MoE)**, que permitirá que diferentes partes do modelo sejam ativadas para tarefas específicas, melhorando a eficiência e o desempenho.

---
## 3. Modelos Disponíveis

| Tamanho do Modelo | Descrição |
|-------------------|-------------------------------------------------|
| Falcon 2 **11B**         | Modelo base para tarefas de linguagem natural. |
| Falcon 2 **11B VLM**     | Versão multimodal com suporte a visão-para-linguagem. |

---
## 4. Treinamento e Dados

O Falcon 2 foi treinado em um conjunto de dados diversificado e extensivo, cobrindo vários idiomas e domínios para garantir melhor desempenho e generalização.

Principais características do treinamento:
- **Baseado em um corpus multimodal**: Incluir imagens e textos melhora a capacidade de raciocínio visual do modelo.
- **Uso de técnicas avançadas de otimização**: Aprimoramento no processo de ajuste fino para tarefas específicas.
- **Redução de viés**: Maior diversidade de dados para tornar o modelo mais equitativo.

---
## 5. Benchmarks

Os testes de desempenho do Falcon 2 mostram superação do Llama 3 8B e desempenho equivalente ao Google Gemma 7B, conforme avaliações independentes do Hugging Face Leaderboard.

- **Melhor desempenho em tarefas de linguagem natural em relação ao Llama 3 8B.**
- **Eficiência competitiva com modelos da Google, como o Gemma 7B.**
- **Resultados promissores em benchmarks multimodais.**

Para mais detalhes, consulte os resultados completos no [Hugging Face Leaderboard](https://huggingface.co/blog/falcon2-11b).

---
## 6. Referências

- [Artigo Falcon 2](https://arxiv.org/html/2407.14885v1)
- [Hugging Face Falcon 2](https://huggingface.co/blog/falcon2-11b)
- [Site Oficial](https://falconllm.tii.ae/falcon-models.html)


<div align="center">
  <a href="https://huggingface.co/tiiuae" target="_blank">
    <img alt="Hugging Face" src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Falcon%20LLM-ffc107?color=ffc107&logoColor=white" />
  </a>
</div>

<p align="center">
  <a href="https://arxiv.org/abs/2311.16867"><b>📝 Paper - Falcon LLM</b></a>
</p>

---
## 1. Introdução

Falcon LLM é uma família de modelos desenvolvida pelo **Technology Innovation Institute (TII), Abu Dhabi**.

Projetado para ser altamente eficiente, o Falcon supera diversos modelos de sua categoria em benchmarks de NLP,
oferecendo desempenho otimizado para inferência e treinamento.

Seus modelos variam de 7B a 180B parâmetros, sendo amplamente adotados para aplicações de IA generativa e assistentes virtuais.

| Tamanho do Modelo | Descrição |
|-------------------|------------|
| Falcon **7B** | Modelo leve, otimizado para inferência eficiente. |
| Falcon **40B** | Equilíbrio entre eficiência e desempenho. |
| Falcon **180B** | Versão de maior escala, projetada para IA generativa de alto desempenho. |

---
## 2. Arquitetura do Modelo

O Falcon LLM é baseado em uma arquitetura Transformer **decoder-only**, com algumas inovações para otimização de desempenho:

- **Token Merging (FlashAttention)**: Melhoria na eficiência computacional reduzindo latência.
- **Grouped-Query Attention (GQA)**: Melhoria na escalabilidade e inferência otimizada.
- **Parallel Attention Mechanisms**: Permite maior eficiência no processamento de sequências longas.

---
## 3. Treinamento

O treinamento do Falcon LLM foi realizado com um dataset massivo de alta qualidade, priorizando **textos extraídos da Web, artigos científicos e código-fonte**.

- **Fontes de Dados:** The Pile, RefinedWeb, GitHub, arXiv, Books, entre outros.
- **Técnicas de Treinamento:**
  - Uso de **tokenização otimizada** para menor perda de informação.
  - **Fine-tuning** com tarefas específicas, incluindo código e matemática.
  - Aprimoramento baseado em **aprendizado auto-supervisionado**.

---
## 4. Downloads

### HuggingFace
|         Model         |                                Download                                    |                  
|:---------------------:|--------------------------------------------------------------------------: |
| Falcon-7B | [🤖 HuggingFace](https://huggingface.co/tiiuae/falcon-7b) |
| Falcon-40B | [🤖 HuggingFace](https://huggingface.co/tiiuae/falcon-40b) |
| Falcon-180B | [🤖 HuggingFace](https://huggingface.co/tiiuae/falcon-180B) |

---
## 5. Benchmarks

Para detalhes sobre benchmarks, consulte: [Falcon LLM Benchmarks](https://huggingface.co/blog/falcon)

---
## 6. Requisitos de Sistema

| Versão do Modelo | VRAM (GPU) | RAM (CPU) | Armazenamento |
|------------------|-----------|----------|--------------|
| Falcon **7B** | 16GB+ | 32GB+ | 15GB |
| Falcon **40B** | 48GB+ | 128GB+ | 80GB |
| Falcon **180B** | 256GB+ | 512GB+ | 400GB |

---
## 7. Fontes

- [Paper Falcon LLM](https://arxiv.org/abs/2311.16867)
- [Site Oficial](https://falconllm.tii.ae/)
- [HuggingFace Falcon](https://huggingface.co/tiiuae)
- [Guia GeeksforGeeks](https://www.geeksforgeeks.org/falcon-llm-comprehensive-guide/)


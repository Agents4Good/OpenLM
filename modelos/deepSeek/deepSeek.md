<div align="center">
  <img src="https://github.com/Agents4Good/LMGuide/blob/main/imagens/logoDeepSeek.svg" width="60%" alt="DeepSeek LLM" />
</div>

<div align="center">
  <a href="https://huggingface.co/deepseek-ai" target="_blank">
    <img alt="Hugging Face" src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-DeepSeek%20AI-ffc107?color=ffc107&logoColor=white" />
  </a>
</div>

<p align="center">
  <a href="https://arxiv.org/abs/2401.02954"><b>Paper Link</b>👁️</a>
</p>

---
## 1. Introdução

DeepSeek-R1 é o modelo de raciocínio de primeira geração da DeepSeek, com desempenho comparável ao OpenAI-o1. Ele está disponível em várias versões, otimizadas para diferentes capacidades computacionais:

| Tamanho do Modelo | Descrição                                                                 |
|-------------------|---------------------------------------------------------------------------|
| **1.5B**          | Versão leve, otimizada para inferência rápida em dispositivos de borda.    |
| **7B**            | Modelo balanceado, adequado para tarefas gerais de raciocínio.             |
| **8B**            | Maior precisão e melhor compreensão contextual.                           |
| **14B**           | Capacidades aprimoradas de raciocínio e solução de problemas.              |
| **32B**           | Análise lógica mais forte e saídas detalhadas.                            |
| **70B**           | Versão avançada para aplicações de IA de alto nível.                      |
| **671B**          | Modelo Mixture-of-Experts (MoE), ativando 37 bilhões de parâmetros por token para desempenho de raciocínio de última geração. |

---
## 2. Downloads

> "R1" indica que esses modelos são versões distiladas de arquiteturas maiores, como Qwen e Llama, voltadas para um propósito específico.<br>
> O processo de distillação reduz o tamanho e a complexidade do modelo enquanto tenta manter um desempenho próximo ao do modelo maior.<br>
> "LLM" refere-se a modelos maiores e mais gerais.<br>
> "Base" refere-se a modelos para tarefas gerais de NLP.<br>
> "Chat" refere-se a modelos ajustados para tarefas conversacionais.

### Huggingface
|         Model         |                                Download                                    |                  
|:---------------------:|--------------------------------------------------------------------------: |
| DeepSeek-R1-Distill-Qwen-1.5B	| 🤗 [HuggingFace](https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B)   |
| DeepSeek-R1-Distill-Qwen-7B   | 🤗 [HuggingFace](https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Qwen-7B)     |
| DeepSeek-R1-Distill-Llama-8B	| 🤗 [HuggingFace](https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Llama-8B)    |
| DeepSeek-R1-Distill-Llama-70B	| 🤗 [HuggingFace](https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Llama-70B)   |
| DeepSeek LLM 7B Base  | 🤗 [HuggingFace](https://huggingface.co/deepseek-ai/deepseek-llm-7b-base)  |
| DeepSeek LLM 7B Chat  | 🤗 [HuggingFace](https://huggingface.co/deepseek-ai/deepseek-llm-7b-chat)  |
| DeepSeek LLM 67B Base | 🤗 [HuggingFace](https://huggingface.co/deepseek-ai/deepseek-llm-67b-base) |
| DeepSeek LLM 67B Chat | 🤗 [HuggingFace](https://huggingface.co/deepseek-ai/deepseek-llm-67b-chat) |

---
## 3. Benchmarks

> Consulte aqui: https://github.com/deepseek-ai/DeepSeek-LLM/blob/main/README.md#3-evaluation-results

---
## 4. Comparação com outros Modelos

Ao contrário dos modelos fechados, o DeepSeek-R1 oferece visibilidade do seu processo de raciocínio passo a passo, permitindo aos usuários rastrear, verificar e refinar as conclusões geradas pela IA.

Além disso, por ser open-source sob a licença MIT, o DeepSeek-R1 oferece diversas vantagens:
- **Personalização sem Restrições**: Desenvolvedores podem ajustar e modificar o modelo para casos de uso específicos, sem limitações de licenciamento.
- **Melhorias pela Comunidade**: Pesquisadores e especialistas podem contribuir com aprimoramentos.
- **Eficiência de Custos**: É uma alternativa ideal para empresas que buscam integrar IA sem custos recorrentes.

---
## 5. Requisitos de Sistema

| Versão do Modelo | VRAM (GPU)      | RAM (CPU)     | Armazenamento |
|------------------|-----------------|---------------|---------------|
| 1.5B            | 4GB+           | 8GB+          | 5GB           |
| 7B              | 12GB+          | 16GB+         | 10GB          |
| 8B              | 16GB+          | 32GB+         | 15GB          |
| 14B             | 24GB+          | 64GB+         | 30GB          |
| 32B             | 48GB+          | 128GB+        | 60GB          |
| 70B             | 80GB+          | 256GB+        | 120GB         |
| 671B (MoE)      | 4x A100 GPUs (320GB VRAM) | 512GB+ | 500GB+       |

---
## 6. Executando o DeepSeek-R1 Localmente com Ollama

O Ollama facilita a execução do DeepSeek-R1 localmente em seu sistema, sem a necessidade de APIs baseadas na nuvem. Os requisitos do sistema variam dependendo do tamanho do modelo escolhido.

#### Instalar o Ollama
Se ainda não tiver o Ollama instalado, use o seguinte comando para configurá-lo em sua máquina:

```bash
curl -fsSL https://ollama.com/install.sh | sh
```

#### Baixar e Configurar o DeepSeek-R1
Após instalar o Ollama, é possível baixar o modelo DeepSeek-R1:

```bash
ollama pull deepseek-r1:7b
```

> A versão "7b" refere-se ao modelo de 7 bilhões de parâmetros. Substitua por "1.5b", "8b", "14b", "32b", "70b" ou até mesmo "671b".

#### Executar o DeepSeek-R1 Localmente
Para iniciar uma sessão interativa com o modelo, execute:

```bash
ollama run deepseek-r1:7b
```

Este comando permite enviar prompts e receber respostas em tempo real.

<div align="center">
  <img src="https://github.com/Agents4Good/LMGuide/blob/main/imagens/logoDeepSeek.svg" width="60%" alt="DeepSeek LLM" />
</div>

<div align="center">
  <a href="https://huggingface.co/deepseek-ai" target="_blank">
    <img alt="Hugging Face" src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-DeepSeek%20AI-ffc107?color=ffc107&logoColor=white" />
  </a>
</div>

<p align="center">
  <a href="https://arxiv.org/abs/2401.02954"><b>Paper - DeepSeek LLM</b></a><br>
  <a href="https://arxiv.org/abs/2501.12948"><b>Paper - DeepSeek R1</b></a>
</p>

---
## 1. Introdução

DeepSeek introduziu uma nova abordagem para melhorar as capacidades de raciocínio de modelos de linguagem por meio de aprendizado por reforço (RL), conforme detalhado em seu recente artigo sobre o DeepSeek-R1.

Esta pesquisa representa um avanço significativo na forma como podemos aprimorar a capacidade de modelos para resolver problemas complexos usando apenas aprendizado por reforço, sem depender fortemente de ajuste fino supervisionado.

DeepSeek-R1 é o modelo de raciocínio de primeira geração da DeepSeek, com desempenho comparável ao OpenAI-o1. Ele está disponível em várias versões, otimizadas para diferentes capacidades computacionais:

| Tamanho do Modelo | Descrição                                                                 |
|-------------------|---------------------------------------------------------------------------|
| DeepSeek-R1 **1.5B**          | Versão leve, otimizada para inferência rápida em dispositivos de borda.    |
| DeepSeek-R1 **7B**            | Modelo balanceado, adequado para tarefas gerais de raciocínio.             |
| DeepSeek-R1 **8B**            | Maior precisão e melhor compreensão contextual.                           |
| DeepSeek-R1 **14B**           | Capacidades aprimoradas de raciocínio e solução de problemas.              |
| DeepSeek-R1 **32B**           | Análise lógica mais forte e saídas detalhadas.                            |
| DeepSeek-R1 **70B**           | Versão avançada para aplicações de IA de alto nível.                      |

**Atenção!** 
> Não confunda DeepSeek-LLM com DeepSeek-R1.

DeepSeek-LLM é um conceito geral, que refere-se à família de modelos da DeepSeek como um todo.<br>
DeepSeek-R1 é um modelo especializado, voltado para raciocínio lógico e resolução de problemas.

---
## 2. Arquitetura do Modelo

O DeepSeek-R1 não é um modelo único, mas uma família de modelos que inclui: **DeepSeek-R1-Zero** e **DeepSeek-R1**.

- **DeepSeek-R1-Zero**: Representa o experimento inicial da equipe com aprendizado por reforço puro, sem qualquer ajuste fino supervisionado. Partindo de um modelo base, a equipe aplicou RL diretamente, permitindo que o modelo desenvolvesse capacidades de raciocínio por tentativa e erro. Apesar de atingir resultados impressionantes (71% de acurácia no AIME 2024), enfrentou limitações significativas em legibilidade e consistência de linguagem.

- **DeepSeek-R1**: Utiliza uma abordagem de treinamento mais sofisticada em múltiplas etapas. Em vez de RL puro, inicia com ajuste fino supervisionado em um pequeno conjunto de exemplos cuidadosamente selecionados (chamados de "dados de partida fria") antes de aplicar RL. Esta abordagem supera as limitações do DeepSeek-R1-Zero, alcançando melhor desempenho. 

---
## 3. Treinamento 

1. **Aprendizado por Reforço**: Diferente de modelos tradicionais que dependem predominantemente de aprendizado supervisionado, o DeepSeek-R1 utiliza RL extensivamente. O treinamento emprega otimização relativa de políticas em grupo (GRPO), focando em recompensas de precisão e formato para aprimorar as capacidades de raciocínio sem a necessidade de grandes volumes de dados rotulados.

2. **Técnicas de Destilação**: Para democratizar o acesso a modelos de alto desempenho, a DeepSeek também lançou versões destiladas do R1, variando de 1,5 bilhão a 70 bilhões de parâmetros. Essas versões utilizam arquiteturas como Qwen e Llama, demonstrando que raciocínios complexos podem ser encapsulados em modelos menores e mais eficientes. O processo de destilação envolve ajuste fino desses modelos menores com dados sintéticos de raciocínio gerados pelo DeepSeek-R1 completo, preservando alto desempenho a um custo computacional reduzido.

- **DeepSeek-R1-Zero**:
  - Inicia com o modelo base
  - Aplica aprendizado por reforço diretamente
  - Utiliza recompensas simples baseadas em precisão e formato

- **DeepSeek-R1**:
  1. Ajuste fino supervisionado inicial com milhares de exemplos de alta qualidade
  2. Aprendizado por reforço focado em tarefas de raciocínio
  3. Coleta de novos dados de treinamento por amostragem de rejeição
  4. Aprendizado por reforço final abrangendo todos os tipos de tarefas

---
## 4. Downloads

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
## 5. Benchmarks

> Consulte aqui: https://github.com/deepseek-ai/DeepSeek-LLM/blob/main/README.md#3-evaluation-results

---
## 6. Comparação com outros Modelos

Ao contrário dos modelos fechados, o DeepSeek-R1 oferece visibilidade do seu processo de raciocínio passo a passo, permitindo aos usuários rastrear, verificar e refinar as conclusões geradas pela IA.

Além disso, por ser open-source sob a licença MIT, o DeepSeek-R1 oferece diversas vantagens:
- **Personalização sem Restrições**: Desenvolvedores podem ajustar e modificar o modelo para casos de uso específicos, sem limitações de licenciamento.
- **Melhorias pela Comunidade**: Pesquisadores e especialistas podem contribuir com aprimoramentos.
- **Eficiência de Custos**: É uma alternativa ideal para empresas que buscam integrar IA sem custos recorrentes.

---
## 7. Requisitos de Sistema

| Versão do Modelo | VRAM (GPU)      | RAM (CPU)     | Armazenamento |
|------------------|-----------------|---------------|---------------|
| DeepSeek-R1 **1.5B**            | 4GB+           | 8GB+          | 5GB           |
| DeepSeek-R1 **7B**              | 12GB+          | 16GB+         | 10GB          |
| DeepSeek-R1 **8B**              | 16GB+          | 32GB+         | 15GB          |
| DeepSeek-R1 **14B**             | 24GB+          | 64GB+         | 30GB          |
| DeepSeek-R1 **32B**             | 48GB+          | 128GB+        | 60GB          |
| DeepSeek-R1 **70B**             | 80GB+          | 256GB+        | 120GB         |

---
## 8. Executando o DeepSeek-R1 Localmente com Ollama

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

---
## 9. Acesso via API DeepSeek

A DeepSeek oferece uma API compatível com o formato da OpenAI, permitindo integração em diversas aplicações.

- a. **Obter uma Chave de API**: Acesse a plataforma de API da DeepSeek para criar uma conta e gerar sua chave de API exclusiva.
- b. Defina a `base_url` para `https://api.deepseek.com/v1`.
- c. Use sua chave de API para autenticação, geralmente via Bearer Token no cabeçalho HTTP.
- d. Utilize a API para enviar prompts e receber respostas do DeepSeek-R1.
- e. DeepSeek API Docs: https://api-docs.deepseek.com/

```python
# Please install OpenAI SDK first: `pip3 install openai`

from openai import OpenAI

client = OpenAI(api_key="<DeepSeek API Key>", base_url="https://api.deepseek.com")

response = client.chat.completions.create(
    model="deepseek-chat",
    messages=[
        {"role": "system", "content": "You are a helpful assistant"},
        {"role": "user", "content": "Hello"},
    ],
    stream=False
)

print(response.choices[0].message.content)
```

---
## 10. Aplicações que usam o DeepSeek

> Em construção

---
## 11. Fontes

- [Artigo DeepSeek-R1](https://arxiv.org/abs/2501.12948)
- [Artigo DeepSeek-LLM](https://arxiv.org/abs/2401.02954)
- [Artigo Medium - PankaJ](https://medium.com/@pankaj_pandey/deepseek-r1-an-advanced-reasoning-model-for-ai-applications-using-ollama-0497a4899cb2)
- [Artigo Medium - Isaak Kamau](https://medium.com/@isaakmwangi2018/a-simple-guide-to-deepseek-r1-architecture-training-local-deployment-and-hardware-requirements-300c8799112)
- [Site Oficial](https://www.deepseek.com/)
- [HuggingFace](https://huggingface.co/deepseek-ai)

## Mistral Nemo 12B

Substituição direta do Mistral 7B
Projetado para aplicações globais e multilíngues. Treinado para chamadas de função, possui uma grande janela de contexto e se destaca particularmente em inglês, francês, alemão, espanhol, italiano, português, chinês, japonês, coreano, árabe e hindi.

---
## 🔍 Características Principais

- **Desenvolvido por:** Mistral AI
- **Arquitetura** Modelo de transformers.
  - Camadas: 40
  - Dimensão: 5.120
  - Head dim: 128
  - Hidden dim: 14.436
  - Função de Ativação: SwiGLU
  - Número de heads: 32
  - Número de kv-heads: 8 (GQA)
  - Tamanho do vocabulário: 2**17 ~= 128k

---
## 🧪 Desempenho em Benchmarks

## **Geral**

| **Benchmark**              | **Resultado** |
|----------------------------|---------------|
| **HellaSwag (0-shot)**      | 83.5%         |
| **Winogrande (0-shot)**     | 76.8%         |
| **OpenBookQA (0-shot)**     | 60.6%         |
| **CommonSenseQA (0-shot)**  | 70.4%         |
| **TruthfulQA (0-shot)**     | 50.3%         |
| **MMLU (5-shot)**           | 68.0%         |
| **TriviaQA (5-shot)**       | 73.8%         |
| **NaturalQuestions (5-shot)**| 31.2%         |

## **MMLU**

| **Language**  | **Score** |
|---------------|-----------|
| French        | 62.3%     |
| German        | 62.7%     |
| Spanish       | 64.6%     |
| Italian       | 61.3%     |
| Portuguese    | 63.3%     |
| Russian       | 59.2%     |
| Chinese       | 59.0%     |
| Japanese      | 59.0%     |

---
## ✅ Prós
1. **Tokenizer**: Treinado com mais de 100 línguas e com compressão eficiente.
2. **Tokenizer**: Grande janela de contexto (128k tokens). Lida com sequências longas, ideal para documentos complexos.

---
## ❌ Contras
1. **Linguagem tóxica**: Foi treinado com dados que contém linguagem tóxica. Pode retornar respostas tóxicas especialmente se receber inputs do tipo.
2. **Precisão**: Pode retornar respostas erradas, omitir informações ou incluir texto irrelevante nas respostas.

---
## 🚀 Como Usar 
> Pelo mistral inference (recomendado).

### **Instalação**
```bash
pip install mistral_inference
```

### **Download**
```python
from huggingface_hub import snapshot_download
from pathlib import Path

mistral_models_path = Path.home().joinpath('mistral_models', 'Nemo-v0.1')
mistral_models_path.mkdir(parents=True, exist_ok=True)

snapshot_download(repo_id="mistralai/Mistral-Nemo-Base-2407", allow_patterns=["params.json", "consolidated.safetensors", "tekken.json"], local_dir=mistral_models_path)
```

### **Demo**
```bash
mistral-demo $HOME/mistral_models/Nemo-v0.1
```

### **Finetuning**
[mistral-finetune](https://github.com/mistralai/mistral-finetune).

---
## 📜 Fontes
https://mistral.ai/news/mistral-nemo/

https://huggingface.co/nvidia/Mistral-NeMo-12B-Base

https://huggingface.co/mistralai/Mistral-Nemo-Base-2407

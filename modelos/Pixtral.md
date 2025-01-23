## Pixtral 12B

Treinado para entender tanto imagens naturais quanto documentos. Demonstra habilidades em tarefas como compreensão de gráficos e figuras, resposta a perguntas em documentos, raciocínio multimodal e seguimento de instruções. 

---
## 🔍 Características Principais

- **Desenvolvido por:** Mistral AI
- **Arquitetura:**  Baseada em Transformers, encoders e decoders.
  - Codificador de visão de 400M parâmetros treinado do zero
  - Decodificador multimodal de 12B parâmetros baseado no Mistral Nemo
- **Capacidades:**
  - Nativamente multimodal, treinado com dados intercalados de imagem e texto
  - Desempenho de ponta em sua classe de peso em tarefas multimodais
  - Mantém desempenho de última geração em benchmarks apenas de texto
  - Suporta tamanhos variados de imagem

---
## 🧪 Desempenho em Benchmarks

## **Benchmarks multimodais**

| **MMMU (CoT)** | **Mathvista (CoT)** | **ChartQA (CoT)** | **DocVQA (ANLS)** | **VQAv2 (VQA Match)** |
|----------------|---------------------|-------------------|-------------------|-----------------------|
| 52.5           | 58.0                | 81.8              | 90.7              | 78.6                  |

## **Benchmarks de texto**

| **MMLU (5-shot)** | **Math (Pass@1)** | **Human Eval (Pass@1)** |
|-------------------|-------------------|-------------------------|
| 69.2              | 48.1              | 72.0                    |

## **Comparação com modelos maiores**

| **Benchmark**               | **Pixtral 12B** | **Claude-3 Haiku** | **Gemini-1.5 Flash 8B (0827)** | **LLaVA-OV 72B** | **GPT-4o** | **Claude-3.5 Sonnet** |
|-----------------------------|------------------|--------------------|-------------------------------|------------------|------------|-----------------------|
| **MMMU (CoT)**               | 52.5             | 50.4               | 50.7                          | 54.4             | 68.6       | 68.0                  |
| **Mathvista (CoT)**          | 58.0             | 44.8               | 56.9                          | 57.2             | 64.6       | 64.4                  |
| **ChartQA (CoT)**            | 81.8             | 69.6               | 78.0                          | 66.9             | 85.1       | 87.6                  |
| **DocVQA (ANLS)**            | 90.7             | 74.6               | 79.5                          | 91.6             | 88.9       | 90.3                  |
| **VQAv2 (VQA Match)**        | 78.6             | 68.4               | 65.5                          | 83.8             | 77.8       | 70.7                  |

---
## ✅ Prós
1. **Multimodal**: Processa tanto texto quanto imagens, bom para compreensão de gráficos e documentos.
2. **Tokenizer**: Grande janela de contexto (128k tokens). Lida com sequências longas, ideal para documentos complexos.
3. **Processamento Flexível de Imagens**: Suporta tamanhos variados de imagem e resolução natural.

---
## ❌ Contras
1. **Especializado**: Seu aspecto multimodal o torna inferior a certos modelos especializados de texto único.
2. **Treinamento**: Requer grandes conjuntos de dados para um finetuning eficiente.

---
## 🚀 Como Usar
> É recomendado o uso do modelo com a biblioteca vllm.

### **Instalação**
vllm
```bash
pip install --upgrade vllm
```
mistral_common
```bash
pip install --upgrade mistral_common
```

### **Exemplo**

```python
from vllm import LLM
from vllm.sampling_params import SamplingParams

model_name = "mistralai/Pixtral-12B-2409"

sampling_params = SamplingParams(max_tokens=8192)

llm = LLM(model=model_name, tokenizer_mode="mistral")

prompt = "Describe this image in one sentence."
image_url = "https://picsum.photos/id/237/200/300"

messages = [
    {
        "role": "user",
        "content": [{"type": "text", "text": prompt}, {"type": "image_url", "image_url": {"url": image_url}}]
    },
]

outputs = llm.chat(messages, sampling_params=sampling_params)

print(outputs[0].outputs[0].text)
```

### **Finetuning**
[mistral-finetune](https://github.com/mistralai/mistral-finetune).

---
## 📜 Fontes
https://mistral.ai/news/pixtral-12b/

https://huggingface.co/mistralai/Pixtral-12B-2409

https://unfoldai.com/pixtral-12b/

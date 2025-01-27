<div align="center">
  <a href="https://huggingface.co/collections/microsoft/phi-4-677e9380e514feb5577a40e4" target="_blank">
    <img alt="Hugging Face" src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-DeepSeek%20AI-ffc107?color=ffc107&logoColor=white" />
  </a>
</div>

<p align="center">
  <a href="https://arxiv.org/abs/2412.08905"><b>📜 Paper - Phi 4</b></a>
</p>

---
## 1. Introdução

Phi-4, é o mais recente modelo de linguagem pequeno da família Phi, que oferece resultados de alta qualidade em um tamanho compacto (14 bilhões de parâmetros).

Este modelo se destaca em raciocínio complexo em áreas como matemática, além do processamento de linguagem convencional.

---
## 2. Comparação com outros modelos

Diferentemente da maioria dos modelos de linguagem, que se baseiam principalmente em fontes de dados orgânicas, como conteúdo da web ou código, o phi-4 incorpora estrategicamente dados sintéticos ao longo de todo o processo de treinamento.

Enquanto os modelos anteriores da família Phi se concentravam em distilar as capacidades de um modelo professor (especificamente o GPT-4), o phi-4 supera substancialmente seu modelo professor em capacidades de perguntas e respostas focadas em STEM, evidenciando que as técnicas de geração de dados e pós-treinamento vão além da distilação.

Apesar de mudanças mínimas na arquitetura em relação ao phi-3, o phi-4 alcança um desempenho robusto em relação ao seu tamanho, especialmente em benchmarks focados em raciocínio, devido a melhorias nos dados, currículo de treinamento e inovações no esquema de pós-treinamento.

---
## 3. Desenvolvimento do Phi-4

1. **Dados Sintéticos para Pré-treinamento e Treinamento Intermediário**:
    - Conjuntos de dados sintéticos de alta qualidade são projetados para priorizar raciocínio e resolução de problemas.
2. **Curadoria e Filtragem de Dados Orgânicos de Alta Qualidade**:
    - Fontes orgânicas, como conteúdo da web, livros licenciados e repositórios de código, são cuidadosamente filtradas para gerar sementes de dados sintéticos focadas em raciocínio profundo e valor educacional.
3. **Pós-Treinamento**:
    -  receita de pós-treinamento foi aprimorada no phi-4 por meio da criação de novas versões refinadas de conjuntos de dados SFT.

---
## 4. Benchmarks

![image](https://github.com/user-attachments/assets/75d254b0-c986-4c83-90af-5938cff98017)

Confira detalhes em: [Introducing Phi-4: Microsoft’s Newest Small Language Model Specializing in Complex Reasoning](https://techcommunity.microsoft.com/blog/aiplatformblog/introducing-phi-4-microsoft%E2%80%99s-newest-small-language-model-specializing-in-comple/4357090)

---
## 5. Download

|         Model         |                                Download                                    |                  
|:---------------------:|--------------------------------------------------------------------------: |
| Phi-4                 | [🤗 HuggingFace](https://huggingface.co/microsoft/phi-4)                   |

---
## 6. Requisitos de Sistema

| Requisito                 | Detalhes                                                       |
|---------------------------|---------------------------------------------------------------|
| **Memória RAM**            | Mínimo de 14 GB de RAM                                         |
| **Memória VRAM**           | Placa gráfica com VRAM recomendada, mas não essencial         |
| **Processador (CPU)**      | Processador moderno e de alto desempenho                       |
| **Armazenamento**          | Espaço suficiente em disco para o modelo e dados associados (recomenda-se 50gb) |
| **Sistema Operacional**   | Compatível com Linux, macOS ou Windows                        |
| **Python**                 | Python 3.8 ou superior                                         |
| **PyTorch**                | Para operações de aprendizado de máquina                      |
| **Transformers (Hugging Face)** | Para carregar e interagir com o modelo                   |

---
## 7. Executar com o LM Studio

1. **Baixe o LM Studio**: https://lmstudio.ai/download
2. **Baixe o Modelo**: Execute via terminal o código abaixo.
  ```bash
    lms get phi-4
  ```
3. **Código Python**:
  ```python
    # Example: reuse your existing OpenAI client code
    # Change the baseUrl to point to LM Studio
    from openai import OpenAI

    # Point to the local server
    client = OpenAI(base_url="http://localhost:1234/v1",
                    api_key="lm-studio")

    completion = client.chat.completions.create(
      model="phi-4",
      messages=[
        {"role": "system", "content": "Always answer in rhymes."},
        {"role": "user", "content": "Introduce yourself."}
      ],
      temperature=0.7,
    )

    print(completion.choices[0].message)
  ```

---
## 8. Fontes

- [Artigo Oficial](https://arxiv.org/abs/2412.08905)
- [Blog Microsoft](https://techcommunity.microsoft.com/blog/aiplatformblog/introducing-phi-4-microsoft%E2%80%99s-newest-small-language-model-specializing-in-comple/4357090)
- [Artigo Medium](https://ritvik19.medium.com/papers-explained-278-phi-4-ea59220f3f88)

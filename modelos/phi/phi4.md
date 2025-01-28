<div align="center">
  <a href="https://huggingface.co/collections/microsoft/phi-4-677e9380e514feb5577a40e4" target="_blank">
    <img alt="Hugging Face" src="https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Phi%204-ffc107?color=ffc107&logoColor=white" />
  </a>
</div>

<p align="center">
  <a href="https://arxiv.org/abs/2412.08905"><b>📜 Paper - Phi 4</b></a>
</p>

---
## 1. Introdução

Phi-4 é o mais recente modelo de linguagem da família Phi, projetado para oferecer resultados de alta qualidade em um tamanho compacto (14 bilhões de parâmetros). O modelo se destaca em raciocínio complexo em áreas como matemática, além do processamento de linguagem convencional, tornando-o uma ferramenta ideal para tarefas técnicas e científicas.

---
## 2. Comparação com Outros Modelos

Diferentemente da maioria dos modelos de linguagem, que dependem de fontes de dados orgânicas como conteúdo da web ou código, o Phi-4 utiliza dados sintéticos estrategicamente em todo o processo de treinamento. Isso proporciona vantagens significativas:

- **Desempenho STEM Superior**: O Phi-4 supera seu modelo professor (GPT-4) em tarefas relacionadas a STEM (Ciência, Tecnologia, Engenharia e Matemática).
- **Treinamento Inovador**: O uso de técnicas avançadas de geração de dados e pós-treinamento permite alcançar uma eficiência impressionante em raciocínio.
- **Robustez em Tamanho Compacto**: Mesmo com mudanças mínimas na arquitetura em relação ao Phi-3, o Phi-4 apresenta melhorias consideráveis devido à curadoria de dados, currículo de treinamento e inovações no esquema de pós-treinamento.

---
## 3. Desenvolvimento do Phi-4

1. **Dados Sintéticos para Pré-treinamento e Treinamento Intermediário**:
    - Conjuntos de dados sintéticos de alta qualidade foram criados para priorizar o raciocínio e a resolução de problemas, simulando cenários complexos e educacionais.

2. **Curadoria e Filtragem de Dados Orgânicos**:
    - Fontes de dados orgânicas (web, livros licenciados e repositórios de código) foram cuidadosamente filtradas para gerar sementes de dados sintéticos focadas em raciocínio profundo e valor educacional.

3. **Pós-Treinamento Aprimorado**:
    - O Phi-4 inclui uma receita de pós-treinamento aprimorada, que incorpora novas versões refinadas de conjuntos de dados supervisionados (SFT), melhorando o desempenho geral.

---
## 4. Benchmarks

O Phi-4 demonstra desempenho robusto em benchmarks focados em raciocínio e STEM, superando outros modelos de linguagem de tamanho semelhante. Veja a comparação completa no [Blog Oficial da Microsoft](https://techcommunity.microsoft.com/blog/aiplatformblog/introducing-phi-4-microsoft%E2%80%99s-newest-small-language-model-specializing-in-comple/4357090).

---
## 5. Download

|         Modelo          |                                Download                                    |                  
|:-----------------------:|--------------------------------------------------------------------------: |
| Phi-4                  | [🤗 HuggingFace](https://huggingface.co/microsoft/phi-4)                   |

---
## 6. Requisitos de Sistema

| Requisito                 | Detalhes                                                       |
|---------------------------|---------------------------------------------------------------|
| **Memória RAM**            | Mínimo de 14 GB                                              |
| **Memória VRAM**           | Placa gráfica recomendada, mas não essencial                 |
| **Processador (CPU)**      | Processador moderno de alto desempenho                       |
| **Armazenamento**          | Espaço mínimo recomendado: 50 GB                             |
| **Sistema Operacional**   | Compatível com Linux, macOS ou Windows                       |
| **Python**                 | Versão 3.8 ou superior                                       |
| **PyTorch**                | Necessário para operações de aprendizado de máquina          |
| **Transformers (Hugging Face)** | Para carregar e interagir com o modelo                   |

---
## 7. Execução com LM Studio

1. **Baixe o LM Studio**: [Download aqui](https://lmstudio.ai/download)
2. **Baixe o Modelo**: Execute o seguinte comando no terminal:
  ```bash
  lms get phi-4
  ```
3. **Uso com Código Python**:
  ```python
  # Exemplo utilizando o cliente OpenAI
  from openai import OpenAI

  # Conectar ao servidor local
  client = OpenAI(base_url="http://localhost:1234/v1", api_key="lm-studio")

  completion = client.chat.completions.create(
      model="phi-4",
      messages=[
          {"role": "system", "content": "Você é um assistente amigável."},
          {"role": "user", "content": "Explique o Phi-4."}
      ],
      temperature=0.7,
  )

  print(completion.choices[0].message)
  ```

---
## 8. Fontes

- [Artigo Oficial (arXiv)](https://arxiv.org/abs/2412.08905)
- [Blog Microsoft](https://techcommunity.microsoft.com/blog/aiplatformblog/introducing-phi-4-microsoft%E2%80%99s-newest-small-language-model-specializing-in-comple/4357090)
- [Artigo no Medium](https://ritvik19.medium.com/papers-explained-278-phi-4-ea59220f3f88)


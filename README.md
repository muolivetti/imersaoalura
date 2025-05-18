# Agente de planejamento de viagens com Gemini

Este projeto utiliza o modelo Gemini do Google para criar um sistema de planejamento de viagens com múltiplos agentes. 
O sistema é capaz de fornecer informações turísticas, planejamento financeiro e roteiros detalhados para os usuários, tudo com base em suas preferências e informações de viagem.

## Funcionalidades

O sistema é composto por três agentes principais:

1.  **Agente de Turismo:** Fornece um panorama geral do destino da viagem, incluindo informações históricas, culturais, gastronômicas e dicas de hospedagem e transporte.
2.  **Agente Financeiro:** Estima os custos totais da viagem, considerando passagens aéreas, hospedagem, alimentação, transporte, passeios e um caixa extra para imprevistos.
3.  **Agente de Roteiro:** Cria um roteiro diário detalhado para a viagem, levando em conta o destino, duração, época, orçamento e preferências do usuário.

## Tecnologias utilizadas

* **Google Gemini:** Modelo de linguagem do Google para geração de texto e busca de informações.
* **Google ADK (Agent Development Kit):** Framework para desenvolvimento de agentes.
* **Google Cloud AI Platform:** Para interagir com o Gemini API.
* **Python:** Linguagem de programação principal.
* **Bibliotecas Python:**
    * `google-genai`: Para interagir com o Gemini API.
    * `google-adk`: Para desenvolvimento de agentes.
    * `google_search`: Ferramenta para realizar buscas no Google.
    * `requests`: Para fazer requisições HTTP.
    * `IPython.display`: Para exibir texto formatado no Colab.
    * `textwrap`: Para formatar a saída de texto.

## Pré-requisitos

* Conta no Google Cloud Platform com a API do Gemini habilitada.
* Chave da API do Google Gemini configurada como uma variável de ambiente (`GOOGLE_API_KEY`). Você pode usar o Google Colab `userdata.get()` para armazená-la com segurança.
* Python 3.6 ou superior instalado.
* pip (gerenciador de pacotes do Python) instalado.

## Como usar

1.  **Configurar a Chave da API:**

    Certifique-se de que você configurou a variável de ambiente `GOOGLE_API_KEY` com sua chave da API do Gemini. No Google Colab, você pode usar:

    ```python
    from google.colab import userdata
    import os
    os.environ["GOOGLE_API_KEY"] = userdata.get('GOOGLE_API_KEY')
    ```

2.  **Executar o Script:**

    Execute o script Python principal para iniciar o sistema de planejamento de viagens. O script irá solicitar as informações da viagem do usuário.

    ```bash
    python nome_do_seu_script.py  # Ex: main.py
    ```

3.  **Interagir com o Sistema:**

    O sistema irá guiá-lo através de uma série de perguntas sobre o destino, datas, preferências e orçamento da viagem. Responda às perguntas para que os agentes possam gerar o plano de viagem.

## Estrutura do Código

* `main.py` (ou nome do seu script principal): Contém o fluxo principal do programa, coleta as informações do usuário e chama os agentes.
* `agentes.py` (ou onde você definiu os agentes): Define os agentes de turismo, financeiro e roteiro, incluindo suas instruções, ferramentas e funcionalidades.
* `funcoes_auxiliares.py` (opcional): Pode conter funções auxiliares como `call_agent` e `to_markdown`.
* `requirements.txt` (opcional): Lista as dependências do projeto.

## Explicação dos Agentes

1.  **Agente de Turismo (`agente_turismo`):**

    * **Responsabilidade:** Fornecer um panorama geral do destino da viagem.
    * **Ferramentas:** `google_search`.
    * **Saída:** Um resumo detalhado do destino, incluindo história, cultura, gastronomia, hospedagem, transporte e atividades.

2.  **Agente Financeiro (`agente_financeiro`):**

    * **Responsabilidade:** Estimar os custos da viagem.
    * **Ferramentas:** `google_search`.
    * **Saída:** Um planejamento financeiro detalhado, incluindo custos de passagens, hospedagem, alimentação, transporte, passeios e um caixa extra.

3.  **Agente de Roteiro (`agente_roteiro`):**

    * **Responsabilidade:** Criar um roteiro diário da viagem.
    * **Ferramentas:** Nenhuma (usa as informações fornecidas e os resultados dos outros agentes).
    * **Saída:** Um roteiro detalhado com sugestões de atividades, restaurantes e dicas para cada dia da viagem.

## Exemplo de Uso

1.  O usuário executa o script e fornece as informações da viagem (destino, datas, preferências, orçamento).
2.  O `agente_turismo` é chamado para fornecer um resumo do destino.
3.  O `agente_financeiro` é chamado para estimar os custos da viagem.
4.  O `agente_roteiro` é chamado para gerar o roteiro detalhado.
5.  Os resultados de cada agente são exibidos ao usuário.


## Licença

[Coloque aqui a licença do seu projeto, por exemplo, MIT]

## Autor

Murilo Olivetti

## Agradecimentos

* Agradecimentos ao Google pela disponibilização do Gemini e do ADK.
* Agradecimentos à Alura pelo curso que inspirou este projeto.

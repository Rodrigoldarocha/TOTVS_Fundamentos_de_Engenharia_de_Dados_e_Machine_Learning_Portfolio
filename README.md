# TOTVS - Fundamentos de Engenharia de Dados e Machine Learning — Pipeline ETL com Python e IA Generativa

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![IA](https://img.shields.io/badge/IA-Simulação%20Local-brightgreen)
![Pandas](https://img.shields.io/badge/Pandas-2.0-green)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)

> **Autor:** Rodrigo Rocha
> **Bootcamp:** TOTVS - Fundamentos de Engenharia de Dados e Machine Learning — DIO

---

## O que é esse projeto?

Esse projeto foi desenvolvido durante o bootcamp **TOTVS - Fundamentos de Engenharia de Dados e Machine Learning** da DIO. O objetivo é construir um pipeline ETL completo usando Python para gerar mensagens de marketing personalizadas para clientes bancários.

ETL significa **Extração, Transformação e Carregamento** — e esse é exatamente o fluxo que segui aqui:

```
TOTVS 2026 - SDW2023.csv  -->  [EXTRACT]  -->  [TRANSFORM]  -->  [LOAD]  -->  TOTVS 2026 - SDW2023_resultado.csv
```

---

## Por que adaptei o projeto original?

Duas APIs foram descontinuadas ou estavam sem créditos durante o desenvolvimento:

- A **API pública da Santander Dev Week** (`sdw-2023-prd.up.railway.app`) foi desativada após o evento
- A **API da OpenAI** (GPT-3.5 Turbo), usada no projeto original para gerar as mensagens, exige créditos pagos

Em vez de travar nisso, adaptei as três etapas mantendo o mesmo conceito de ETL:

- **Extract**: CSV completo com dados dos clientes, no lugar da API GET
- **Transform**: função local que gera mensagens personalizadas por perfil financeiro, no lugar da API de IA
- **Load**: exportação local em CSV e JSON, no lugar da API PUT

O notebook ainda documenta como a chamada para a API da OpenAI funcionaria, caso queira reativar essa parte futuramente.

---

## Como rodar o projeto

### 1. Clone o repositório
```bash
git clone https://github.com/seu-usuario/totvs-etl-pipeline.git
cd totvs-etl-pipeline
```

### 2. Instale as dependências
```bash
pip install pandas
```

Não é necessário nenhuma API Key — o projeto roda 100% localmente.

### 3. Execute o notebook

Abra o arquivo `TOTVS_Fundamentos_de_Engenharia_de_Dados_e_Machine_Learning_Portfolio.ipynb` no Jupyter ou Google Colab e execute as células em ordem.

### Quer usar a API da OpenAI?

Se quiser rodar com a IA de verdade, basta:
1. Criar uma conta em [platform.openai.com](https://platform.openai.com) e adicionar créditos
2. Gerar uma chave em **API Keys > Create new secret key**
3. Seguir as instruções dentro do próprio notebook na seção **"Como seria com uma API de IA"**

---

## Estrutura do projeto

```
totvs-etl-pipeline/
├── TOTVS_Fundamentos_de_Engenharia_de_Dados_e_Machine_Learning_Portfolio.ipynb
├── TOTVS 2026 - SDW2023.csv                     # Dados de entrada dos clientes
├── TOTVS 2026 - SDW2023_resultado.csv           # Saída com as mensagens geradas (criado ao rodar)
├── TOTVS 2026 - SDW2023_resultado.json          # Saída em JSON com estrutura completa (criado ao rodar)
└── README.md
```

---

## Tecnologias usadas

| Tecnologia | Para que usei |
|-----------|--------------|
| Python 3.10+ | Linguagem principal do projeto |
| Pandas | Leitura e manipulação do CSV |
| JSON | Estruturação e exportação dos dados |
| OpenAI SDK *(opcional)* | Integração com GPT — documentado no notebook, não executado |

---

## Exemplo de output

```
============================================================
         RELATÓRIO FINAL DO PIPELINE ETL
============================================================
  Clientes processados : 5
  Mensagens geradas    : 5
  Arquivos salvos      : TOTVS 2026 - SDW2023_resultado.csv e .json
  Modelo de IA         : Simulação local (sem API)
============================================================

Mensagens geradas por cliente:
------------------------------------------------------------
  Naruto      ->  Naruto, todo grande investidor começou com pouco. Dê o primeiro passo hoje!
  Hinata      ->  Hinata, investir R$ 50 por mês já faz diferença no longo prazo. Comece agora!
  Sasuke      ->  Sasuke, seu patrimônio merece uma estratégia avançada. Explore novos ativos!
  Sakura      ->  Sakura, todo grande investidor começou com pouco. Dê o primeiro passo hoje!
  Kakashi     ->  Kakashi, investidores premium fazem o dinheiro trabalhar 24h. Que tal o próximo nível?
------------------------------------------------------------
```

---

*Desenvolvido durante o TOTVS - Fundamentos de Engenharia de Dados e Machine Learning — DIO*

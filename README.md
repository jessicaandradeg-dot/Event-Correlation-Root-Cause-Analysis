# Event Correlation & Root Cause Analysis

Protótipo de Machine Learning para correlação de eventos e identificação de possíveis causas-raiz em um ambiente distribuído simulado.

## O que o projeto demonstra

- geração determinística de incidentes e eventos sintéticos;
- coocorrência de eventos e janela temporal;
- engenharia de atributos de eventos e severidade;
- classificação supervisionada com Random Forest;
- ranking de causas-raiz com Top-1 e Top-3.

## Executar localmente

Requisitos: Python 3.10 ou superior.

```bash
python -m venv .venv
```

No Windows:

```powershell
.venv\Scripts\Activate.ps1
```

No macOS/Linux:

```bash
source .venv/bin/activate
```

Instale as dependências e abra o notebook:

```bash
python -m pip install -r requirements.txt
jupyter notebook RCA_Event_Correlation.ipynb
```

O notebook não depende de arquivos externos: os dados são gerados durante a execução. A semente aleatória `42` permite reproduzir o experimento.

## Estrutura

```text
.
├── RCA_Event_Correlation.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Interpretação dos resultados

As métricas são calculadas no próprio notebook. A acurácia alta é esperada porque os padrões usados para gerar os eventos são fortemente separados por causa-raiz. Isso não representa desempenho de produção.

Em sistemas reais, seria necessário lidar com ruído, dados ausentes, sobreposição de causas, dependências entre serviços e validação temporal. Dados reais devem ser anonimizados antes de qualquer publicação.

## Próximos passos

- adicionar recorrência e dependências entre serviços;
- substituir a divisão aleatória por validação temporal;
- avaliar o modelo com dados reais anonimizados;
- incluir métricas por classe e análise de calibração;
- comparar o ranking supervisionado com métodos formais de inferência causal.

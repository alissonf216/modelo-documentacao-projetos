---
layout: default
title: Modelagem
nav_order: 3
---

# Modelagem
{: .no_toc }

## Modelagem

A modelagem do projeto de previsão de casos de Dengue no Brasil envolve várias etapas importantes, desde a análise de séries temporais até a validação dos modelos. A seguir, detalhamos cada uma dessas etapas, acompanhadas de trechos de código utilizados no processo.

### Análise de Séries Temporais

A análise de séries temporais é utilizada para entender a evolução dos casos ao longo do tempo. Esta análise permite identificar padrões e tendências, essenciais para a criação de modelos preditivos precisos.

#### Código (parte do código em Python)
{: .no_toc }
```python
tmp_registers = registers[registers.ano > 2017]


### Treinamento de Modelos

O desenvolvimento e treinamento de modelos preditivos foram realizados utilizando algoritmos como o Prophet. Este algoritmo é eficaz na previsão de séries temporais e foi escolhido por sua capacidade de lidar com sazonalidade e efeitos de feriados.

#### Código (parte do código em Python)
{: .no_toc }
```python
def forecast_model_parameters_search(data, date_column, target_column, forecast_periods, groupby_columns, n, param_grid, interval_width):
    forecast_results = pd.DataFrame()
    detailed_results = {}
    best_params = {}
    best_metrics = {}
    ...
    return forecast_results, last_train, last_test, last_best_params, detailed_results, last_model, last_future, best_params, best_metrics


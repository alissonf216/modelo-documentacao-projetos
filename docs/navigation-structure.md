---
layout: default
title: Modelagem
nav_order: 3
---

# Modelagem
{: .no_toc }

### Modelagem

A modelagem do projeto de previsão de casos de Dengue no Brasil envolve várias etapas importantes, desde a análise de séries temporais até a validação dos modelos. A seguir, detalhamos cada uma dessas etapas, acompanhadas de trechos de código utilizados no processo.

### Análise de Séries Temporais

A análise de séries temporais é utilizada para entender a evolução dos casos ao longo do tempo. Esta análise permite identificar padrões e tendências, essenciais para a criação de modelos preditivos precisos.

#### Código (parte do código em Python)
{: .no_toc }
```python
tmp_registers = registers[registers.ano > 2017]
```


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
```

### Validação de Modelos

A validação e avaliação dos modelos são cruciais para garantir precisão e robustez. Utilizamos técnicas de validação cruzada e métricas de desempenho, como MAE (Mean Absolute Error), RMSE (Root Mean Squared Error) e R-squared (R²).

#### Código (parte do código em Python)
{: .no_toc }
```python
def evaluate_forecast_metrics(test: pd.DataFrame, forecast: pd.DataFrame, train: pd.DataFrame, n_params: int):
    y_true = test['y'].values
    y_pred = forecast['yhat'][-len(test):].values
    y_train = train['y'].values

    mae = mean_absolute_error(y_true, y_pred)
    mse = mean_squared_error(y_true, y_pred)
    rmse = np.sqrt(mse)
    mape = np.mean(np.abs((y_true - y_pred) / y_true)) * 100

    n = len(y_train)
    d = np.abs(np.diff(y_train)).sum() / (n - 1)
    mase = np.mean(np.abs(y_true - y_pred)) / d

    r2 = r2_score(y_true, y_pred)
    adj_r2 = 1 - ((1 - r2) * (len(y_true) - 1) / (len(y_true) - n_params - 1))

    return {
        'MAE': mae,
        'MSE': mse,
        'RMSE': rmse,
        'MAPE': mape,
        'MASE': mase,
        'R-squared': r2,
        'Adjusted R-squared': adj_r2
    }

last_forecast = last_model.predict(last_future)
n_params = len(best_params)
metrics = evaluate_forecast_metrics(last_test, last_forecast, last_train, n_params)

print(metrics)

```

### Visualização dos Resultados

A visualização dos resultados permite uma melhor compreensão das previsões realizadas pelos modelos. Gráficos são gerados para ilustrar as previsões de casos de dengue.

#### Código (parte do código em Python)
{: .no_toc }
```python

n_groups = forecast_dengue[group_columns].drop_duplicates().shape[0]
n_cols = 3
n_rows = (n_groups + n_cols - 1) // n_cols 

fig, axes = plt.subplots(n_rows, n_cols, figsize=(18, 6 * n_rows), sharex=True)
axes = axes.flatten()  

for idx, (name, group) in enumerate(forecast_dengue.groupby(group_columns)):
    if idx < len(axes): 
        ax = axes[idx]

        ax.plot(group['mes_ano'], group['previsao_pacientes'], color='orange', label='Previsão de Pacientes')
        ax.fill_between(group['mes_ano'], group['previsao_pacientes'], group['previsao_maxima_pacientes'], color='orange', alpha=0.3, label='Máximo de Pacientes')

        ax.set_title(f'Previsão para: {", ".join(map(str, name))}')
        ax.set_xlabel('Data')
        ax.set_ylabel('Número de Pacientes')
        ax.legend()

for i in range(idx + 1, len(axes)):
    axes[i].axis('off')

plt.tight_layout()
plt.show()

```



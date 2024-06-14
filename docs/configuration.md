---
layout: default
title: Estrutura do Projeto
nav_order: 2
---

# Estrutura do Projeto
{: .no_toc }

Estrutura do projeto.
{: .fs-6 .fw-300 }


### Estrutura do Projeto

O projeto de previsão de casos de Dengue no Brasil foi desenvolvido utilizando diversas tecnologias, frameworks e bases de dados. A seguir, são apresentados os requisitos e componentes do projeto.

#### Repositório e Gestão de Tarefas

- **Repositório GitHub**: O projeto está hospedado no GitHub. Todas as contribuições são gerenciadas através de pull requests e issues.

- **GitHub Projects**: Utilizado para gerenciamento de tarefas e planejamento de sprints. As tarefas são organizadas em epics, histórias de usuário e tarefas técnicas.

#### Base de Dados

- **Coleta de Dados**: Os dados históricos de casos de dengue são obtidos de fontes confiáveis, como o DATASUS e o Sistema de Informação de Agravos de Notificação (SINAN).

  - **Dataset**: [Arbovirus clinical data, Brazil, 2013–2020](https://data.mendeley.com/datasets/2d3kr8zynf/4), Referência: Sampaio, Vanderson; Endo, Patricia; Lynn, Theo; Oliveira, Thomás; Silva Neto, Sebastião; Medeiros Neto, Leonides; Teixeira, Igor (2022), “Arbovirus clinical data, Brazil, 2013–2020”, Mendeley Data, V4, doi: 10.17632/2d3kr8zynf.4

- **Processamento de Dados**: Utilização de pandas para limpeza e transformação dos dados.

- **Armazenamento**: Dados são armazenados no Amazon S3 para acesso seguro e eficiente.

#### Modelagem

- **Tecnologias e Ferramentas**: StatsModel, Algoritmo Prophet, Python, C#, .NET.

- **Atividades**:
  - Análise de Séries Temporais

  - Modelagem

  - Treinamento de Modelo

  - Validação de Modelo

#### Integração entre Back-End e Front-End

- **Tecnologias e Ferramentas**: Flutter, .NET, Dart.

- **Atividades**:

  - Criação dos serviços para consumo das APIs

  - Modelagem de dados

  - Desserialização dos dados

  - Tratamento de retornos das APIs

  - Criação de processos assíncronos

  - Validação do consumo de dados

#### Front-End

- **Tecnologias e Ferramentas**: Flutter, Dart, JavaScript.

- **Atividades**:

  - Montagem do ambiente em Dart/Flutter

  - Configuração do ambiente web para a plataforma

  - Criação da UI/UX

  - Codificação das funcionalidades e telas

  - Validação de fluidez

#### Infraestrutura

- **Provisionamento de Serviços de Computação em Nuvem AWS**:

  - **CloudFront**: Serviço de CDN para entrega da aplicação front-end

  - **S3**: Serviço de armazenamento para a aplicação front-end

  - **App Runner**: Serviço de aplicação para hospedagem da aplicação back-end

  - **Lambda Function**: Serviço de execução de código sem servidor

- **Criação do Código Terraform**: Para implantação da infraestrutura AWS


Este projeto utiliza um conjunto robusto de tecnologias e práticas para garantir a eficácia e a eficiência na previsão de casos de dengue no Brasil, auxiliando no combate e na prevenção da doença.


---
layout: default
title: Home
nav_order: 1
description: "O projeto:Previsão de casos de Dengue no Brasil, foi desenvolvido como parte do programa de pós-graduação em Ciências da Computação da Universidade Federal de São Paulo, na disciplina de Engenharia de Software. Ele se propõe a antecipar novos casos de dengue no Brasil."
permalink: /
---

# Previsão de Dengue no Brasil
{: .fs-9 }

O projeto surge como uma proposta para auxiliar no combate e prevenção da Dengue no Brasil.
{: .fs-6 .fw-300 }

[Teste agora][Teste agora]{: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
[Repositorio GitHub][Just the Docs repo]{: .btn .fs-5 .mb-4 .mb-md-0 }

---

{: .warning }
> Esta página ainda está em construção, utilizando como tema base o just-the-docs `main`. Em breve, haverá conteúdo disponível.


## Descrição do Projeto:

O projeto tem como objetivo desenvolver uma ferramenta para prever o número de casos de dengue no Brasil. A solução oferecerá uma interface interativa, permitindo ao usuário definir a granularidade das previsões com base em dados demográficos históricos, como logradouro, unidade federativa, gênero e faixa etária, auxiliando no planejamento e na tomada de decisões para o futuro.

## Motivação do Projeto:

A dengue, transmitida pelo mosquito Aedes aegypti, afeta milhões de brasileiros anualmente, desafiando a saúde pública e a economia. Este projeto busca combater a dengue através de uma ferramenta inovadora que prevê novos casos com precisão, utilizando técnicas avançadas de forecasting e análise de dados.

A solução oferecerá uma interface intuitiva, permitindo previsões detalhadas com base em dados demográficos como logradouro, unidade federativa, gênero e faixa etária. Esta precisão ajudará a direcionar recursos e ações de combate de forma eficaz.

Esperamos que a ferramenta seja um recurso valioso para pesquisadores, profissionais de saúde e gestores públicos, auxiliando na redução da incidência de dengue e na preservação de vidas ao antecipar surtos e entender padrões de propagação da doença.

## Estrutura Analítica do Projeto

A Estrutura Analítica do Projeto é uma decomposição hierárquica do trabalho a que foi executado pela equipe para atingir os objetivos do projeto e criar os entregáveis necessários. Ela divide o projeto em componentes menores e mais gerenciáveis, facilitando o planejamento, a execução e o controle das atividades. Abaixo estão listadas as principais etapas e tarefas deste projeto, detalhando os recursos e o esforço estimado para cada uma delas.

{: .note }
O detalhamento de cada grande tópico ou dos tópicos julgados necessários poderá ser acessado no menu lateral.

### 1. Configuração de Projeto
1.1. Alinhamento e Definição do Projeto
1.2. Criação de Repositório
1.3. Configuração do Projeto
1.4. Criação de Board de Tarefas

### 2. Base de Dados
2.1. Definição de Base de Dados
2.2. Tratamento de Dados
2.3. Análise Exploratória de Dados
2.4. Criação de Infraestrutura como Código (Terraform)

### 3. Modelagem
3.1. Análise de Séries Temporais
3.2. Modelagem
3.3. Treinamento de Modelo
3.4. Validação de Modelo

### 4. Integração entre Back e Front
4.1. Criação dos Serviços para Consumo das APIs
4.2. Modelagem de Dados
4.3. Desserialização dos Dados
4.4. Tratamento de Retornos das APIs
4.5. Criação de Processos Assíncronos
4.6. Validação do Consumo de Dados

### 5. Front End
5.1. Montagem do Ambiente em Dart/Flutter
5.2. Configuração do Ambiente Web para a Plataforma
5.3. Criação da UI/UX
5.4. Codificação das Funcionalidades e Telas
5.5. Validação de Fluidez

### 6. Infraestrutura
6.1. Provisionamento de Serviços de Computação em Nuvem AWS
6.1.1. CloudFront para Entrega da Aplicação Front-End
6.1.2. S3 para Armazenamento da Aplicação Front-End
6.1.3. App Runner para Hospedagem da Aplicação Back-End
6.1.4. Lambda Function para Execução de Código Sem Servidor
6.2. Criação de Código Terraform para Implantação da Infraestrutura AWS

### 7. Documentação
7.1. Descrição de Frameworks e Requisitos Técnicos
7.2. Montagem de Ambiente
7.3. Funcionalidades
7.4. Controle de Versão

#### Membros do grupo:

<ul class="list-style-none">
{% for contributor in site.github.contributors %}
  <li class="d-inline-block mr-1">
     <a href="{{ contributor.html_url }}"><img src="{{ contributor.avatar_url }}" width="32" height="32" alt="{{ contributor.login }}"></a>
  </li>
{% endfor %}
</ul>

[Jekyll]: https://jekyllrb.com
[Markdown]: https://daringfireball.net/projects/markdown/
[Liquid]: https://github.com/Shopify/liquid/wiki
[Front matter]: https://jekyllrb.com/docs/front-matter/
[Jekyll configuration]: https://jekyllrb.com/docs/configuration/
[source file for this page]: https://github.com/just-the-docs/just-the-docs/blob/main/index.md
[Just the Docs Template]: https://just-the-docs.github.io/just-the-docs-template/
[Just the Docs]: https://just-the-docs.com
[Teste agora]: https://github.com/FranklinAurelio/Engenharia_de_software_PPGCC
[Just the Docs repo]: https://github.com/FranklinAurelio/Engenharia_de_software_PPGCC
[Just the Docs README]: https://github.com/just-the-docs/just-the-docs/blob/main/README.md
[GitHub Pages]: https://pages.github.com/
[Template README]: https://github.com/just-the-docs/just-the-docs-template/blob/main/README.md
[GitHub Pages / Actions workflow]: https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/
[customize]: {% link docs/customization.md %}
[use the template]: https://github.com/just-the-docs/just-the-docs-template/generate

---
layout: default
title: Backend da Solução
nav_order: 4
---

### Backend da Solução

O backend da solução apresentada no diagrama utiliza uma infraestrutura na nuvem, mais especificamente na AWS (Amazon Web Services), para garantir escalabilidade, segurança e alta disponibilidade. A seguir, descreveremos cada componente do backend e seu papel dentro do fluxo de trabalho.

#### Armazenamento e Distribuição de Conteúdo

- **Amazon S3 (Simple Storage Service)**: Serve como o armazenamento centralizado para os arquivos e dados necessários. O conteúdo do projeto é versionado e mantido de forma segura no S3. Arquivos como configurações, dados estáticos e logs podem ser armazenados aqui.

- **CloudFront**: É o serviço de distribuição de conteúdo (CDN - Content Delivery Network) que garante a entrega rápida e segura dos arquivos armazenados no S3 para os dispositivos clientes. Através do CloudFront, o conteúdo é distribuído globalmente com baixa latência.

#### Processamento e API

- **API Gateway**: Atua como um ponto de entrada para todas as solicitações da API vindas dos dispositivos clientes. Ele gerencia chamadas, enfileira e as roteia para o serviço apropriado. Além disso, o API Gateway fornece funcionalidades como autenticação, autorização e monitoramento.

- **Lambda**: As funções Lambda são executadas sob demanda, proporcionando um ambiente de execução sem servidor (serverless). Elas processam as solicitações vindas através do API Gateway, realizando operações como leitura e escrita no S3, processamento de dados e integração com outros serviços.

- **Parquet**: Formato de armazenamento colunar que é utilizado para armazenar grandes volumes de dados de forma eficiente. A integração com Parquet permite a análise e manipulação eficiente dos dados.

#### Monitoramento e Logging

- **CloudWatch**: Serviço de monitoramento que coleta e rastreia métricas, coleta e monitora arquivos de log, e define alarmes. No contexto do backend, o CloudWatch monitora a performance das funções Lambda, a disponibilidade da API Gateway e a integridade dos dados no S3.

#### Integração e Deploy

- **GitHub**: Repositório de código-fonte onde o desenvolvimento colaborativo é gerenciado. A integração contínua (CI) e a entrega contínua (CD) são facilitadas através do GitHub, onde o código é versionado e os pipelines de deploy são automatizados.

- **Terraform**: Ferramenta de infraestrutura como código (IaC) que permite definir e provisionar toda a infraestrutura necessária no AWS de maneira declarativa. O Terraform gerencia os recursos como S3, API Gateway, Lambda e CloudFront, garantindo consistência e reprodutibilidade no ambiente.

#### Região

- **Region (us-east-1)**: Todos os serviços AWS mencionados estão localizados na região "us-east-1", garantindo proximidade e menor latência para os usuários finais nesta área geográfica.

### Fluxo de Trabalho

1. **Desenvolvimento e Deploy**: O código é desenvolvido e versionado no GitHub. Utilizando Terraform, a infraestrutura necessária é provisionada na AWS.

2. **Armazenamento**: Arquivos e dados são armazenados no S3. O conteúdo é distribuído globalmente via CloudFront.

3. **Solicitações de Cliente**: Dispositivos clientes fazem requisições à API através do API Gateway.

4. **Processamento**: O API Gateway roteia as requisições para as funções Lambda, que processam os dados e interagem com o S3 ou outras fontes de dados como Parquet.

5. **Monitoramento**: O desempenho e a integridade de toda a solução são monitorados via CloudWatch.

Essa arquitetura baseada em serviços gerenciados da AWS proporciona uma solução robusta, escalável e eficiente, permitindo foco no desenvolvimento e melhoria contínua das funcionalidades do sistema.


{% endraw %}

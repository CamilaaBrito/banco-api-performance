# Testes de Performance com K6

## Introdução
Este projeto tem como objetivo realizar testes de performance utilizando JavaScript com a ferramenta K6 na API do sistema bancario desenvolvida pelo Julio de lima.

Os testes simulam cargas de usuários para avaliar o comportamento da aplicação em diferentes cenários, permitindo identificar gargalos, medir tempo de resposta e contribuindo com a estabilidade do sistema. Os testes são escritos com foco em modularidade, organização por contexto e reutilização de modelos de dados.

## Tecnologias Utilizadas
- JavaScript
- K6
- Variáveis de ambiente para configuração dinâmica (ex: `BASE_URL`).

## Estrutura do Repositório
```
banco-api-performance/
│
├── config/               # Arquivo de configuração de variáveis de ambiente
├── fixtures/             # Dados utilizados nos testes (payloads, massas de teste)
├── helpers/              # Funções auxiliares reutilizáveis para interação com a API
├── tests/                # Scripts de testes de performance
├── utils/                # Funções auxiliares reutilizáveis
└── README.md             # Documentação do projeto
```

## Objetivo de Cada Grupo de Arquivos

### tests/
Casos de teste organizado por mmódulo da API.

### Helpers/
Funções auxiliares reutilizáveis para interação com a API

### fixtures/
Dados de entrada utilizados nos testes.

### utils/
Funções auxiliares para reutilização de código.

### config/
Arquivo de configuração de variáveis de ambiente.

## Instalação

### 1. Clonar o repositório
```bash
git clone https://github.com/CamilaaBrito/banco-api-performance.git

```

### 2. Configure as variáveis de ambiente

Altere o arquivo  `config.local.json` e defina a URL base a ser testada:

```json
{
    "baseUrl":"http://localhost:3000"
}
```

Essas variáveis serão usadas dinamicamente
nos testes para montar as requisições.

### Execute um teste

```bash
k6 run tests/login.tests.js
```

Certifique-se de passar a variável de ambiente `BASE_URL`,
caso não esteja usando um `config.local.json` ou uma 
abordagem  de carregamento automático:

```bash
k6 run tests/login.tests.js -e  
BASE_URL=http//localhost:3000`
```

### Exportação de relatório HTML

```bash

K6_WEB_DASHBOARD=true \
K6_WEB_DASHBOARD_EXPORT=html-report.html \
k6 run tests/login.test.js
-e BASE_URL=http//localhost:3000
```
---

## Observações
- Certifique-se de que a API esteja acessível antes de executar os testes.
- Ajuste os cenários conforme a necessidade.

---

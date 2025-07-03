# ☕ Reusable CI/CD Pipeline para Projetos Java

[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=SEU_PROJETO_ID&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=SEU_PROJETO_ID)
[![Maintainability](https://sonarcloud.io/api/project_badges/measure?project=SEU_PROJETO_ID&metric=sqale_rating)](https://sonarcloud.io/summary/new_code?id=SEU_PROJETO_ID)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=SEU_PROJETO_ID&metric=security_rating)](https://sonarcloud.io/summary/new_code?id=SEU_PROJETO_ID)

---

## 📖 Sobre o Projeto

Este repositório foi criado com o objetivo de **explorar e estudar pipelines CI/CD reutilizáveis com foco em projetos Java**, utilizando **GitHub Actions** e o recurso de **composição de workflows (`workflow_call`)**.

> A ideia é centralizar uma esteira reutilizável que possa ser facilmente integrada a outros repositórios Java, garantindo padronização, agilidade e boas práticas como análise de qualidade com SonarQube.

---

## 🚧 Status do Projeto

📌 **Em desenvolvimento**  
Este repositório é um laboratório pessoal, criado com foco educacional e testes de esteiras Java utilizando boas práticas de automação contínua.

---

## ⚙️ Como Utilizar Esta Esteira Reutilizável

Para aplicar esta esteira CI/CD no seu repositório Java, siga os passos abaixo:

### 1. Estrutura Esperada
Certifique-se de que seu repositório tenha uma estrutura padrão de projeto Java (Maven ou Gradle).

### 2. Configurar o Secrets
Adicione no seu repositório os segredos necessários, por exemplo:

- `SONAR_TOKEN` → Token de autenticação do SonarQube

### 3. Chamar o Workflow Reutilizável
Crie um arquivo `ci.yml` dentro da pasta `.github/workflows` do seu projeto, com o seguinte conteúdo:

```yaml
name: CI Java com Pipeline Reutilizável

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  call-pipeline:
    uses: codenest/reusable-java-pipelines/.github/workflows/java-ci.yml@main
    secrets:
      SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}

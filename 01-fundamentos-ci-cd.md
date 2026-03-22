# 01 - Fundamentos de Integração e Entrega Contínua (CI/CD)

## 🎯 Objetivo
Compreender os conceitos fundamentais de Integração Contínua (CI), Entrega Contínua (CD) e Deploy, além de entender como esses conceitos se encaixam na cultura DevOps e na automação de software moderno.

---

## 📚 Conceitos-chave
- Integração Contínua (CI)
- Entrega Contínua (CD)
- Deploy Contínuo
- Pipeline
- Automação
- Feedback rápido
- Cultura DevOps
- Fluxo de desenvolvimento moderno
- Problemas do modelo tradicional
- Ciclo de entrega de software

---

## 🧠 Explicação

### 🔹 O que é CI (Integração Contínua)
Prática onde desenvolvedores integram código frequentemente em um repositório compartilhado, acionando builds e testes automáticos.

---

### 🔹 O que é CD (Entrega Contínua)
Extensão da CI onde o software está sempre pronto para ser entregue em produção de forma segura e automatizada.

---

### 🔹 Diferença entre CI, CD e Deploy Contínuo
- CI → Integração e testes automáticos  
- CD (Entrega Contínua) → Código pronto para produção  
- Deploy Contínuo → Publicação automática em produção  

---

### 🔹 Problemas que CI/CD resolve
- Integração tardia de código
- Bugs difíceis de rastrear
- Deploy manual e arriscado
- Baixa frequência de entrega

---

### 🔹 Cultura DevOps
Integra desenvolvimento e operações com foco em:
- Automação
- Colaboração
- Entregas rápidas
- Qualidade contínua

---

### 🔹 Fluxo tradicional vs moderno

Tradicional:
Dev → Teste → Deploy manual → Produção

Moderno (CI/CD):
Dev → Commit → Pipeline automático → Testes → Deploy

---

### 🔹 Feedback rápido
Erros são detectados rapidamente após o commit, reduzindo custo de correção.

---

### 🔹 Automação
Automatiza:
- Build
- Testes
- Deploy
- Validação

---

### 🔹 Conceito de Pipeline
Sequência automatizada de etapas que validam e entregam software.

Exemplo:
Build → Test → Deploy

---

### 🔹 Visão geral do curso
Este curso aborda:
- Versionamento
- Pipelines
- Testes
- Deploy
- DevOps
- Containers e Cloud

---

## 🔧 Ferramentas relacionadas
- Git
- GitHub / GitLab
- Jenkins
- GitHub Actions
- Docker
- Kubernetes

---

## 💻 Exemplo prático

Exemplo de pipeline simples (GitHub Actions):

name: CI Pipeline

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Install dependencies
        run: npm install
      - name: Run tests
        run: npm test

---

## ⚠️ Erros comuns
- Não rodar testes automaticamente
- Deploy manual sem validação
- Falta de versionamento
- Pipeline lento demais
- Falta de feedback rápido

---

## 📝 Resumo
- CI = integração automática
- CD = entrega pronta para produção
- Pipeline = automação do fluxo
- DevOps = cultura + automação
- Objetivo = entregar rápido e com qualidade

---

## 📖 Referências
- HUMBLE, J.; PRIKLADNICKI, R. Entrega Contínua. Bookman, 2013.  
- MUNIZ, A. et al. Jornada DevOps. Brasport, 2019.  
- SATO, D. DevOps na prática. Casa do Código, 2014.  
- SILVA, R. Entrega contínua em Android. Casa do Código, 2016.  

---

## 🚀 Desafio / Exercício
1. Crie um repositório no GitHub  
2. Configure um pipeline simples com GitHub Actions  
3. Adicione um teste automatizado  
4. Faça um commit e valide a execução do pipeline  
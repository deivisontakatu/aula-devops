# 04 - Pipelines CI/CD e Automação de Build/Deploy

## 🎯 Objetivo
Entender como funcionam pipelines de CI/CD, suas etapas, automação de build e deploy, além de aprender estratégias modernas de implantação e configuração dinâmica.

---

## 📚 Conceitos-chave
- Pipeline
- Estrutura de pipeline
- Estágios (build, test, deploy)
- Pipeline como código
- Qualidade no pipeline
- Gates de aprovação
- Paralelismo
- Fail fast
- Observabilidade
- Scripts de build
- Deploy automatizado
- Estratégias de deploy (Blue/Green, Canary)
- Parametrização de pipeline
- Variáveis de ambiente
- Configuração dinâmica

---

## 🧠 Explicação

### 🔹 O que é pipeline
Pipeline é uma sequência automatizada de etapas que transformam código em software pronto para produção.

---

### 🔹 Estrutura de pipeline
Pipeline geralmente é composto por:
- Build
- Test
- Deploy

---

### 🔹 Estágios (build/test/deploy)
- **Build** → compila e gera artefatos  
- **Test** → executa testes automatizados  
- **Deploy** → publica aplicação  

---

### 🔹 Pipeline como código
Pipeline definido em arquivos (ex: YAML), versionado junto com o código.

---

### 🔹 Qualidade no pipeline
Inclui:
- Testes automatizados
- Análise estática
- Cobertura de código

---

### 🔹 Gates de aprovação
Etapas que exigem aprovação manual antes de avançar (ex: produção).

---

### 🔹 Paralelismo
Executar tarefas simultaneamente para acelerar o pipeline.

---

### 🔹 Fail fast
Falhar rapidamente ao detectar erro para economizar tempo.

---

### 🔹 Observabilidade
Monitoramento do pipeline:
- Logs
- Métricas
- Status de execução

---

### 🔹 Scripts de build
Automatizam:
- Compilação
- Instalação de dependências
- Testes

---

### 🔹 Automatização de build
Executada automaticamente a cada commit.

---

### 🔹 Empacotamento (artefatos)
Gerar arquivos distribuíveis:
- .jar
- .zip
- Docker image

---

### 🔹 Deploy automatizado
Publicação automática em ambientes (dev, staging, produção).

---

### 🔹 Rollback
Voltar para versão anterior em caso de erro.

---

### 🔹 Blue/Green Deploy
Dois ambientes:
- Um ativo
- Um novo (troca rápida)

---

### 🔹 Canary Deploy
Liberação gradual para pequena parte dos usuários.

---

### 🔹 Shell scripts
Automação usando scripts bash.

---

### 🔹 Docker build
Criação de imagens containerizadas para padronizar ambientes.

---

### 🔹 Boas práticas de scripts
- Idempotência
- Simplicidade
- Logs claros
- Tratamento de erro

---

### 🔹 Parametrização de pipeline
Permite configurar comportamento do pipeline via parâmetros.

---

### 🔹 Variáveis de ambiente
Usadas para:
- Configurações
- Credenciais
- URLs

---

### 🔹 Configuração dinâmica
Pipeline se adapta conforme:
- Branch
- Ambiente
- Parâmetros

---

## 🔧 Ferramentas relacionadas
- GitHub Actions
- Jenkins
- GitLab CI/CD
- Docker
- Kubernetes
- Bash / Shell

---

## 💻 Exemplo prático

Exemplo de pipeline (GitHub Actions):

name: CI/CD Pipeline

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    env:
      NODE_ENV: production

    steps:
      - uses: actions/checkout@v3

      - name: Install dependencies
        run: npm install

      - name: Build
        run: npm run build

      - name: Test
        run: npm test

      - name: Build Docker image
        run: docker build -t app:latest .

---

## ⚠️ Erros comuns
- Pipeline lento
- Falta de testes automatizados
- Hardcode de configurações
- Falta de rollback
- Deploy manual
- Não usar variáveis de ambiente

---

## 📝 Resumo
- Pipeline automatiza build, teste e deploy
- Pipeline como código melhora rastreabilidade
- Fail fast e paralelismo aumentam eficiência
- Estratégias de deploy reduzem risco
- Variáveis e parâmetros tornam pipeline flexível

---

## 📖 Referências
- HUMBLE, J.; PRIKLADNICKI, R. Entrega Contínua. Bookman, 2013.  
- MUNIZ, A. et al. Jornada DevOps. Brasport, 2019.  
- SATO, D. DevOps na prática. Casa do Código, 2014.  
- PIRES, A.; MILITÃO, J. Integração Contínua com Jenkins. Casa do Código, 2019.  

---

## 🚀 Desafio / Exercício
1. Crie um pipeline no GitHub Actions ou Jenkins  
2. Adicione etapas de build, teste e deploy  
3. Use variáveis de ambiente  
4. Implemente build de imagem Docker  
5. Simule falha e implemente rollback  
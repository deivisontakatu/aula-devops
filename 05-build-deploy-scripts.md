# 05 - Build e Deploy Automatizado

## 🎯 Objetivo
Compreender como automatizar processos de build e deploy, empacotar aplicações e aplicar estratégias modernas de implantação para garantir entregas seguras e eficientes.

---

## 📚 Conceitos-chave
- Scripts de build
- Automatização de build
- Empacotamento (artefatos)
- Deploy automatizado
- Rollback
- Blue/Green deploy
- Canary deploy
- Shell scripts
- Docker build
- Boas práticas de scripts

---

## 🧠 Explicação

### 🔹 Scripts de build
Scripts que automatizam tarefas como:
- Compilação
- Instalação de dependências
- Execução de testes

---

### 🔹 Automatização de build
Processo de executar builds automaticamente após eventos (ex: commit).

---

### 🔹 Empacotamento (artefatos)
Geração de arquivos prontos para distribuição:
- .jar (Java)
- .zip
- Docker images

---

### 🔹 Deploy automatizado
Processo de enviar aplicação para ambiente automaticamente, sem intervenção manual.

---

### 🔹 Rollback
Permite retornar a uma versão anterior em caso de falha.

---

### 🔹 Blue/Green Deploy
Dois ambientes:
- Um em produção
- Outro com nova versão

Troca rápida sem downtime.

---

### 🔹 Canary Deploy
Liberação gradual da nova versão para uma pequena parte dos usuários.

---

### 🔹 Shell scripts
Automação usando scripts bash para executar tarefas repetitivas.

---

### 🔹 Docker build
Criação de imagens containerizadas:

- Padroniza ambientes
- Facilita deploy
- Garante consistência

---

### 🔹 Boas práticas de scripts
- Scripts idempotentes
- Logs claros
- Tratamento de erros
- Evitar hardcode
- Reutilização

---

## 🔧 Ferramentas relacionadas
- Bash / Shell
- Docker
- Jenkins
- GitHub Actions
- GitLab CI/CD
- Kubernetes

---

## 💻 Exemplo prático

Exemplo de script de build (bash):

#!/bin/bash

echo "Instalando dependências..."
npm install

echo "Executando testes..."
npm test

echo "Gerando build..."
npm run build

---

Exemplo de Dockerfile:

FROM node:18

WORKDIR /app
COPY . .

RUN npm install
RUN npm run build

CMD ["npm", "start"]

---

## ⚠️ Erros comuns
- Deploy manual
- Falta de rollback
- Scripts sem tratamento de erro
- Configurações hardcoded
- Builds inconsistentes

---

## 📝 Resumo
- Build automatizado garante consistência
- Artefatos representam versões do sistema
- Deploy automatizado reduz erros humanos
- Estratégias como Blue/Green e Canary reduzem risco
- Docker padroniza ambientes

---

## 📖 Referências
- HUMBLE, J.; PRIKLADNICKI, R. Entrega Contínua. Bookman, 2013.  
- MUNIZ, A. et al. Jornada DevOps. Brasport, 2019.  
- SATO, D. DevOps na prática. Casa do Código, 2014.  
- VITALINO, J. F. N.; CASTRO, M. A. N. Descomplicando o Docker. Brasport, 2018.  

---

## 🚀 Desafio / Exercício
1. Crie um script de build para um projeto (Node, Java ou Python)  
2. Gere um artefato da aplicação  
3. Crie um Dockerfile para a aplicação  
4. Execute o build da imagem Docker  
5. Simule um deploy e implemente rollback  
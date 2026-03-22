# 07 - Gerenciamento de Dependências, Containers e Dados

## 🎯 Objetivo
Compreender como gerenciar dependências de software, garantir segurança e versionamento, além de trabalhar com containers e controle de dados em diferentes ambientes.

---

## 📚 Conceitos-chave
- Gerenciamento de dependências
- Package managers (npm, pip, maven)
- Versionamento de bibliotecas
- Segurança de dependências
- Containers (Docker)
- Imagens e registries
- Gerência de dados
- Migração de banco de dados
- Seeds e fixtures
- Configuração por ambiente

---

## 🧠 Explicação

### 🔹 Gerenciamento de dependências
Controle das bibliotecas e pacotes que o sistema utiliza.

Objetivo:
- Garantir compatibilidade
- Evitar conflitos
- Facilitar manutenção

---

### 🔹 Package managers (npm, pip, maven)
Ferramentas que gerenciam dependências:

- **npm** → JavaScript  
- **pip** → Python  
- **maven** → Java  

---

### 🔹 Versionamento de libs
Controle de versões das dependências.

Exemplo:
- ^1.2.0 → aceita atualizações compatíveis  
- 1.2.3 → versão fixa  

---

### 🔹 Segurança de dependências
Análise de vulnerabilidades em bibliotecas externas.

Práticas:
- Atualizar dependências
- Usar scanners de segurança
- Evitar pacotes desconhecidos

---

### 🔹 Containers (Docker)
Tecnologia que empacota aplicação + dependências em ambiente isolado.

Benefícios:
- Portabilidade
- Consistência
- Facilidade de deploy

---

### 🔹 Imagens e registries
- **Imagem** → snapshot da aplicação  
- **Registry** → local de armazenamento (Docker Hub, ECR)

---

### 🔹 Gerência de dados
Controle de dados da aplicação ao longo do tempo.

---

### 🔹 Migração de banco
Atualização estruturada do banco de dados.

Exemplo:
- Criar tabela
- Alterar coluna
- Inserir dados

---

### 🔹 Seeds e fixtures
- **Seeds** → dados iniciais  
- **Fixtures** → dados para testes  

---

### 🔹 Configuração por ambiente
Definir configurações específicas para:
- Dev
- Homologação
- Produção

Exemplo:
- URLs
- Credenciais
- Banco de dados

---

## 🔧 Ferramentas relacionadas
- npm
- pip
- Maven
- Docker
- Docker Hub
- PostgreSQL / MySQL
- Flyway / Liquibase

---

## 💻 Exemplo prático

Exemplo de package.json (Node.js):

{
  "dependencies": {
    "express": "^4.18.2"
  }
}

---

Exemplo de Dockerfile:

FROM node:18

WORKDIR /app
COPY . .

RUN npm install

CMD ["npm", "start"]

---

Exemplo de variável de ambiente:

export DB_HOST=localhost

---

## ⚠️ Erros comuns
- Não versionar dependências corretamente
- Ignorar vulnerabilidades
- Ambientes inconsistentes
- Não usar containers
- Alterar banco sem controle de migração

---

## 📝 Resumo
- Dependências devem ser gerenciadas e versionadas
- Package managers automatizam esse processo
- Containers garantem consistência
- Dados precisam de controle (migração + seeds)
- Configuração varia por ambiente

---

## 📖 Referências
- HUMBLE, J.; PRIKLADNICKI, R. Entrega Contínua. Bookman, 2013.  
- MUNIZ, A. et al. Jornada DevOps. Brasport, 2019.  
- SATO, D. DevOps na prática. Casa do Código, 2014.  
- VITALINO, J. F. N.; CASTRO, M. A. N. Descomplicando o Docker. Brasport, 2018.  

---

## 🚀 Desafio / Exercício
1. Crie um projeto usando npm, pip ou maven  
2. Adicione e versione dependências  
3. Crie um Dockerfile para a aplicação  
4. Execute a aplicação em container  
5. Simule migração de banco e adicione dados iniciais  
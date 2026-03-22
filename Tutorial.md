# 🚀 Tutorial Completo DevOps (Projeto do Zero)

## 📺 Fonte

https://www.youtube.com/watch?v=PrAPwkxpbWM

---

## 🧱 Visão Geral do Projeto

Você vai montar um sistema completo com:

1. Código simples (Node.js)
2. Versionamento com Git
3. Repositório no GitHub
4. Pipeline com GitHub Actions
5. Build com Docker
6. Deploy na AWS
7. Infraestrutura com Terraform
8. Configuração com Ansible
9. Orquestração com Kubernetes
10. Monitoramento com Grafana

👉 Um mini ambiente DevOps real

---

## 🧪 Parte 1 — Criando o Projeto

### Instalar ferramentas

Para começar, você precisa instalar as ferramentas essenciais no seu sistema:

- **Git**: Ferramenta de controle de versão para rastrear mudanças no código. Baixe e instale em: https://git-scm.com/downloads
- **Node.js**: Ambiente de execução JavaScript necessário para rodar o aplicativo. Baixe a versão LTS em: https://nodejs.org
- **Docker**: Plataforma para containerização de aplicações. Baixe o Docker Desktop em: https://www.docker.com/products/docker-desktop

Certifique-se de que todas as ferramentas estejam instaladas e funcionando corretamente antes de prosseguir.

### Criar projeto

1. Abra o terminal ou prompt de comando e navegue para o diretório onde deseja criar o projeto.

2. Crie uma nova pasta para o projeto e entre nela:

   ```bash
   mkdir devops-project
   cd devops-project
   ```

   Isso cria um diretório chamado `devops-project` e muda para ele.

3. Inicialize um novo projeto Node.js com configurações padrão:

   ```bash
   npm init -y
   ```

   Este comando cria um arquivo `package.json` com metadados do projeto, como nome, versão e dependências.

4. Crie o arquivo principal da aplicação, `index.js`, com o seguinte código:

   ```javascript
   const http = require('http');

   http.createServer((req, res) => {
     res.end("Hello DevOps 🚀");
   }).listen(3000);
   ```

   Este código cria um servidor HTTP simples usando o módulo nativo `http` do Node.js. Ele escuta na porta 3000 e responde a todas as requisições com a mensagem "Hello DevOps 🚀".

5. Teste a aplicação localmente executando:

   ```bash
   node index.js
   ```

   Abra um navegador e acesse http://localhost:3000 para verificar se a aplicação está funcionando. Você deve ver a mensagem de boas-vindas.

---

## 🔁 Parte 2 — Git e GitHub

### Criar conta no GitHub

1. Acesse o site do GitHub em: https://github.com
2. Clique no botão "Sign up" para criar uma nova conta.
3. Siga os passos para verificar seu e-mail e configurar a conta. Use uma conta gratuita para este tutorial.

### Criar repositório

1. Após fazer login no GitHub, clique no botão "+" no canto superior direito e selecione "New repository".
2. Dê o nome `devops-project` ao repositório.
3. Adicione uma descrição opcional, como "Projeto DevOps do Zero".
4. Deixe as outras configurações como padrão (público, sem README inicial, etc.).
5. Clique em "Create repository" para finalizar.

### Conectar projeto ao GitHub

1. No terminal, dentro da pasta `devops-project`, inicialize um repositório Git local:

   ```bash
   git init
   ```

   Isso cria um repositório Git vazio no diretório atual.

2. Adicione todos os arquivos do projeto ao staging area:

   ```bash
   git add .
   ```

   O ponto (.) adiciona todos os arquivos e pastas no diretório atual.

3. Faça o primeiro commit com uma mensagem descritiva:

   ```bash
   git commit -m "feat: projeto inicial"
   ```

   Um commit salva as mudanças no repositório local.

4. Renomeie a branch padrão para `main` (padrão moderno do Git):

   ```bash
   git branch -M main
   ```

5. Adicione o repositório GitHub como remoto (substitua `SEU_USUARIO` pelo seu nome de usuário no GitHub):

   ```bash
   git remote add origin https://github.com/SEU_USUARIO/devops-project.git
   ```

6. Envie o código para o repositório remoto:

   ```bash
   git push -u origin main
   ```

   O `-u` define a branch `main` como upstream, facilitando pushes futuros.

---

## ⚙️ Parte 3 — Pipeline (GitHub Actions)

Configure uma pipeline de Integração Contínua (CI) usando GitHub Actions para automatizar testes e builds.

1. Crie a estrutura de pastas necessária para workflows:

   ```bash
   mkdir -p .github/workflows
   ```

2. Crie um novo arquivo chamado `ci.yml` dentro de `.github/workflows` com o seguinte conteúdo:

   ```yaml
   name: CI Pipeline

   on: [push]

   jobs:
     build:
       runs-on: ubuntu-latest

       steps:
         - uses: actions/checkout@v3
         - name: Install dependencies
           run: npm install
         - name: Run app
           run: node index.js
   ```

   - `name`: Nome da pipeline.
   - `on`: Gatilho para executar (a cada push).
   - `jobs.build`: Define um job chamado "build" que roda em Ubuntu.
   - `steps`: Passos sequenciais: checkout do código, instalação de dependências e execução do app.

3. Adicione, commite e envie as mudanças para o GitHub:

   ```bash
   git add .
   git commit -m "feat: adicionar pipeline CI com GitHub Actions"
   git push
   ```

   A pipeline será executada automaticamente no GitHub após o push.

---

## 🐳 Parte 4 — Docker

Containerize a aplicação para facilitar o deploy e isolamento.

1. Crie um arquivo chamado `Dockerfile` na raiz do projeto com o seguinte conteúdo:

   ```dockerfile
   FROM node:18

   WORKDIR /app
   COPY . .

   RUN npm install

   CMD ["node", "index.js"]
   ```

   - `FROM`: Baseia a imagem no Node.js 18.
   - `WORKDIR`: Define o diretório de trabalho dentro do container.
   - `COPY`: Copia os arquivos do projeto para o container.
   - `RUN`: Instala as dependências.
   - `CMD`: Comando para executar a aplicação.

2. Construa a imagem Docker:

   ```bash
   docker build -t devops-app .
   ```

   Isso cria uma imagem chamada `devops-app` baseada no Dockerfile.

3. Execute o container mapeando a porta 3000:

   ```bash
   docker run -p 3000:3000 devops-app
   ```

   O `-p` mapeia a porta do host para o container.

4. Verifique acessando http://localhost:3000 no navegador.

---

## ☁️ Parte 5 — AWS

Configure um servidor na nuvem usando Amazon Web Services (AWS).

1. Crie uma conta gratuita em: https://aws.amazon.com
2. Faça login no Console da AWS.
3. Navegue para o serviço EC2 (Elastic Compute Cloud).
4. Clique em "Launch Instance" para criar uma nova instância.
5. Selecione uma AMI (Amazon Machine Image) baseada em Ubuntu.
6. Configure o tipo de instância (ex: t2.micro para free tier).
7. Baixe o arquivo de chave privada (.pem) para acesso SSH.
8. Lance a instância e aguarde até que esteja rodando.
9. Anote o endereço IP público da instância.
10. Conecte-se via SSH (substitua `sua-chave.pem` e `IP_DA_MAQUINA`):

    ```bash
    ssh -i sua-chave.pem ubuntu@IP_DA_MAQUINA
    ```

    Agora você tem acesso ao servidor Ubuntu na AWS.

---

## 🏗️ Parte 6 — Terraform

Use Terraform para provisionar infraestrutura como código.

1. Baixe e instale o Terraform em: https://developer.hashicorp.com/terraform/downloads
2. Crie um arquivo `main.tf` na raiz do projeto com o seguinte código HCL (HashiCorp Configuration Language):

   ```hcl
   provider "aws" {
     region = "us-east-1"
   }

   resource "aws_instance" "example" {
     ami           = "ami-123456"
     instance_type = "t2.micro"
   }
   ```

   - `provider`: Define o provedor de nuvem (AWS) e região.
   - `resource`: Cria uma instância EC2 com AMI e tipo especificados.

3. Inicialize o Terraform no diretório:

   ```bash
   terraform init
   ```

   Isso baixa os plugins necessários.

4. Planeje e aplique as mudanças:

   ```bash
   terraform plan
   terraform apply
   ```

   Confirme a aplicação quando solicitado. Isso criará a instância na AWS.

---

## ⚙️ Parte 7 — Ansible

Automatize a configuração de servidores com Ansible.

1. Instale o Ansible no seu sistema (ou na instância AWS):

   ```bash
   sudo apt update
   sudo apt install ansible
   ```

2. Crie um arquivo `playbook.yml` com o seguinte conteúdo:

   ```yaml
   - hosts: all
     tasks:
       - name: Instalar Docker
         apt:
           name: docker.io
           state: present
   ```

   Este playbook instala o Docker em todos os hosts alvo.

3. Execute o playbook (configure o inventário se necessário):

   ```bash
   ansible-playbook playbook.yml
   ```

---

## ☸️ Parte 8 — Kubernetes

Orquestre containers com Kubernetes para escalabilidade.

1. Instale o Minikube para um cluster local: https://minikube.sigs.k8s.io/docs/start/
2. Inicie o Minikube:

   ```bash
   minikube start
   ```

3. Crie um arquivo `deployment.yaml` para o deployment:

   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: devops-app

   spec:
     replicas: 2
     selector:
       matchLabels:
         app: devops

     template:
       metadata:
         labels:
           app: devops

     spec:
       containers:
       - name: app
         image: devops-app
         ports:
         - containerPort: 3000
   ```

   - Define um deployment com 2 réplicas do container `devops-app`.

4. Aplique o deployment no cluster:

   ```bash
   kubectl apply -f deployment.yaml
   ```

5. Verifique os pods:

   ```bash
   kubectl get pods
   ```

---

## 📊 Parte 9 — Monitoramento (Grafana)

Configure monitoramento com Grafana para visualizar métricas.

1. Execute o Grafana em um container Docker:

   ```bash
   docker run -d -p 3000:3000 grafana/grafana
   ```

   O `-d` roda em background, `-p` mapeia a porta.

2. Acesse http://localhost:3000 no navegador.
3. Faça login com usuário `admin` e senha `admin`.
4. Configure dashboards e fontes de dados conforme necessário.

---

## 🔗 Integração das Ferramentas

| Etapa          | Ferramenta       | Descrição |
|----------------|------------------|-----------|
| Código         | Git + GitHub    | Versionamento e colaboração |
| CI/CD          | GitHub Actions  | Automação de builds e testes |
| Build          | Docker          | Containerização da aplicação |
| Infraestrutura | Terraform       | Provisionamento de infraestrutura |
| Configuração   | Ansible         | Automação de configuração de servidores |
| Deploy         | Kubernetes      | Orquestração de containers |
| Monitoramento  | Grafana         | Visualização de métricas e logs |
| Cloud          | AWS             | Plataforma de nuvem para hospedagem |

---

## 🧠 Resultado Final

Ao completar todas as etapas, você terá um ambiente DevOps completo com:

- **Código versionado**: Gerenciado com Git e hospedado no GitHub
- **Pipeline automático**: CI/CD com GitHub Actions para builds contínuos
- **Container rodando**: Aplicação isolada em Docker
- **Infra criada como código**: Servidores provisionados via Terraform
- **Deploy automatizado**: Aplicação orquestrada com Kubernetes
- **Monitoramento ativo**: Métricas visualizadas no Grafana

Este setup simula um ambiente de produção real, demonstrando as práticas essenciais do DevOps.
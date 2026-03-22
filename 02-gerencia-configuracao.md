# 02 - Gerência de Configuração

## 🎯 Objetivo
Entender os conceitos de gerência de configuração, controle de mudanças e rastreabilidade, além de aprender como gerenciar ambientes, infraestrutura e artefatos de software de forma controlada e automatizada.

---

## 📚 Conceitos-chave
- Gerência de Configuração
- Versionamento de artefatos
- Ambientes (dev, homologação, produção)
- Infraestrutura como Código (IaC)
- Controle de mudanças
- Baselines
- Auditoria
- Rastreabilidade
- Configuração vs código
- Automação de infraestrutura

---

## 🧠 Explicação

### 🔹 O que é Gerência de Configuração
Conjunto de práticas para controlar e gerenciar mudanças em software e seus componentes ao longo do tempo.

---

### 🔹 Versionamento de artefatos
Além do código, também versionamos:
- Binários
- Imagens Docker
- Pacotes
- Configurações

---

### 🔹 Ambientes (dev/homolog/prod)
- **Dev** → desenvolvimento  
- **Homologação** → testes e validação  
- **Produção** → ambiente final  

Cada ambiente deve ser consistente e controlado.

---

### 🔹 Infraestrutura como Código (IaC)
Infraestrutura definida por código, permitindo automação e reprodutibilidade.

Exemplo:
- Criar servidores automaticamente
- Configurar redes e serviços

---

### 🔹 Controle de mudanças
Processo para garantir que mudanças sejam:
- Registradas
- Revisadas
- Aprovadas

---

### 🔹 Baselines
Versões estáveis de um sistema que servem como referência para futuras mudanças.

---

### 🔹 Auditoria
Permite rastrear:
- Quem fez a mudança
- Quando ocorreu
- O que foi alterado

---

### 🔹 Rastreabilidade
Capacidade de ligar:
Requisito → Código → Teste → Deploy

---

### 🔹 Configuração vs Código
- Código → lógica da aplicação  
- Configuração → parâmetros (ex: URL, banco, credenciais)

Boas práticas:
- Não misturar config com código
- Usar variáveis de ambiente

---

### 🔹 Ferramentas (Ansible, Terraform)
Ferramentas que automatizam infraestrutura e configuração:
- Provisionamento
- Configuração de servidores
- Deploy de ambientes

---

## 🔧 Ferramentas relacionadas
- Ansible
- Terraform
- Docker
- Kubernetes
- AWS CloudFormation
- Azure ARM

---

## 💻 Exemplo prático

Exemplo simples com Terraform:

provider "aws" {
  region = "us-east-1"
}

resource "aws_instance" "example" {
  ami           = "ami-123456"
  instance_type = "t2.micro"
}

---

## ⚠️ Erros comuns
- Não versionar configurações
- Configurações diferentes entre ambientes
- Alterações manuais em produção
- Falta de rastreabilidade
- Misturar configuração com código

---

## 📝 Resumo
- Gerência de configuração controla mudanças
- IaC permite automação de infraestrutura
- Ambientes devem ser padronizados
- Rastreabilidade garante controle
- Baselines definem versões estáveis

---

## 📖 Referências
- HUMBLE, J.; PRIKLADNICKI, R. Entrega Contínua. Bookman, 2013.  
- MUNIZ, A. et al. Jornada DevOps. Brasport, 2019.  
- SATO, D. DevOps na prática. Casa do Código, 2014.  
- MORAES, G. Caixa de Ferramentas DevOps. Casa do Código, 2015.  

---

## 🚀 Desafio / Exercício
1. Instale o Terraform  
2. Crie um script para provisionar uma máquina virtual  
3. Versione esse script no Git  
4. Simule alteração de configuração e registre a mudança  
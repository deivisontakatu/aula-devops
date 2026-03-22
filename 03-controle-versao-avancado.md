# 03 - Controle de Versão Avançado

## 🎯 Objetivo
Dominar o uso avançado de controle de versão com Git, incluindo estratégias de branching, versionamento, colaboração em equipe e boas práticas para manter histórico limpo e rastreável.

---

## 📚 Conceitos-chave
- Git básico
- Branching strategies (Git Flow, Trunk Based)
- Merge vs Rebase
- Pull Requests
- Code Review
- Tags e Releases
- Versionamento semântico
- Hooks (pre-commit, commit-msg)
- Monorepo vs Multirepo
- Fluxo de commit
- Conventional Commits
- Ferramentas de versionamento

---

## 🧠 Explicação

### 🔹 Git básico (rápido)
Sistema de controle de versão distribuído que permite rastrear mudanças no código.

---

### 🔹 Fluxo de commit (add → commit → push)
- `git add` → adiciona mudanças  
- `git commit` → registra mudanças  
- `git push` → envia para o repositório remoto  

---

### 🔹 Branching strategies
- **Git Flow** → múltiplas branches (feature, develop, release, main)  
- **Trunk Based** → commits frequentes na branch principal  

---

### 🔹 Merge vs Rebase
- **Merge** → mantém histórico completo  
- **Rebase** → histórico linear e limpo  

---

### 🔹 Pull Requests (PR)
Forma de propor mudanças antes de integrar ao código principal.

---

### 🔹 Code Review
Revisão de código para garantir:
- Qualidade
- Padrões
- Segurança

---

### 🔹 Tags e Releases
- Tags marcam versões específicas  
- Releases representam versões distribuídas  

---

### 🔹 Versionamento semântico (SemVer)
Formato: MAJOR.MINOR.PATCH  
Exemplo: 1.2.3

- MAJOR → quebra compatibilidade  
- MINOR → nova funcionalidade  
- PATCH → correção  

---

### 🔹 Conventional Commits / Commit semântico
Padronização de mensagens de commit:

Exemplo:
feat: adiciona login  
fix: corrige bug no cadastro  

---

### 🔹 Hooks (pre-commit, commit-msg)
Scripts que rodam automaticamente:
- Validar código
- Rodar testes
- Validar mensagem de commit

---

### 🔹 Monorepo vs Multirepo
- **Monorepo** → um único repositório para vários projetos  
- **Multirepo** → vários repositórios separados  

---

### 🔹 Boas práticas Git
- Commits pequenos
- Mensagens claras
- Uso de branches
- Revisão antes de merge

---

### 🔹 Ferramentas de versionamento
- Git (principal)
- Plataformas de hospedagem e colaboração

---

### 🔹 GitHub vs GitLab vs Bitbucket

- **GitHub** → popular, integração com Actions  
- **GitLab** → CI/CD integrado  
- **Bitbucket** → integração com Jira  

---

## 🔧 Ferramentas relacionadas
- Git
- GitHub
- GitLab
- Bitbucket
- Husky (hooks)
- Commitlint

---

## 💻 Exemplo prático

Fluxo básico:

git init
git add .
git commit -m "feat: adiciona funcionalidade X"
git push origin main

Exemplo de commit semântico:

git commit -m "fix: corrige erro de autenticação"

---

## ⚠️ Erros comuns
- Commits grandes demais
- Mensagens vagas (ex: "update")
- Trabalhar direto na main
- Não usar branches
- Não revisar código
- Uso incorreto de rebase

---

## 📝 Resumo
- Git controla versões de código
- Branches organizam o desenvolvimento
- PR + Code Review garantem qualidade
- SemVer padroniza versões
- Conventional commits padronizam histórico

---

## 📖 Referências
- HUMBLE, J.; PRIKLADNICKI, R. Entrega Contínua. Bookman, 2013.  
- MUNIZ, A. et al. Jornada DevOps. Brasport, 2019.  
- SATO, D. DevOps na prática. Casa do Código, 2014.  
- SILVERMAN, R. E. Git: guia prático. Novatec, 2019.  

---

## 🚀 Desafio / Exercício
1. Crie um repositório Git  
2. Implemente Git Flow ou Trunk Based  
3. Faça commits usando Conventional Commits  
4. Crie uma branch feature e abra um Pull Request  
5. Adicione um hook para validar commits  
# 06 - Testes e Qualidade de Software

## 🎯 Objetivo
Compreender os diferentes tipos de testes de software, sua automação e integração em pipelines CI/CD, além de garantir qualidade de código e confiabilidade na entrega de aplicações.

---

## 📚 Conceitos-chave
- Tipos de testes
- Testes automatizados
- Testes unitários
- Testes de integração
- Testes E2E (end-to-end)
- Cobertura de código
- Qualidade de código
- Testes no pipeline
- TDD (Test Driven Development)
- BDD (Behavior Driven Development)
- Estratégias de teste

---

## 🧠 Explicação

### 🔹 Tipos de testes
Testes garantem que o sistema funciona corretamente em diferentes níveis:
- Unitário
- Integração
- Sistema
- E2E

---

### 🔹 Testes automatizados
Execução automática de testes sem intervenção manual, essencial para CI/CD.

---

### 🔹 Testes unitários
Testam partes isoladas do código (funções, métodos).

Objetivo:
- Validar lógica individual
- Detectar erros rapidamente

---

### 🔹 Testes de integração
Verificam a interação entre componentes (ex: API + banco de dados).

---

### 🔹 Testes E2E (End-to-End)
Testam o sistema completo simulando o comportamento do usuário.

---

### 🔹 Cobertura de código
Mede quanto do código foi testado.

Exemplo:
- 80% de cobertura → 80% do código executado em testes

---

### 🔹 Qualidade de código (SonarQube)
Ferramentas analisam:
- Bugs
- Vulnerabilidades
- Code smells
- Complexidade

---

### 🔹 Testes no pipeline
Testes são executados automaticamente no pipeline CI/CD:
- Após commit
- Antes de deploy

---

### 🔹 TDD (Test Driven Development)
Fluxo:
1. Escreve teste  
2. Escreve código  
3. Refatora  

---

### 🔹 BDD (Behavior Driven Development)
Foco no comportamento do sistema, usando linguagem próxima do negócio.

Exemplo:
Given / When / Then

---

### 🔹 Estratégias de teste
- Pirâmide de testes (mais unitários, menos E2E)
- Testes rápidos primeiro
- Automação sempre que possível

---

## 🔧 Ferramentas relacionadas
- Jest
- JUnit
- Cypress
- Selenium
- SonarQube
- Mocha / Chai

---

## 💻 Exemplo prático

Exemplo de teste unitário (JavaScript com Jest):

test('soma dois números', () => {
  expect(1 + 2).toBe(3);
});

---

Exemplo simples de pipeline com testes:

- name: Run tests
  run: npm test

---

## ⚠️ Erros comuns
- Não automatizar testes
- Baixa cobertura de código
- Testes lentos
- Depender apenas de testes manuais
- Não rodar testes no pipeline

---

## 📝 Resumo
- Testes garantem qualidade e confiabilidade
- Tipos: unitário, integração, E2E
- Automação é essencial em CI/CD
- TDD melhora qualidade do código
- Cobertura indica nível de teste

---

## 📖 Referências
- HUMBLE, J.; PRIKLADNICKI, R. Entrega Contínua. Bookman, 2013.  
- MUNIZ, A. et al. Jornada DevOps. Brasport, 2019.  
- SATO, D. DevOps na prática. Casa do Código, 2014.  

---

## 🚀 Desafio / Exercício
1. Crie testes unitários para uma função simples  
2. Adicione testes de integração  
3. Configure execução automática no pipeline  
4. Meça a cobertura de código  
5. Configure análise com SonarQube  
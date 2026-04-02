# ⚙️ Guia Completo — DevOps e Entrega Contínua

---
## 📌 1. Integração Contínua e Entrega Contínua (CI/CD)

CI/CD são práticas do DevOps que automatizam o desenvolvimento, testes e deploy, aumentando qualidade e velocidade.

---

## 🔄 Integração Contínua (CI)

Integra o código frequentemente ao repositório, executando testes automáticos para validar mudanças.

### ⚙️ Fluxo:
1. Commit no Git  
2. Pipeline inicia automaticamente  
3. Instala dependências  
4. Executa testes e valida build  

### 💻 Exemplo (GitHub Actions)
```yaml
name: CI
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: npm install
      - run: npm test
```

### ✅ Benefícios
- Detecta erros rapidamente  
- Código sempre validado e integrado  

---

## 🚀 Entrega Contínua (CD)

Automatiza build e deploy, garantindo que o sistema esteja pronto para produção a qualquer momento.

### 🔄 Fluxo:
1. Código aprovado na CI  
2. Build da aplicação  
3. Deploy em ambiente  

### 💻 Exemplo
```bash
docker build -t app .
docker run -d -p 80:3000 app
```

---

## 🧪 Ambientes
- Dev → desenvolvimento local  
- Teste → validação funcional  
- Prod → uso real pelos usuários  

---

## ⚠️ Boas Práticas
- Automatizar testes e builds  
- Usar versionamento (Git)  
- Monitorar falhas de deploy  

---

## ✅ Resumo
CI = integração + testes automáticos  
CD = entrega + deploy contínuo  
Automação melhora qualidade e reduz erros  

---

## 📌 2. Gerência de Configuração, Dados e Dependências

A gerência de configuração garante organização, controle e consistência dos elementos do sistema ao longo do desenvolvimento.

---

## ⚙️ Gerência de Configuração

Controla versões e mudanças no sistema.

### 🔧 Práticas:
- Uso de Git (versionamento de código)  
- Padronização de ambientes (dev, teste, prod)  
- Rastreabilidade de alterações (histórico de commits)  

### 💻 Exemplo
```bash
git commit -m "feat: adiciona login"
git push origin main
```

---

## 💾 Gerência de Dados

Controla dados e estrutura do banco.

### 🔧 Práticas:
- Versionamento de banco (migrations)  
- Backup periódico  
- Garantia de integridade dos dados  

### 💻 Exemplo (Migration)
```sql
ALTER TABLE usuarios ADD email VARCHAR(100);
```

---

## 📦 Gerenciamento de Dependências

Controla bibliotecas e frameworks utilizados.

### 🔧 Práticas:
- Uso de arquivos como `package.json` ou `requirements.txt`  
- Evitar conflitos de versões  
- Garantir ambiente reproduzível  

### 💻 Exemplo
```json
"dependencies": {
  "express": "^4.18.0"
}
```

---

## ⚠️ Boas Práticas

- Versionar tudo (código, banco, configs)  
- Usar arquivos de lock (`package-lock.json`)  
- Automatizar instalação de dependências  
- Documentar o ambiente  

---

## ✅ Resumo

Configuração = controle e organização do sistema  
Dados = integridade e versionamento  
Dependências = bibliotecas necessárias para execução  

---

## 📌 3. Ferramentas de DevOps e Versionamento

As ferramentas de DevOps e versionamento automatizam processos, melhoram a qualidade e facilitam a colaboração no desenvolvimento de software.

---

## 🛠️ Ferramentas de CI/CD

Responsáveis por automatizar build, testes e deploy.

### 🔧 Exemplos:
- Jenkins → ferramenta tradicional e altamente configurável  
- GitHub Actions → integrada ao GitHub  
- GitLab CI → integrada ao GitLab  

### 💻 Exemplo (GitHub Actions)
```yaml
name: CI
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: npm install
```

---

## 🧾 Ferramentas de Versionamento

Controlam versões do código e histórico de mudanças.

### 🔧 Exemplos:
- Git → sistema de versionamento distribuído  
- GitHub / GitLab / Bitbucket → plataformas de hospedagem de código  

### 💻 Exemplo (Git)
```bash
git init
git add .
git commit -m "inicial"
git push
```

---

## 🤝 Colaboração

Essas ferramentas permitem:
- Trabalho em equipe (branches, pull requests)  
- Revisão de código  
- Controle de mudanças  

---

## 🎯 Objetivos

- Automatizar processos de desenvolvimento  
- Garantir qualidade do software  
- Facilitar colaboração entre equipes  

---

## ⚠️ Boas Práticas

- Usar branches (main, develop, feature)  
- Fazer commits frequentes  
- Revisar código antes de integrar  
- Integrar CI/CD ao repositório  

---

## ✅ Resumo

Git = versionamento e histórico  
CI/CD = automação de build, testes e deploy  
Ferramentas DevOps = mais produtividade e qualidade  

---

## 📌 4. Pipeline de Desenvolvimento

O pipeline é o fluxo automatizado que o código percorre desde o desenvolvimento até a produção, garantindo qualidade e rapidez.

---

## 🔄 Etapas do Pipeline

1. Commit do código → envio para repositório (Git)  
2. Build → compilação ou empacotamento  
3. Testes automatizados → validação do sistema  
4. Análise de qualidade → lint, cobertura, segurança  
5. Deploy → publicação em ambiente  

---

## ⚙️ Exemplo de Pipeline (CI/CD)

```yaml
name: Pipeline
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - run: npm install
      - run: npm test
```

---

## 🎯 Funções do Pipeline

- Construção automática da aplicação  
- Verificação da qualidade do código  
- Validação de requisitos antes do deploy  
- Redução de erros humanos  

---

## 🧪 Etapas Detalhadas

- Build → gera artefato (ex: aplicação ou imagem Docker)  
- Testes → garantem funcionamento correto  
- Qualidade → análise estática (lint, segurança)  
- Deploy → entrega em dev, teste ou produção  

---

## ⚠️ Boas Práticas

- Automatizar todas as etapas  
- Falhar rápido em caso de erro  
- Monitorar execução do pipeline  
- Manter pipelines versionados  

---

## 🚀 Benefícios

- Entregas mais rápidas  
- Maior confiabilidade  
- Padronização do processo  

---

## ✅ Resumo

Pipeline = fluxo automatizado do software  
Integra CI/CD em etapas contínuas  
Garante qualidade, validação e entrega eficiente  

---

## 📌 5. Scripts de Build e Deploy

Scripts automatizam tarefas repetitivas no desenvolvimento, garantindo consistência e agilidade no processo.

---

## ⚙️ Scripts de Build (Compilação)

Responsáveis por preparar a aplicação para execução.

### 🔧 Funções:
- Compilar código (quando necessário)  
- Gerar artefatos (ex: arquivos `.jar`, `.dist`, bundles JS)  
- Minificar e otimizar recursos  

### 💻 Exemplo (Node.js)
```json
"scripts": {
  "build": "webpack",
  "start": "node app.js"
}
```

---

## 🚀 Scripts de Deploy (Implantação)

Responsáveis por publicar a aplicação em um ambiente.

### 🔧 Funções:
- Enviar arquivos para servidor  
- Configurar variáveis de ambiente  
- Atualizar versões da aplicação  

### 💻 Exemplo
```bash
docker build -t app .
docker run -d -p 80:3000 app
```

---

## 🔄 Automação

Scripts podem ser integrados ao pipeline CI/CD:
- Executados automaticamente após commit  
- Garantem padronização do processo  
- Reduzem erros manuais  

---

## ⚠️ Boas Práticas

- Versionar scripts no repositório  
- Manter scripts simples e reutilizáveis  
- Usar variáveis de ambiente  
- Testar antes do deploy em produção  

---

## 🎯 Benefícios

- Agilidade no desenvolvimento  
- Consistência entre ambientes  
- Redução de erros humanos  

---

## ✅ Resumo

Build = construir a aplicação  
Deploy = disponibilizar a aplicação  
Scripts automatizam todo o processo  

---

## 📌 6. Controle de Versão Avançado

O controle de versão permite gerenciar alterações no código, facilitando colaboração, rastreabilidade e organização do desenvolvimento.

---

## 🔄 Conceitos Importantes

- **Branches** → linhas de desenvolvimento independentes (ex: `feature/login`)  
- **Merge** → junção de alterações entre branches  
- **Pull Request (PR)** → solicitação de revisão antes de integrar código  

### 💻 Exemplo
```bash
git checkout -b feature/login
git add .
git commit -m "feat: tela de login"
git push origin feature/login
```

---

## 🧩 Estágios do Commit

1. **Working Directory** → arquivos modificados  
2. **Staging Area** → arquivos preparados (`git add`)  
3. **Repositório** → histórico salvo (`git commit`)  

---

## 🔁 Fluxo Básico

1. Criar branch  
2. Desenvolver funcionalidade  
3. Commit das alterações  
4. Abrir Pull Request  
5. Merge após revisão  

---

## 🎯 Objetivos

- Controle de mudanças no código  
- Trabalho colaborativo entre desenvolvedores  
- Manutenção do histórico de versões  

---

## ⚠️ Boas Práticas

- Commits pequenos e frequentes  
- Mensagens claras (ex: `feat`, `fix`)  
- Uso de branches por funcionalidade  
- Revisão de código antes do merge  

---

## 🚀 Benefícios

- Organização do desenvolvimento  
- Facilidade de rollback  
- Melhor controle de versões  

---

## ✅ Resumo

Commit = salvar mudanças no histórico  
Branch = linha paralela de desenvolvimento  
PR = revisão antes de integrar código  

---

## 📌 7. Testes Automatizados e Qualidade de Software

Os testes automatizados garantem que o sistema funcione corretamente, prevenindo erros antes que cheguem à produção.

---

## 🧪 Tipos de Testes

- **Unitários** → testam funções isoladas  
- **Integração** → testam comunicação entre módulos  
- **Sistema** → testam a aplicação completa  

### 💻 Exemplo (JavaScript)
```javascript
function soma(a, b) {
  return a + b;
}

test('soma correta', () => {
  expect(soma(2, 3)).toBe(5);
});
```

---

## 🎯 Qualidade de Software

Garantir qualidade envolve boas práticas no desenvolvimento.

### 🔧 Práticas:
- Código limpo e organizado  
- Cobertura de testes adequada  
- Análise estática (lint, segurança)  

---

## ⚙️ Automação de Testes

- Executados automaticamente no pipeline CI/CD  
- Detectam falhas rapidamente  
- Garantem estabilidade do sistema  

---

## ⚠️ Boas Práticas

- Testar casos positivos e negativos  
- Manter testes atualizados  
- Automatizar sempre que possível  
- Integrar testes ao pipeline  

---

## 🚀 Benefícios

- Redução de bugs  
- Maior confiabilidade  
- Facilidade de manutenção  

---

## ✅ Resumo

Teste = prevenir erros antes da produção  
Qualidade = código limpo + testes + validação contínua  


---

## 📌 8. Implantação e Entrega de Aplicações

A implantação (deploy) é o processo de disponibilizar o sistema para uso em ambientes como teste ou produção.

---

## 🚀 Tipos de Deploy

- **Manual** → feito por intervenção humana (mais sujeito a erros)  
- **Automatizado** → realizado por scripts ou pipelines  
- **Contínuo** → deploy automático após validações (CI/CD)  

---

## ⚙️ Exemplo de Deploy

```bash
docker build -t app .
docker run -d -p 80:3000 app
```

---

## 🎯 Boas Práticas

- Uso de pipelines CI/CD para automação  
- Monitoramento da aplicação após deploy  
- Implementação de rollback em caso de falha  
- Separação de ambientes (dev, teste, produção)  

---

## 🔄 Estratégias de Deploy

- **Blue/Green** → duas versões em paralelo  
- **Rolling Update** → atualização gradual  
- **Canary** → liberação para poucos usuários  

---

## 💡 Objetivos

- Entregas rápidas e frequentes  
- Redução de erros em produção  
- Maior confiabilidade do sistema  

---

## 📊 Monitoramento

- Logs de aplicação  
- Métricas de desempenho  
- Alertas de falhas  

---

## 🎯 Síntese Final

- DevOps integra desenvolvimento e operações  
- CI/CD automatiza integração e entrega  
- Pipeline organiza o fluxo do software  
- Versionamento controla mudanças  
- Testes garantem qualidade  
- Deploy entrega valor ao usuário  

---

## ✅ Resumo

Deploy = colocar em produção  
Automação = mais segurança e velocidade  
Monitoramento = garantir estabilidade  

# 08 - Entrega Contínua, DevOps e Observabilidade

## 🎯 Objetivo
Compreender a entrega contínua em ambientes reais, estratégias de release, monitoramento, cultura DevOps e integração com cloud, além de analisar métricas e maturidade de processos de entrega.

---

## 📚 Conceitos-chave
- Entrega contínua vs deploy contínuo
- Estratégias de release
- Monitoramento
- Observabilidade
- Logs e métricas
- Cultura DevOps
- Integração com cloud
- Kubernetes básico
- Escalabilidade
- Maturidade DevOps
- Métricas de entrega (lead time, deploy frequency)
- Gestão de fluxo de entrega

---

## 🧠 Explicação

### 🔹 Entrega contínua vs deploy contínuo
- **Entrega contínua** → sistema sempre pronto para deploy manual  
- **Deploy contínuo** → deploy automático em produção  

---

### 🔹 Estratégias de release
Formas de liberar novas versões:
- Blue/Green
- Canary
- Rolling update

---

### 🔹 Monitoramento
Acompanhamento do sistema em produção:
- Disponibilidade
- Performance
- Erros

---

### 🔹 Observabilidade
Capacidade de entender o comportamento do sistema através de:
- Logs
- Métricas
- Traces

---

### 🔹 Logs e métricas
- **Logs** → registros de eventos  
- **Métricas** → dados quantitativos (CPU, memória, tempo de resposta)

---

### 🔹 Cultura DevOps
Integra:
- Desenvolvimento
- Operações
- Automação
- Colaboração

Objetivo: entregar software com qualidade e rapidez.

---

### 🔹 Integração com cloud
Uso de plataformas cloud:
- AWS
- Azure
- GCP

Benefícios:
- Escalabilidade
- Alta disponibilidade
- Automação

---

### 🔹 Kubernetes básico
Orquestrador de containers que gerencia:
- Deploy
- Escala
- Balanceamento

---

### 🔹 Escalabilidade
Capacidade de aumentar recursos conforme demanda:
- Horizontal (mais instâncias)
- Vertical (mais recursos)

---

### 🔹 Métricas (lead time, deploy frequency)
- **Lead time** → tempo do commit até produção  
- **Deploy frequency** → frequência de deploys  

---

### 🔹 Maturidade DevOps
Níveis de evolução:
1. Manual  
2. Automatizado  
3. Contínuo  
4. Otimizado  

---

### 🔹 Gestão de fluxo de entrega
Controle do fluxo de desenvolvimento até produção:
- Redução de gargalos
- Automação
- Melhoria contínua

---

## 🔧 Ferramentas relacionadas
- Kubernetes
- Docker
- Prometheus
- Grafana
- ELK Stack (Elasticsearch, Logstash, Kibana)
- AWS / Azure / GCP

---

## 💻 Exemplo prático

Exemplo de comando Kubernetes:

kubectl apply -f deployment.yaml

---

Exemplo de métrica (Prometheus):

http_requests_total

---

Exemplo de log:

[INFO] Application started successfully

---

## ⚠️ Erros comuns
- Não monitorar produção
- Falta de métricas
- Deploy sem estratégia
- Ignorar logs
- Não escalar corretamente
- Falta de cultura DevOps

---

## 📝 Resumo
- Entrega contínua prepara deploy; deploy contínuo automatiza
- Observabilidade = logs + métricas + análise
- Cloud permite escala e automação
- Kubernetes gerencia containers
- Métricas ajudam a melhorar entrega
- DevOps é cultura + processo + tecnologia

---

## 📖 Referências
- HUMBLE, J.; PRIKLADNICKI, R. Entrega Contínua. Bookman, 2013.  
- MUNIZ, A. et al. Jornada DevOps. Brasport, 2019.  
- SATO, D. DevOps na prática. Casa do Código, 2014.  
- ARUNDEL, J.; DOMINGUS, J. DevOps nativo de nuvem com Kubernetes. Novatec, 2019.  

---

## 🚀 Desafio / Exercício
1. Configure monitoramento básico (logs ou métricas)  
2. Simule deploy com estratégia (Blue/Green ou Canary)  
3. Calcule lead time de uma mudança  
4. Suba uma aplicação simples no Kubernetes  
5. Analise melhorias no fluxo de entrega  
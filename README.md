## 📦 Pedidos Veloz

**Este projeto é uma aplicação de microserviços desenvolvida para demonstrar as práticas modernas de arquitetura de software e conceitos de DevOps. Utiliza as seguintes tecnologias:**
- Docker
- Docker Compose
- Kubernetes
- CI/CD (Integração e Entrega Contínua)
- HPA (Horizontal Pod Autoscaler)

## 🎯 Objetivo do Projeto

**O principal objetivo deste projeto é demonstrar:**
- Containerização de aplicações com Docker.
- Arquitetura baseada em microserviços.
- Orquestração de containers com Kubernetes.
- Escalabilidade automática usando o Horizontal Pod Autoscaler (HPA).
- Integração e entrega contínua (CI/CD).


## 🏗 Arquitetura do Sistema

**O sistema é dividido em quatro microserviços:**
- Gateway: Centraliza as requisições de entrada.
- Pedidos: Gerencia as operações relacionadas a pedidos.
- Pagamentos: Processa os pagamentos.
- Estoque: Controla o inventário de produtos.

**Cada serviço é independente e roda em seu próprio container, proporcionando:**
- Facilidade na manutenção.
- Escalabilidade de cada serviço individualmente.
- Melhor organização do código e atualizações isoladas.

## 🐳 Docker

**Cada microserviço possui seu próprio Dockerfile para:**
- Definir a imagem base (Node.js 20 Alpine).
- Copiar os arquivos do projeto.
- Instalar as dependências necessárias.
- Definir o comando de execução.

**Subindo o Projeto com Docker Compose**
Com o comando:

```
docker compose up --build
```
Esse comando:

- Constrói as imagens Docker.
- Cria os containers necessários.
- Inicia todos os serviços simultaneamente.

## ☸ Kubernetes

**Após a containerização, o sistema foi adaptado para rodar em Kubernetes. Para isso, foram criados os seguintes recursos:**
- Deployments: Gerenciam a implantação dos serviços.
- Services: Permitem comunicação entre os serviços.
- Namespace: Para organizar os recursos no Kubernetes.
- HPA (Horizontal Pod Autoscaler): Escala os pods automaticamente conforme a carga.

**Aplicando os manifests:**
```
kubectl apply -f k8s/
```
**Verificando os Pods:**
```
kubectl get pods
```
## 📈 HPA — Horizontal Pod Autoscaler

**O HPA ajusta automaticamente a quantidade de pods com base no uso de CPU. O comportamento é o seguinte:**

- Se a demanda aumentar, o Kubernetes cria novos pods automaticamente.
- Se a demanda diminuir, o número de pods é reduzido.

**Isso garante:**

- Melhor performance.
- Uso eficiente de recursos.
- Escalabilidade automática.

## 🔁 CI/CD

**Este projeto utiliza GitHub Actions para automação do processo de integração e entrega contínua. A cada push no repositório:**

- O pipeline de CI/CD é executado automaticamente.
-  build é validado.
- As etapas configuradas do processo são rodadas automaticamente.

Essa automação simula um ambiente profissional de integração contínua, facilitando a entrega de novas versões de forma eficiente e sem erros.

## 📊 Monitoramento (Opcional)

**O sistema pode ser integrado com ferramentas de monitoramento como:**

- Prometheus: Para coletar métricas.
- Grafana: Para visualização de métricas como uso de CPU, memória, e status dos pods.

## 🚀 Tecnologias Utilizadas

- Node.js: Plataforma de execução para os microserviços.
- Docker: Para containerização.
- Docker Compose: Para orquestração local de containers.
- Kubernetes: Para orquestração de containers em produção.
- GitHub Actions: Para automação do pipeline CI/CD.
- Minikube: Para testar o Kubernetes localmente.

## 📚 Estrutura do Projeto
```
pedidos-veloz/
│
├── gateway/
├── pedidos/
├── pagamentos/
├── estoque/
│
├── k8s/
│   ├── pedidos.yaml
│   ├── pagamentos.yaml
│   ├── estoque.yaml
│   ├── gateway.yaml
│
├── docker-compose.yml
└── README.md
```


Link do video explicativo
https://youtu.be/pin5QK7i4bM


##  Autor
**Matheus Souza**
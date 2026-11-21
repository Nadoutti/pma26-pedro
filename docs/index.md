# Pedro Nadotti · PMA 2026.2

**Nome:** Pedro Nadotti
**Grupo:** Organização dos Coisa Ruim
**Projeto:** e-commerce em microsserviços Spring Boot (Gateway, Auth, Account, Exchange, Product, Order), com Docker
Compose, Kubernetes e AWS.

## Documentação do projeto

A documentação completa do projeto do grupo (arquitetura, serviços, API, gargalos, Kubernetes, CI/CD, load test,
custos e uso de IA) está no site do grupo:

**[organizacao-dos-coisa-ruim.github.io/pma26](https://organizacao-dos-coisa-ruim.github.io/pma26/)**

## Meus gargalos

| Gargalo | Problema | Solução | Evidência |
|---------|----------|---------|-----------|
| [Observabilidade (Prometheus + Grafana)](https://organizacao-dos-coisa-ruim.github.io/pma26/gargalos/observabilidade/) | o sistema era uma caixa-preta: sem métricas de requisições por segundo, latência ou erros | Spring Actuator + Micrometer em todos os serviços → Prometheus → Grafana, com dashboards provisionados | dashboards do Grafana (RPS, p95/p99, 5xx, CPU, heap, pool do banco, threads) |
| [RBAC (controle de acesso por papel)](https://organizacao-dos-coisa-ruim.github.io/pma26/gargalos/rbac/) | qualquer usuário logado listava e apagava contas de outros usuários | papel `user`/`admin` no JWT, checado no gateway e no Account | cenários 403/200 no smoke test do CI |

## Código-fonte do projeto

| Repositório | O que é |
|-------------|---------|
| [pma26](https://github.com/Organizacao-dos-Coisa-Ruim/pma26) | repositório principal: submodules, Docker Compose, Kubernetes, documentação |
| [gateway-service](https://github.com/Organizacao-dos-Coisa-Ruim/gateway-service) | API Gateway (Spring Cloud Gateway) |
| [pma26-auth](https://github.com/Organizacao-dos-Coisa-Ruim/pma26-auth) · [pma26-auth-service](https://github.com/Organizacao-dos-Coisa-Ruim/pma26-auth-service) | autenticação (JWT) |
| [pma-26-account](https://github.com/Organizacao-dos-Coisa-Ruim/pma-26-account) · [pma26-account-service](https://github.com/Organizacao-dos-Coisa-Ruim/pma26-account-service) | contas de usuário |
| [pma26-exchange](https://github.com/Organizacao-dos-Coisa-Ruim/pma26-exchange) · [pma26-exchange-service](https://github.com/Organizacao-dos-Coisa-Ruim/pma26-exchange-service) | câmbio |
| [product](https://github.com/Organizacao-dos-Coisa-Ruim/product) · [product-service](https://github.com/Organizacao-dos-Coisa-Ruim/product-service) | catálogo de produtos |
| [order](https://github.com/Organizacao-dos-Coisa-Ruim/order) · [order-service](https://github.com/Organizacao-dos-Coisa-Ruim/order-service) | pedidos (com mensageria RabbitMQ) |

## Atividades (exercícios)

*A adicionar: documentação e código-fonte dos exercícios da disciplina.*

## Apresentação

*A adicionar: slides e vídeo de 1 a 2 minutos.*

## Uso de IA

Partes do código e da documentação foram feitas com auxílio do Claude Code, conforme a regra do curso. O registro
detalhado (o que a IA fez e o que o grupo fez) está em
[Uso de IA](https://organizacao-dos-coisa-ruim.github.io/pma26/ia/).

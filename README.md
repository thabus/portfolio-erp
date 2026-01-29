# Sistema de Gestão Empresarial (ERP) - Fullstack

> **Status:** Em Desenvolvimento 🚧

Um sistema ERP (Enterprise Resource Planning) completo e personalizado, desenvolvido para digitalizar a operação de uma empresa de Representação Comercial. O objetivo foi centralizar o controle financeiro, gestão de clientes e fluxo de atendimento (chamados) que antes eram descentralizados.

---

## 📸 Visão Geral do Projeto

### 1. Dashboard Executivo e Financeiro
Painel de controle para visualização rápida de KPIs, metas mensais e fluxo de caixa.
* **Destaque:** As informações financeiras são renderizadas apenas para usuários do setor "Financeiro".

| Dashboard de Vendas | Controle Financeiro |
|:---:|:---:|
| ![Dashboard Principal](https://github.com/thabus/portfolio-erp/blob/main/assets/metas.png) | ![Financeiro](https://github.com/thabus/portfolio-erp/blob/main/assets/financas.png) |

---

### 2. Sistema de Chamados Inteligente (SLA & Workflow)
Módulo para gestão de demandas de TI e operacionais.
* **Workflow Completo:** `Aberto` → `Em Andamento` → `Pendente` → `Resolvido` → `Fechado`.
* **Regra de Negócio Automatizada:** Implementação de uma lógica no Backend que aguarda **24 horas** após um chamado ser marcado como "Resolvido". Se não houver contestação, o sistema altera o status automaticamente para "Fechado", bloqueando edições futuras para garantir a integridade histórica do atendimento.

![Detalhe do Chamado](https://github.com/thabus/portfolio-erp/blob/main/assets/sistema-de-chamados.png)

---

### 3. Experiência Mobile (Responsividade)
O sistema foi projetado com metodologia *Mobile First*. Menus, tabelas e modais se adaptam fluidamente a telas menores, permitindo que a equipe externa consulte pedidos e abra chamados pelo celular.

| Menu Mobile | Busca Responsiva |
|:---:|:---:|
| ![Menu Mobile](https://github.com/thabus/portfolio-erp/blob/main/assets/icones-mobile.png) | ![Busca Mobile](https://github.com/thabus/portfolio-erp/blob/main/assets/mobile-historico-compras.png) |

---

## 🔐 Segurança Avançada e Controle de Acesso (RBAC)

A segurança foi um pilar central deste desenvolvimento, utilizando **JWT (JSON Web Tokens)** para garantir que cada requisição seja autêntica e autorizada.

* **Proteção Total de Rotas:** Todas as vias de acesso e endpoints da API exigem validação. Não é possível acessar uma página ou dados apenas colando a URL no navegador; o Back-end verifica o token e as permissões em tempo real.
* **Autenticação por Setor:**
    * Usuários do **Financeiro** acessam fluxo de caixa e relatórios.
    * Usuários de **TI** acessam a gestão de chamados e logs.
    * O Front-end utiliza renderização condicional para montar o menu dinamicamente com base nas *authorities* contidas no token JWT.

---

## 🛠 Tecnologias Utilizadas

Arquitetura moderna baseada em microsserviços e SPA.

### Back-end (API)
* **Java 17 & Spring Boot:** Núcleo da aplicação.
* **Spring Security + JWT:** Implementação rigorosa de stateless authentication.
* **PostgreSQL:** Banco de dados relacional.
* **Task Scheduling:** Para automação do fechamento de chamados (regra de 24h).

### Front-end (Interface)
* **React.js:** Single Page Application (SPA).
* **Axios Interceptors:** Para injetar o Token JWT automaticamente nos headers das requisições.
* **Recharts & Chart.js:** Bibliotecas para composição dos gráficos analíticos.
* **CSS Modules/Styled Components:** Para estilização responsiva.

---

## 🧠 Desafios e Aprendizados
Este projeto apresentou desafios técnicos significativos que elevaram meu nível de senioridade:

1.  **A Rigidez do Spring Security:** Implementar o filtro de JWT foi desafiador. Configurar a aplicação para que *nenhuma* rota ficasse exposta acidentalmente exigiu disciplina: cada novo endpoint criado precisava ser explicitamente mapeado e autorizado. Isso garantiu uma aplicação "Secure by Design".
2.  **Lógica de Estado Temporal:** Criar a automação que monitora o tempo (24h) para fechar chamados exigiu lidar com cron jobs e verificação de timestamps no banco de dados.
3.  **Visualização de Dados:** Transformar tabelas gigantes de banco de dados em gráficos limpos e rápidos usando Recharts.

---

## 📬 Contato
Desenvolvido por **Thaís Bustamante**.
* [https://www.linkedin.com/in/tha%C3%ADs-bustamante/]
* [thais.bustamante@outlook.com]

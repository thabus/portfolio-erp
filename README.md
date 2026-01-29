# Sistema de Gestão Empresarial (ERP) - Fullstack

> **Status:** Em Desenvolvimento 🚧

Um sistema ERP (Enterprise Resource Planning) completo e personalizado, desenvolvido para digitalizar a operação de uma empresa de Representação Comercial. O objetivo foi centralizar o controle financeiro, gestão de clientes e fluxo de atendimento (chamados) que antes eram descentralizados.

---

## 📸 Visão Geral do Projeto

### 1. Dashboard Executivo
Painel de controle para visualização rápida de KPIs (Indicadores-Chave de Desempenho).
* Visualização de metas mensais vs. realizado.
* Gráficos de tendências de vendas usando visualização de dados dinâmica.
* Filtros por representação e período.

![Dashboard Principal](caminho-para-sua-imagem-dashboard.png)
*(Substitua pela sua Imagem 2 ou 3 editada)*

---

### 2. Módulo Financeiro
Controle rigoroso de fluxo de caixa (Entradas e Saídas).
* **Features:** Cadastro de transações, categorização de despesas e cálculo automático de lucro líquido.
* **Destaque Técnico:** O back-end realiza agregações complexas para gerar os relatórios de "Receitas vs Despesas" em tempo real.

| Resumo Financeiro | Listagem de Transações |
|:---:|:---:|
| ![Resumo](caminho-para-imagem-9.png) | ![Transações](caminho-para-imagem-10.png) |

---

### 3. Sistema de Chamados (Ticket System)
Módulo interno para gestão de demandas e suporte de TI.
* Permite abertura, edição e acompanhamento de chamados.
* Workflow de status (Aberto, Em Andamento, Fechado) e Prioridade.
* Filtros avançados e ordenação para gestão da fila de atendimento.

![Sistema de Chamados](caminho-para-imagem-6-ou-8.png)

---

## 🔐 Controle de Acesso e Segurança (RBAC)
O sistema implementa uma lógica rigorosa de permissões baseada no setor do usuário:
* **Renderização Condicional:** O Front-end verifica o perfil do usuário logado e oculta/exibe itens do menu dinamicamente.
* **Proteção de Rotas:** Páginas sensíveis (como o Módulo Financeiro) são acessíveis **apenas** para usuários autenticados e vinculados ao setor Financeiro/Administrativo.
* **Segurança no Backend:** A API valida as requisições para garantir que usuários não acessem dados de outros setores via URL direta.

---

## 📱 Design Responsivo (Mobile First)
A interface foi projetada pensando na usabilidade em diferentes dispositivos.
* Layouts flexíveis que se adaptam a telas de desktops e celulares.
* Menus e tabelas otimizados para toque (touch), permitindo que a equipe de vendas ou gerência consulte dados rapidamente pelo smartphone.

---

## 🛠 Tecnologias Utilizadas

O projeto foi construído utilizando uma arquitetura moderna, separando totalmente o Back-end do Front-end (REST API).

### Back-end (API)
* **Java 17 & Spring Boot:** Núcleo da aplicação.
* **Spring Security:** Autenticação e controle de acesso (Login/Logout).
* **PostgreSQL:** Banco de dados relacional para persistência segura.
* **Hibernate/JPA:** Mapeamento objeto-relacional.

### Front-end (Interface)
* **React.js:** Biblioteca para construção da interface interativa (SPA).
* **Axios:** Consumo da API REST.
* **Bibliotecas de UI:** Componentes modulares para garantir responsividade e design limpo.
* **Visualização de Dados:** Uso híbrido de **Recharts** e **Chart.js** para diferentes tipos de relatórios gráficos.

---

## 🧠 Desafios e Aprendizados
Este projeto simula um ambiente corporativo real, lidando com:
1.  **Regras de Negócio Complexas:** Cálculo de comissões e metas que variam por representante.
2.  **CRUDs Interdependentes:** O sistema de chamados se conecta aos usuários, que se conectam aos setores.
3.  **Visualização de Dados:** Transformação de dados brutos do PostgreSQL em gráficos intuitivos para tomada de decisão.

---

## 📬 Contato
Desenvolvido por **Thaís Bustamante**.
* [Seu LinkedIn]
* [Seu E-mail]

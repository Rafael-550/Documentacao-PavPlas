# 🛒 PavPlas — Gateway de Pagamento

Sistema em desenvolvimento para **automação do processo de vendas, pedidos, estoque e pagamentos da PavPlas**, desenvolvido como projeto acadêmico do curso de **Gestão da Tecnologia da Informação — Fatec Barueri**. Site: https://www.pavplas.com.br/

> 🚧 **Status: Em desenvolvimento**
>
> O projeto contempla a implementação da base do sistema comercial e de controle operacional, enquanto funcionalidades como integração com gateway de pagamento, ERP, logística e processamento financeiro automatizado fazem parte do cenário **To-Be** e das próximas etapas do projeto.

---

## 📌 Sobre o projeto

O projeto tem como objetivo analisar, modelar e implementar uma solução tecnológica para modernizar o processo de vendas da **PavPlas**.

Atualmente, o processo comercial da empresa possui forte dependência de atividades manuais. O site funciona principalmente como catálogo de produtos, enquanto a compra envolve atendimento pelo **WhatsApp**, consultas de estoque, negociação, definição de frete e confirmação manual de pagamentos.

A proposta do projeto é transformar esse processo em uma plataforma integrada, permitindo centralizar as informações de **produtos, estoque, pedidos e pagamentos**, reduzindo retrabalho e melhorando a experiência do cliente.

O sistema foi estruturado considerando a integração futura com **Gateway de Pagamento, ERP, sistemas de estoque/WMS, serviços de logística e processos financeiros e fiscais**.

---

## 🎯 Objetivo geral

Analisar, modelar e propor o desenvolvimento de um **Gateway de Pagamento integrado ao processo de vendas da PavPlas**, buscando:

- Automatizar e centralizar as etapas de compra e pagamento;
- Reduzir atividades manuais e retrabalho;
- Aumentar a segurança das transações;
- Melhorar a integração entre vendas, estoque, financeiro e logística;
- Melhorar a experiência de compra do cliente.

---

## 🎯 Objetivos específicos

- Levantar e analisar o processo atual de vendas e pagamentos da PavPlas;
- Identificar gargalos, limitações e riscos do processo atual;
- Mapear requisitos funcionais, administrativos e não funcionais;
- Modelar o processo futuro (**To-Be**);
- Desenvolver a base do sistema comercial e operacional;
- Projetar a integração com Gateway de Pagamento, ERP e serviços externos;
- Implementar mecanismos de segurança e controle de acesso;
- Avaliar o funcionamento da solução em relação aos requisitos definidos.

---

## 🔎 Problema identificado

O processo atual da PavPlas depende de atividades manuais entre diferentes setores e ferramentas.

Entre os principais problemas identificados estão:

- Dependência de atendimento humano para concluir vendas;
- Limitação do processo de vendas ao horário de atendimento;
- Conferência manual de pagamentos;
- Risco de falsificação de comprovantes;
- Falta de integração entre vendas, estoque, faturamento e logística;
- Uso de planilhas e informações descentralizadas;
- Redigitação de dados e possibilidade de inconsistências;
- Necessidade de sair do site e utilizar o WhatsApp para concluir a compra.

Esses problemas foram utilizados como base para definição do processo proposto.

---

# 🔄 Processo As-Is x To-Be

### Processo atual — As-Is

```text
Cliente
   │
   ▼
Catálogo
   │
   ▼
WhatsApp
   │
   ├── Consulta de estoque
   ├── Negociação
   ├── Definição de frete
   └── Dados para pagamento
   │
   ▼
PIX / Transferência
   │
   ▼
Envio do comprovante
   │
   ▼
Conferência financeira
   │
   ▼
Separação do produto
   │
   ▼
Faturamento
   │
   ▼
Transportadora
```

### Processo proposto — To-Be

```text
Cliente
   │
   ▼
E-commerce
   │
   ▼
Catálogo
   │
   ▼
Carrinho
   │
   ▼
Validação de Estoque
   │
   ▼
CEP / Frete
   │
   ▼
Checkout
   │
   ▼
Gateway de Pagamento
   │
   ├── PIX
   ├── Boleto
   └── Cartão
   │
   ▼
Confirmação do Pagamento
   │
   ├── Atualização do Pedido
   ├── Baixa no Estoque
   ├── ERP / Faturamento
   ├── Logística / WMS
   └── Registro Financeiro
```

A arquitetura proposta também considera comunicação assíncrona por **Webhooks**, permitindo atualizar o status das transações e dos pedidos após o processamento do pagamento.

---

# 🛍️ Funcionalidades

## ✅ Base do sistema

Funcionalidades implementadas ou em implementação no projeto atual:

- [x] Catálogo de produtos;
- [x] Busca e filtros de produtos;
- [x] Detalhamento de produtos;
- [x] Carrinho de compras;
- [x] Controle de usuários;
- [x] Autenticação;
- [x] Controle de acesso por perfis;
- [x] Cadastro e gerenciamento de produtos;
- [x] Categorias;
- [x] Controle de estoque;
- [x] Histórico de movimentações;
- [x] Backend integrado ao banco de dados;
- [x] Aplicação hospedada em ambiente de produção.

---

## 🛒 E-commerce

Funcionalidades previstas no modelo To-Be:

- [x] Catálogo de produtos;
- [x] Carrinho de compras;
- [ ] Cadastro e autenticação de clientes;
- [ ] Checkout completo;
- [ ] Validação automática de estoque no fechamento do pedido;
- [ ] Cadastro e validação do endereço de entrega;
- [ ] Cálculo automático de frete via integração;
- [ ] Seleção da modalidade de entrega;
- [ ] Histórico de pedidos do cliente;
- [ ] Acompanhamento do status do pedido.

---

## 💳 Gateway de pagamento

A solução proposta prevê integração com um Gateway de Pagamento para processamento das transações.

- [ ] Integração com Gateway de Pagamento;
- [ ] Pagamento via PIX;
- [ ] Geração de QR Code e PIX Copia e Cola;
- [ ] Pagamento via boleto bancário;
- [ ] Geração e disponibilização de boleto;
- [ ] Pagamento via cartão de crédito;
- [ ] Parcelamento parametrizado;
- [ ] Retorno do status da transação;
- [ ] Atualização automática do pedido;
- [ ] Webhooks autenticados;
- [ ] Tratamento idempotente de eventos;
- [ ] Cancelamentos e estornos;
- [ ] Tratamento de chargebacks.

---

## 📦 Estoque e pedidos

O projeto possui uma camada de controle operacional responsável pela gestão de produtos e estoque.

Funcionalidades previstas para evolução:

- [x] Cadastro de produtos;
- [x] Categorias;
- [x] Controle de saldo;
- [x] Movimentações de estoque;
- [x] Histórico de movimentações;
- [ ] Reserva temporária de estoque;
- [ ] Baixa automática após pagamento aprovado;
- [ ] Gestão completa do ciclo de vida do pedido;
- [ ] Ordem de separação;
- [ ] Atualização de rastreamento.

---

## 🏢 ERP e integrações

O modelo arquitetural da solução prevê integração com sistemas externos.

```text
             ┌──────────────────────┐
             │       Cliente        │
             └──────────┬───────────┘
                        │
                        ▼
             ┌──────────────────────┐
             │    Sistema PavPlas   │
             │   E-commerce +       │
             │   Gestão Operacional │
             └──────────┬───────────┘
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
      Gateway          ERP         Logística
    Pagamento                       / WMS
          │             │             │
          └─────────────┼─────────────┘
                        ▼
                 Financeiro/Fiscal
```

Integrações previstas:

- [ ] Gateway de pagamento;
- [ ] ERP;
- [ ] Sistema de estoque/WMS;
- [ ] Transportadora;
- [ ] Serviços de frete;
- [ ] Faturamento e NF-e;
- [ ] Processos financeiros;
- [ ] Webhooks de serviços externos.

---

# 🔐 Segurança

A segurança é um dos pontos centrais da solução proposta.

O projeto considera:

- Autenticação individual;
- Autorização baseada em perfis;
- Princípio do menor privilégio;
- Controle de acesso no servidor;
- Proteção das credenciais;
- Identificação única das transações;
- Validação de Webhooks;
- Idempotência para evitar processamento duplicado;
- Proteção de dados pessoais;
- Minimização da coleta de dados;
- Tokenização de dados de cartão;
- Não armazenamento de PAN completo, CVV ou validade do cartão;
- Mascaramento de informações sensíveis em logs;
- Controle e retenção de registros;
- Adequação às diretrizes da **LGPD**.

Os perfis previstos pela solução incluem usuários administrativos, financeiro, comercial, estoque/expedição, faturamento, transportadora e cliente final.

---

# 👥 Perfis de usuário

A solução considera diferentes perfis de acesso para aplicar o princípio do menor privilégio:

| Perfil | Função principal |
|---|---|
| **Administrador** | Gerenciar usuários, permissões e configurações |
| **Comercial** | Acompanhar pedidos e operações comerciais |
| **Financeiro** | Acompanhar transações, conciliação e operações financeiras |
| **Estoque/Expedição** | Consultar estoque, separar pedidos e acompanhar envios |
| **Faturamento** | Processos fiscais e emissão de documentos |
| **Transportadora** | Operações relacionadas à entrega |
| **Cliente** | Comprar produtos e acompanhar pedidos |

---

# 🧩 Tecnologias

### Frontend

- **React**
- **TypeScript**
- **Vite**
- **Tailwind CSS**
- **Lucide React**

### Backend

- **Node.js**
- **Express**
- **TypeScript**
- **Prisma ORM**
- **JWT**

### Banco de dados

- **PostgreSQL**
- **Supabase**

### Infraestrutura

- **Vercel** — Frontend
- **Render** — Backend
- **Supabase** — Banco de dados

### Ferramentas

- **Git**
- **GitHub**
- **Trello**
- **Visual Studio Code**

### Modelagem e processos

- **BPMN**
- **UML**
- **DER**

---

# 📋 Requisitos

A monografia define requisitos funcionais, administrativos e não funcionais para a solução.

Entre os principais requisitos funcionais estão:

- Cadastro e autenticação de usuários;
- Catálogo;
- Carrinho;
- Controle de estoque;
- Checkout;
- Frete;
- PIX;
- Boleto;
- Cartão;
- Atualização do status dos pedidos;
- Integração com ERP;
- Integração logística;
- Conciliação financeira;
- Cancelamentos e estornos.

Também são previstos requisitos administrativos relacionados a:

- Controle de acesso por perfis;
- Gerenciamento de produtos;
- Ajustes de estoque;
- Gestão de pedidos;
- Configuração do gateway;
- Conciliação financeira;
- Integração com ERP;
- Dashboards e relatórios;
- Gerenciamento de fretes.

---

# 🚀 Roadmap

O projeto foi estruturado em etapas para permitir a evolução gradual da solução.

### 1. Base do sistema

- [x] Estrutura frontend;
- [x] Backend;
- [x] Banco de dados;
- [x] Autenticação;
- [x] Controle de usuários;
- [x] Produtos e categorias;
- [x] Controle de estoque;
- [x] Loja e carrinho.

### 2. MVP

- [ ] Checkout;
- [ ] Pedidos;
- [ ] Integração de frete;
- [ ] Gateway de pagamento;
- [ ] PIX;
- [ ] Boleto;
- [ ] Cartão;
- [ ] Atualização automática de pedidos;
- [ ] Integração inicial com estoque.

### 3. Integrações e evolução

- [ ] ERP;
- [ ] WMS / logística;
- [ ] NF-e;
- [ ] Conciliação financeira;
- [ ] Rastreamento;
- [ ] Webhooks;
- [ ] Estornos;
- [ ] Chargeback / Stop Delivery;
- [ ] Relatórios gerenciais;
- [ ] Melhorias de segurança e observabilidade.

---

# 📚 Documentação acadêmica

A monografia **“Desenvolvimento e Implementação de um Gateway de Pagamento para a PavPlas”** aborda:

- Introdução e contextualização;
- Problema de pesquisa;
- Justificativa e objetivos;
- Sistemas de pagamento;
- Gateway de pagamento;
- APIs REST;
- Integração de sistemas;
- Segurança da informação;
- Banco de dados;
- Engenharia de software;
- LGPD;
- Metodologia;
- Levantamento de requisitos;
- Stakeholders e personas;
- Processo **As-Is**;
- Problemas e gargalos;
- Processo **To-Be**;
- Requisitos funcionais;
- Requisitos administrativos;
- Requisitos não funcionais;
- Modelagem e arquitetura;
- Casos de uso;
- Diagrama de classes;
- Modelo de dados;
- Fluxo de pagamento;
- Segurança e controle de acesso;
- Conclusão, limitações e trabalhos futuros.

---

# 🎓 Projeto acadêmico

Projeto desenvolvido para o curso de:

**Fatec Barueri — Padre Danilo José de Oliveira Ohl**

**Curso:** Gestão da Tecnologia da Informação  
**Ano:** 2026

### 👥 Integrantes

- Rafael Thiengo Reis
- Gustavo Sirqueira Soares da Silva
- Stanley Sousa do Vale
- Cauã Azeredo Golden Rodrigues
- Nayara Teixeira da Silva
- Heitor Soares Tanan
- Bruno Temoteo de Macedo

**Orientador:** Prof. Vander Ribeiro Elme

---

# 📄 Referências

O projeto utiliza referências relacionadas a:

- Gestão de Processos de Negócio (BPM);
- Mapeamento de processos As-Is e To-Be;
- Gateways de pagamento;
- APIs REST;
- Segurança da informação;
- LGPD;
- PCI-DSS;
- Engenharia de Software;
- Integração de sistemas.

---

## 🚧 Projeto em desenvolvimento

Este repositório acompanha a evolução do projeto **PavPlas — Gateway de Pagamento**, desde o levantamento e análise do processo atual até a construção da solução proposta.

A arquitetura foi planejada para permitir a evolução do sistema comercial e de controle operacional para uma plataforma integrada com **Gateway de Pagamento, ERP, estoque, logística e financeiro**, conforme definido no cenário **To-Be** da monografia.

---
title: "SaaS Social Media Manager (Automação + IA)"
excerpt: "Gestão de redes sociais com agenda, fila de publicação, rascunhos e sugestões por IA. Back-end Node/Prisma/PostgreSQL, front React SPA, orquestração n8n."
permalink: /projetos/saas-social-manager/
---

**Status:** em desenvolvimento/uso interno (sem repositório público)  
**Foco:** automação e inteligência para acelerar criação e publicação

### O que é
Desenvolvi um **SaaS para gerenciar redes sociais**: **agenda de postagens**, **fila de publicação**, **rascunhos** e **sugestões com IA** (legendas, hashtags, variações de texto).  
O **back-end (Node.js)** expõe **APIs REST** e persiste dados com **Prisma + PostgreSQL** (migrações e modelos versionados).  
O **front (React)** entrega **SPA responsiva**. **n8n** entra na orquestração (webhooks, checagem de horários, roteamento e **retries**). Projeto versionado em **Git/GitHub**, com branches e commits enxutos.

### Funcionalidades
- **Calendário/Agenda** por canal/perfil, com fuso horário.
- **Fila de publicação** (programado, rascunho, enviado, falhou).
- **Rascunhos** com revisão rápida e histórico.
- **Sugestões por IA**: legendas, hashtags e variações (tom/idioma).
- **Webhooks n8n** para disparo, reprocesso e re-tentativas.
- **Logs & métricas** básicas de publicação.

### Principais tecnologias
- **Back-end:** Node.js (Fastify/Express), **Prisma ORM**, **PostgreSQL**
- **Front-end:** **React** (SPA, Vite), React Query/axios
- **Orquestração:** **n8n** (webhooks, schedulers, retries)
- **Autenticação:** JWT, roles básicas
- **Infra/Dev:** Git/GitHub, `.env`, migrações Prisma

### Exemplos de endpoints
- `POST /posts` – cria rascunho  
- `PUT /posts/:id/schedule` – agenda (data/hora/fuso)  
- `GET /posts?status=scheduled` – lista programados  
- `POST /ai/suggest` – gera legenda/hashtags/variações  

### Fluxos no n8n
- **Scheduler** (cron): verifica posts programados e dispara publicação.  
- **Webhook**: recebe pedido de sugestão de IA → chama LLM → devolve texto.  
- **Retries**: reenvio automático em falha de API externa.

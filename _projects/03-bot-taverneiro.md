---
title: "Bot Taverneiro (Discord NPC)"
excerpt: "NPC de taverna para RPG: conversa natural, rumores/quests, rolagem de dados, contexto e integração n8n/LLM."
permalink: /projetos/bot-taverneiro/
---

**Status:** uso interno (sem repositório público) · **Stack:** Node.js, discord.js, n8n (webhooks), API de LLM

### O que é
Bot de Discord que simula um **taverneiro NPC** para mesas de RPG:
- conversa em linguagem natural com **persona** e **regras de segurança**;
- oferece **rumores/quests** e **rola dados**;
- mantém **contexto** da sessão (canal/jogador);
- integra com **n8n** para orquestração (webhooks, roteamento, logs);
- **rate limit** e handlers por comando/evento para evitar spam.

### Funcionalidades
- `/rumor` – gera boato/gancho coerente com o cenário
- `/quest` – cria missão curta com objetivo, obstáculo e recompensa
- `/roll 1d20+5` – rolagem com bônus e descrição
- **Contexto** por canal e jogador (memória curta)
- **Logs básicos** (join/leave, erros, uso de comandos)

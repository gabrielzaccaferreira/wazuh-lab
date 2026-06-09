
# 19 - Threat Hunting Playbook

# Objetivo

Este documento apresenta um conjunto de consultas e procedimentos para investigação de eventos utilizando o Wazuh Dashboard, simulando o trabalho de um Analista SOC/Blue Team.

---

# Cenário

Origem:

Kali Linux

↓

Suricata

↓

Wazuh Agent

↓

Wazuh Manager

↓

Dashboard

---

# Investigação 1

## Todos os eventos do Suricata

Consulta:

```
rule.groups:suricata
```

Objetivo:

Visualizar todos os eventos provenientes do IDS.

---

# Investigação 2

## Eventos do agente

Consulta:

```
agent.name:kali-linux
```

Objetivo:

Visualizar apenas eventos do agente Kali.

---

# Investigação 3

## Port Scan

Consulta:

```
rule.description:*PORT SCAN*
```

Objetivo:

Localizar atividades de reconhecimento.

---

# Investigação 4

## Eventos contendo NMAP

Consulta:

```
rule.description:*NMAP*
```

Objetivo:

Detectar varreduras realizadas pelo Nmap.

---

# Investigação 5

## Rule ID

Consulta:

```
rule.id:86601
```

Objetivo:

Visualizar eventos gerados pela regra Suricata Alert.

---

# Investigação 6

## Apenas alertas

Consulta:

```
event_type:alert
```

Objetivo:

Filtrar somente eventos classificados como alerta.

---

# Investigação 7

## Eventos do último período

Utilizar:

Last 15 minutes

Last 24 hours

Last 7 days

Objetivo:

Realizar análise temporal dos eventos.

---

# Processo de investigação

Recebimento do alerta

↓

Identificação do agente

↓

Análise da regra

↓

Validação do evento

↓

Correlação

↓

Determinação do impacto

↓

Documentação

↓

Resposta ao incidente

---

# Indicadores observados

- Port Scan
- Service Detection
- OS Detection
- Reconhecimento
- Eventos ICMP
- Eventos TCP

---

# Ferramentas utilizadas

- Wazuh Dashboard
- Suricata
- Nmap
- Linux
- Threat Hunting

---

# Conclusão

O laboratório permite executar atividades reais de Threat Hunting utilizando consultas direcionadas e correlação de eventos, simulando o fluxo operacional de uma equipe Blue Team.

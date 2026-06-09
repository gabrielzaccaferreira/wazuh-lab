
# 18 - Mapeamento MITRE ATT&CK

# Objetivo

Relacionar os eventos detectados pelo laboratório Wazuh + Suricata com as técnicas do framework MITRE ATT&CK.

---

# O que é MITRE ATT&CK

MITRE ATT&CK é uma base de conhecimento que documenta técnicas utilizadas por atacantes durante um incidente de segurança.

Ela é amplamente utilizada por:

- SOC
- Blue Team
- Threat Hunters
- Incident Response
- Threat Intelligence

---

# Cenário realizado

Atacante:

Kali Linux

↓

Nmap

↓

Ubuntu Server

↓

Suricata

↓

Wazuh

↓

Dashboard

---

# Técnica observada

## Reconnaissance

Objetivo:

Coletar informações sobre o alvo.

Exemplo:

```
sudo nmap -sS 192.168.218.129
```

---

## Active Scanning

Descrição:

Enumeração de serviços e portas abertas.

Framework:

MITRE ATT&CK

Técnica:

T1595

Nome:

Active Scanning

---

## Network Service Discovery

Exemplo:

```
sudo nmap -sV 192.168.218.129
```

Objetivo:

Identificar serviços disponíveis.

Relaciona-se à fase de descoberta do ambiente.

---

## System Information Discovery

Exemplo:

```
sudo nmap -O 192.168.218.129
```

Objetivo:

Identificar sistema operacional.

---

## Full Reconnaissance

Exemplo:

```
sudo nmap -A -Pn -sS -sV -O 192.168.218.129
```

Inclui:

- OS Detection
- Service Detection
- Script Scan
- Traceroute

---

# Detecção pelo Suricata

Exemplo:

```
POSSBL PORT SCAN (NMAP -sS)
```

SID:

```
3400002
```

Outro exemplo:

```
POSSBL PORT SCAN (NMAP -sX)
```

SID:

```
3400005
```

---

# Correlação pelo Wazuh

Rule:

```
86601
```

Descrição:

```
Suricata Alert
```

Grupo:

```
ids
suricata
```

---

# Fluxo de detecção

Reconhecimento

↓

Captura do tráfego

↓

Análise pelo Suricata

↓

Registro no eve.json

↓

Leitura pelo Wazuh Agent

↓

Processamento pelo Manager

↓

Visualização no Dashboard

---

# Benefícios

- Threat Hunting
- Correlação de eventos
- Investigação
- Resposta a incidentes
- Mapeamento MITRE

---

# Conclusão

O laboratório demonstra a capacidade de detectar atividades de reconhecimento de rede e correlacioná-las com técnicas do framework MITRE ATT&CK, simulando um cenário real de monitoramento por uma equipe Blue Team.

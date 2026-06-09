
# 16 - Detecção de Port Scan com Nmap

# Objetivo

Validar a capacidade do laboratório em detectar atividades de reconhecimento utilizando o Nmap e encaminhar os eventos para o Wazuh SIEM.

---

# Ambiente

Atacante:

- Kali Linux
- IP: 192.168.218.130

Alvo:

- Ubuntu Server
- Wazuh Manager
- IP: 192.168.218.129

---

# Ferramentas

- Nmap
- Suricata IDS
- Wazuh Agent
- Wazuh Manager
- Wazuh Dashboard

---

# Fluxo

Kali Linux

↓

Nmap

↓

Suricata

↓

eve.json

↓

Wazuh Agent

↓

Wazuh Manager

↓

Dashboard

---

# Testes realizados

## SYN Scan

```bash
sudo nmap -sS 192.168.218.129
```

---

## Service Detection

```bash
sudo nmap -sV 192.168.218.129
```

---

## OS Detection

```bash
sudo nmap -O 192.168.218.129
```

---

## Aggressive Scan

```bash
sudo nmap -A 192.168.218.129
```

---

## Scan completo

```bash
sudo nmap -A -Pn -sS -sV -O 192.168.218.129
```

---

# Alertas Suricata

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

# Eventos no Wazuh

Rule:

```
86601
```

Descrição:

```
Suricata Alert - POSSBL PORT SCAN (NMAP -sS)
```

Grupo:

```
ids
suricata
```

---

# Resultado

O laboratório foi capaz de:

- Detectar o scan
- Registrar no Suricata
- Enviar para o Wazuh
- Exibir no Dashboard
- Permitir Threat Hunting

---

# Conclusão

A integração Suricata + Wazuh encontra-se operacional e apta para monitoramento de atividades de reconhecimento em ambiente de laboratório.

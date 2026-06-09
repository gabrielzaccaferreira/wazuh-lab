
# 17 - Casos de Uso Reais do Laboratório

# Objetivo

Demonstrar cenários práticos de utilização do laboratório Wazuh + Suricata para atividades de monitoramento e detecção de ameaças.

---

# Caso 1 - Port Scan

## Ferramenta

Nmap

## Comando

```bash
sudo nmap -sS 192.168.218.129
```

## Objetivo do atacante

Descobrir portas abertas.

## Detecção

Suricata:

```
POSSBL PORT SCAN (NMAP -sS)
```

Wazuh:

```
Suricata Alert
```

---

# Caso 2 - Service Detection

## Comando

```bash
sudo nmap -sV 192.168.218.129
```

## Objetivo

Identificar serviços e versões.

## Resultado

Eventos registrados pelo Suricata e encaminhados ao Wazuh.

---

# Caso 3 - OS Detection

## Comando

```bash
sudo nmap -O 192.168.218.129
```

## Objetivo

Identificar o sistema operacional do alvo.

## Resultado

Atividade registrada pelo IDS.

---

# Caso 4 - Aggressive Scan

## Comando

```bash
sudo nmap -A 192.168.218.129
```

## Inclui

- OS Detection
- Version Detection
- Script Scan
- Traceroute

---

# Caso 5 - Full Recon

## Comando

```bash
sudo nmap -A -Pn -sS -sV -O 192.168.218.129
```

## Objetivo

Executar reconhecimento completo do host.

---

# Pipeline de Detecção

Atacante

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

↓

Threat Hunting

---

# Valor para Blue Team

O laboratório permite:

- Monitoramento de reconhecimento
- Correlação de eventos
- Investigação de incidentes
- Threat Hunting
- Geração de evidências

---

# Conclusão

Os cenários implementados simulam atividades comuns realizadas durante a fase de reconhecimento de um ataque e demonstram a integração funcional entre Suricata e Wazuh.

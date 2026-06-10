
# Incidente 001 - Detecção de Port Scan

# Resumo

Foi identificado um comportamento compatível com atividade de reconhecimento de rede utilizando a ferramenta Nmap.

O evento foi detectado pelo Suricata IDS e encaminhado ao Wazuh SIEM para correlação e análise.

---

# Data

Preencher

---

# Origem

192.168.218.130

Hostname:

kali-linux

---

# Destino

192.168.218.129

Hostname:

wazuh-server

---

# Ferramenta utilizada

Nmap

---

# Tipo de atividade

Reconnaissance

Port Scan

---

# Evidências

Suricata:

```
POSSBL PORT SCAN (NMAP -sS)
```

SID:

```
3400002
```

---

Dashboard:

```
Suricata Alert
```

---

# Classificação

Severidade:

Média

Categoria:

Reconhecimento

---

# MITRE ATT&CK

T1595

Active Scanning

---

# Impacto

O atacante tentou identificar serviços disponíveis no host.

Não houve exploração.

---

# Resposta

Nenhuma ação automática foi executada.

Evento registrado para investigação.

---

# Lições aprendidas

O laboratório demonstrou corretamente:

- Captura
- Correlação
- Visualização
- Threat Hunting

---

# Status

Encerrado

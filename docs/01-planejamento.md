
# Planejamento do Laboratório Wazuh

## Objetivo

Implementar um ambiente de monitoramento de segurança utilizando o Wazuh SIEM/XDR para aprendizado prático de:

- SIEM
- XDR
- SOC
- Blue Team
- Linux Administration
- Monitoramento de Logs
- File Integrity Monitoring (FIM)

---

## Ambiente

### Hypervisor

VMware Workstation

### Máquina 1

Ubuntu Server 24.04 LTS

Função:

- Wazuh Manager
- Wazuh Dashboard
- Wazuh Indexer
- Filebeat

Hostname:

```text
wazuh-server
```

IP:

```text
192.168.0.120
```

---

### Máquina 2

Kali Linux

Função:

- Wazuh Agent

---

## Recursos Utilizados

### Ubuntu Server

- 4 vCPU
- 8 GB RAM
- 70 GB Disco

### Kali Linux

- 4 vCPU
- 8 GB RAM
- 80 GB Disco

---

## Objetivos Futuros

- Integração Suricata
- Integração CrowdSec
- MITRE ATT&CK
- Vulnerability Detection
- Monitoramento SSH
- Regras Customizadas

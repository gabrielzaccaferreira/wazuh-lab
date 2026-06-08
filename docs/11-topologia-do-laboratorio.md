
# Topologia do Laboratório Wazuh SIEM/XDR

## Objetivo

Documentar a arquitetura geral do laboratório Wazuh SIEM/XDR, demonstrando como os componentes se comunicam dentro do ambiente virtualizado.

Este laboratório foi construído para estudos práticos de Redes, Infraestrutura, Segurança da Informação, SOC e Blue Team.

---

## Visão Geral do Ambiente

O laboratório foi executado em um host físico Dell OptiPlex utilizando VMware Workstation como plataforma de virtualização.

O ambiente é composto por três máquinas virtuais principais:

- Ubuntu Server com Wazuh Manager, Wazuh Indexer e Wazuh Dashboard
- Kali Linux com Wazuh Agent e Suricata IDS
- pfSense atuando como firewall e fonte de logs

---

## Host Físico

| Componente | Descrição |
|---|---|
| Equipamento | Dell OptiPlex |
| Processador | Intel Core i7-10700T |
| Memória RAM | 16 GB |
| Sistema Operacional | Windows 11 Pro |
| Hypervisor | VMware Workstation |

---

## Máquinas Virtuais

### Ubuntu Server - Wazuh Server

| Item | Valor |
|---|---|
| Sistema | Ubuntu Server 24.04 LTS |
| Hostname | wazuh-server |
| IP atual | 192.168.218.129 |
| Função | Wazuh Manager, Indexer, Dashboard e Filebeat |

---

### Kali Linux

| Item | Valor |
|---|---|
| Sistema | Kali Linux |
| Agente | Wazuh Agent |
| IDS | Suricata |
| Nome do agente | kali-linux |
| ID do agente | 001 |
| Status | Active |

---

### pfSense

| Item | Valor |
|---|---|
| Função | Firewall e roteamento |
| Hostname | soc-fw01.home.lab |
| Interface LAN | 192.168.220.254 |
| Integração | Envio de logs via Syslog para o Wazuh |

---

## Diagrama Lógico

```text
Notebook
   |
   | RDP
   v
Dell OptiPlex - Windows 11 Pro
   |
   | VMware Workstation
   |
   +-----------------------------+
   |                             |
   v                             v
Ubuntu Server                 Kali Linux
Wazuh Server                  Wazuh Agent
192.168.218.129               Suricata IDS
   ^                             |
   |                             |
   | Logs e alertas              | eve.json
   |                             v
   +------------------------- Wazuh Agent
                                 |
                                 v
                            Wazuh Manager
                                 |
                                 v
                            Wazuh Dashboard

pfSense Firewall
soc-fw01.home.lab
192.168.220.254
   |
   | Syslog
   v
Wazuh Server

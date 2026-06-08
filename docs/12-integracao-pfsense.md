
# Integração pfSense Firewall com Wazuh SIEM/XDR

## Objetivo

Documentar a integração do pfSense com o Wazuh SIEM/XDR, permitindo o envio, coleta, análise e visualização de eventos de firewall no Wazuh Dashboard.

Essa integração tem como objetivo aproximar o laboratório de um ambiente real de SOC/Blue Team, centralizando logs de rede, firewall e segurança em uma única plataforma.

---

## Ambiente Utilizado

### pfSense

| Item | Valor |
|---|---|
| Hostname | soc-fw01.home.lab |
| Função | Firewall |
| LAN | 192.168.220.254 |
| Envio de logs | Remote Syslog |

### Wazuh Server

| Item | Valor |
|---|---|
| Sistema | Ubuntu Server |
| IP atual | 192.168.218.129 |
| Funções | Wazuh Manager, Indexer, Dashboard e Filebeat |

---

## Arquitetura da Integração

```text
pfSense Firewall
     |
     | Syslog
     v
Ubuntu Server
     |
     | /var/log/pfsense.log
     v
Wazuh Manager
     |
     v
Wazuh Dashboard

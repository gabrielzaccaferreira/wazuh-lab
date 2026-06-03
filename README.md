
# Wazuh Lab - Ubuntu Server + Kali Linux

## Objetivo

Este projeto documenta a instalação, configuração e validação de um laboratório de SIEM/XDR utilizando o Wazuh em um ambiente virtualizado com Ubuntu Server e Kali Linux.

O objetivo é praticar conceitos de:

* Segurança da Informação
* Blue Team
* SOC
* SIEM
* XDR
* Linux Administration
* Monitoramento de Logs
* File Integrity Monitoring (FIM)

---

## Ambiente Utilizado

* VMware Workstation
* Ubuntu Server 24.04 LTS
* Kali Linux
* Wazuh 4.14.5
* OpenSSH
* Rede NAT

---

## Topologia

```text
VMware Workstation
│
├── Ubuntu Server
│   ├── Wazuh Manager
│   ├── Wazuh Indexer
│   ├── Wazuh Dashboard
│   └── Filebeat
│
└── Kali Linux
    └── Wazuh Agent
```

---

## Endereçamento

| Máquina       | Função       | IP            |
| ------------- | ------------ | ------------- |
| Ubuntu Server | Wazuh Server | 192.168.0.120 |
| Kali Linux    | Wazuh Agent  | DHCP          |

---

## Documentação

| Arquivo                 | Descrição                        |
| ----------------------- | -------------------------------- |
| 01-planejamento.md      | Planejamento do laboratório      |
| 02-instalacao-ubuntu.md | Instalação do Ubuntu Server      |
| 03-instalacao-wazuh.md  | Instalação do Wazuh              |
| 04-agente-kali.md       | Configuração do agente Kali      |
| 05-validacoes.md        | Validações realizadas            |
| 06-troubleshooting.md   | Problemas encontrados e soluções |
| 07-proximos-passos.md   | Roadmap do laboratório           |

---

## Status do Projeto

* [x] Ubuntu Server instalado
* [x] OpenSSH configurado
* [x] Wazuh instalado
* [x] Dashboard operacional
* [x] Agente Kali Linux conectado
* [x] Comunicação validada
* [ ] File Integrity Monitoring documentado
* [ ] Integração Suricata
* [ ] Integração CrowdSec

---

## Aprendizados Obtidos

Durante este laboratório foram praticados:

* Administração Linux
* VMware Workstation
* OpenSSH
* Redes TCP/IP
* SIEM
* XDR
* Wazuh
* Gestão de agentes
* Troubleshooting
* Monitoramento de eventos

---

## Tecnologias

* Ubuntu Server 24.04 LTS
* Kali Linux
* Wazuh 4.14.5
* OpenSSH
* VMware Workstation

---

## Evidências

As capturas de tela do laboratório serão armazenadas na pasta:

```text
evidencias/
```

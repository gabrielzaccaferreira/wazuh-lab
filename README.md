
# Wazuh SIEM/XDR Lab

## Laboratório Profissional de SIEM, IDS, Firewall e Threat Hunting

Este projeto documenta a construção completa de um laboratório voltado para estudos de:

* Redes de Computadores
* Infraestrutura
* Linux Administration
* SIEM
* IDS/IPS
* Blue Team
* SOC (Security Operations Center)
* Threat Hunting

Todo o ambiente foi desenvolvido em um laboratório próprio utilizando virtualização, integração entre ferramentas e documentação técnica detalhada.

---

# Objetivos

Este laboratório foi criado para:

* Compreender o funcionamento interno do Wazuh;
* Integrar diferentes fontes de eventos;
* Estudar monitoramento de segurança;
* Desenvolver habilidades em investigação de incidentes;
* Construir um portfólio técnico para atuação em Redes, Infraestrutura, Cloud e Cibersegurança.

---

# Arquitetura do Laboratório

```text
Notebook
        │
        │ RDP
        ▼

Dell OptiPlex
Windows 11 Pro

        │

VMware Workstation

        │
        ├─────────────────────────────┐
        │                             │
        ▼                             ▼

Ubuntu Server                  Kali Linux
Wazuh Server                   Wazuh Agent
                               Suricata IDS

        ▲                             │
        │                             │
        │                             ▼
        │                        eve.json
        │                             │
        └──────────────►──────────────┘
                       │
                       ▼

                 Wazuh Manager

                       │

                 Wazuh Indexer

                       │

                Wazuh Dashboard

                       ▲

                       │

                   pfSense Firewall
```

---

## Diagramas

Os diagramas técnicos do laboratório estão disponíveis em:

- [Topologia do Laboratório](diagrams/01-topologia.mmd)
- [Fluxo dos Eventos](diagrams/02-fluxo-eventos.mmd)
- [Arquitetura do Wazuh](diagrams/03-arquitetura-wazuh.mmd)
- [Pipeline de Alertas](diagrams/04-pipeline-alertas.mmd)

---

# Tecnologias Utilizadas

## Sistemas Operacionais

* Windows 11 Pro
* Ubuntu Server 24.04 LTS
* Kali Linux

---

## Virtualização

* VMware Workstation

---

## Segurança

* Wazuh
* Suricata
* pfSense

---

## Ferramentas

* Linux
* SSH
* RDP
* Git
* GitHub
* Syslog
* JSON Logs

---

# Estrutura do Projeto

```text
wazuh-lab/

├── configs/
├── diagrams/
├── docs/
├── evidencias/
├── LICENSE
└── README.md
```

---

# Documentação

## 01 - Planejamento

Planejamento completo do laboratório.

---

## 02 - Instalação do Ubuntu

Instalação e preparação do servidor.

---

## 03 - Instalação do Wazuh

Instalação do Manager, Dashboard e Indexer.

---

## 04 - Agente Kali

Instalação e configuração do agente.

---

## 05 - Validações

Testes realizados após a instalação.

---

## 06 - Troubleshooting

Problemas encontrados e respectivas soluções.

---

## 07 - Próximos Passos

Roadmap inicial do laboratório.

---

## 08 - Integração Suricata

Integração entre Suricata IDS e Wazuh.

---

## 09 - Validação Suricata + Wazuh

Validação prática dos eventos.

---

## 10 - Conclusão

Resultados obtidos.

---

## 11 - Topologia do Laboratório

Arquitetura completa do ambiente.

---

## 12 - Integração pfSense

Integração do firewall com o SIEM.

---

## 13 - Fluxo dos Eventos

Funcionamento interno do pipeline de eventos.

---

## 14 - Geração de Alertas

Validação do processo completo de geração e processamento de alertas.

---

## 15 - Threat Hunting

Utilização do laboratório para investigação de eventos e análise de ameaças.

---

# Competências Demonstradas

Este projeto evidencia conhecimentos práticos em:

* Linux Administration
* Redes de Computadores
* Virtualização
* SIEM
* IDS
* Firewall
* Log Management
* Troubleshooting
* Threat Hunting
* Blue Team
* SOC Operations

---

# Próximas Evoluções

* MITRE ATT&CK Mapping
* Sysmon para Windows
* Active Response
* Dashboards personalizados
* Threat Intelligence
* Casos reais de investigação

---

# Autor

Gabriel Zacca Ferreira

Estudante de Redes de Computadores com foco em Infraestrutura, Cloud Computing e Cibersegurança.

Este laboratório foi desenvolvido como projeto de estudo e evolução profissional, com documentação técnica completa e foco em boas práticas de monitoramento e defesa.

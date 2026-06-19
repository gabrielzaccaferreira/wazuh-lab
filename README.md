

## Sumário

- [Objetivos](#objetivos)
- [Arquitetura do Laboratório](#arquitetura-do-laboratório)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Documentação](#documentação)
- [Competências Demonstradas](#competências-demonstradas)
- [Próximas Evoluções](#próximas-evoluções)
- [Laboratórios do SOC Home Lab](#-laboratórios-do-soc-home-lab)

# 🛡️ Wazuh SIEM/XDR Lab

## SOC Home Lab • SIEM • Threat Hunting • Incident Response

---

> Projeto prático de Cibersegurança voltado para estudos de Blue Team, SOC, Threat Hunting e Incident Response, desenvolvido através de laboratórios reais, simulações de ataques e documentação técnica profissional.

---


# 📚 Sobre o Projeto

O **SOC Home Lab Enterprise** é um laboratório prático de Cibersegurança desenvolvido para simular o funcionamento de um Centro de Operações de Segurança (Security Operations Center - SOC), utilizando ferramentas amplamente adotadas no mercado e cenários reais de detecção e resposta a incidentes.

O projeto tem como objetivo aplicar conhecimentos de Redes de Computadores, Linux, Segurança da Informação, Threat Hunting e Incident Response por meio da implementação de laboratórios, simulações controladas de ataques e documentação técnica detalhada.

Diferentemente de um ambiente apenas voltado para instalação de ferramentas, este laboratório segue uma metodologia baseada no ciclo completo de uma investigação de segurança:

* Planejamento;
* Implementação;
* Simulação de ataques;
* Detecção;
* Investigação;
* Correlação de eventos;
* Mapeamento MITRE ATT&CK;
* Análise de IOC (Indicators of Compromise);
* Documentação técnica;
* Registro de Lessons Learned.

Todo o conteúdo é documentado em Markdown e versionado no GitHub, permitindo acompanhar a evolução do laboratório e a construção de um portfólio técnico voltado para atuação em Blue Team, SOC e Segurança da Informação.

---

# 🎯 Objetivos

Este projeto foi criado com os seguintes objetivos:

* Desenvolver experiência prática em Segurança da Informação;
* Aplicar conhecimentos de Redes de Computadores e Linux em cenários reais;
* Construir um ambiente completo de SOC (Security Operations Center) para estudos e pesquisas;
* Simular ataques controlados para validar mecanismos de detecção e resposta;
* Produzir documentação técnica baseada em metodologias utilizadas no mercado;
* Desenvolver competências em Threat Hunting, Incident Response e Detection Engineering;
* Construir um portfólio técnico público que demonstre conhecimento prático além de certificações e cursos.

## Objetivos específicos

Ao longo do projeto serão desenvolvidos laboratórios envolvendo:

* SIEM com Wazuh;
* IDS/IPS com Suricata;
* Threat Intelligence com CrowdSec;
* Simulações de ataques;
* Análise de logs;
* Mapeamento MITRE ATT&CK;
* IOC Analysis;
* Playbooks de resposta;
* Documentação de incidentes;
* Estudos de Blue Team e SOC.

---

# 🏗️ Arquitetura do Laboratório

O laboratório foi projetado para simular um ambiente de monitoramento e resposta a incidentes semelhante ao encontrado em operações de segurança (SOC).

## Componentes

### Host

* Dell OptiPlex
* Intel Core i7-10700T
* Windows 11
* VMware Workstation

### Máquina 1 — Ubuntu Server

Funções:

* Wazuh Manager
* Wazuh Indexer
* Wazuh Dashboard

Responsável por:

* Receber eventos
* Correlacionar logs
* Gerar alertas
* Disponibilizar dashboards para análise

### Máquina 2 — Kali Linux

Funções:

* Wazuh Agent
* Suricata IDS
* CrowdSec

Responsável por:

* Gerar eventos
* Detectar atividades suspeitas
* Enviar logs para o Wazuh
* Simular cenários ofensivos controlados

---

## Fluxo do ambiente

```text
Ataque Simulado
        │
        ▼
 Suricata IDS
        │
        ▼
 Wazuh Agent
        │
        ▼
 Wazuh Manager
        │
        ▼
 Wazuh Indexer
        │
        ▼
Wazuh Dashboard
        │
        ▼
Investigação
        │
        ▼
MITRE ATT&CK
        │
        ▼
IOC Analysis
        │
        ▼
Incident Report
```
---

# 🛠️ Tecnologias Utilizadas

Este laboratório utiliza ferramentas amplamente empregadas em ambientes corporativos de Segurança da Informação, Redes e Infraestrutura.

| Categoria                 | Tecnologia               |
| ------------------------- | ------------------------ |
| SIEM                      | Wazuh                    |
| IDS                       | Suricata                 |
| Threat Intelligence       | CrowdSec                 |
| Sistema Operacional       | Ubuntu Server 24.04 LTS  |
| Sistema Operacional       | Kali Linux Rolling       |
| Virtualização             | VMware Workstation       |
| Versionamento             | Git                      |
| Repositório               | GitHub                   |
| Linguagem de Documentação | Markdown                 |
| Protocolos                | TCP/IP, SSH, HTTP, HTTPS |
| Ferramentas de Análise    | Nmap, Linux Utilities    |

---

## Áreas de conhecimento aplicadas

Durante o desenvolvimento deste laboratório são praticados conhecimentos em:

* Linux Administration;
* Redes de Computadores;
* Infraestrutura;
* Segurança de Redes;
* SIEM;
* IDS/IPS;
* Threat Hunting;
* Incident Response;
* Detection Engineering;
* MITRE ATT&CK;
* IOC Analysis;
* Documentação Técnica.

---

# 📁 Estrutura do Projeto

O repositório está organizado de forma modular para facilitar a navegação, documentação e evolução contínua do laboratório.

```text
wazuh-lab/

├── assets/               # Recursos gráficos
├── attack-scenarios/     # Cenários de ataque simulados
├── configs/              # Arquivos de configuração
├── diagrams/             # Diagramas da arquitetura
├── docs/                 # Documentação técnica
├── evidencias/           # Evidências gerais do laboratório
├── incidents/            # Relatórios completos de incidentes
├── playbooks/            # Procedimentos de resposta
├── reports/              # Relatórios complementares
├── scripts/              # Scripts auxiliares
├── templates/            # Modelos de documentação
│
├── README.md
├── ROADMAP.md
├── CHANGELOG.md
└── LICENSE
```

## Organização

Cada incidente segue um padrão único de documentação:

```text
incidents/

└── 00X-nome-do-incidente/

      ├── README.md

      ├── timeline.md

      ├── iocs.md

      ├── mitre.md

      ├── lessons-learned.md

      ├── executive-summary.md

      └── evidencias/
```

Essa padronização facilita a reprodução dos estudos, a investigação dos cenários e a manutenção do projeto ao longo do tempo.

---

# 🧪 Attack Scenarios

O laboratório possui cenários de ataque controlados desenvolvidos para validar mecanismos de detecção, investigação e resposta a incidentes.

Cada cenário é executado em ambiente isolado e documentado de forma técnica, permitindo a reprodução dos testes e a análise completa dos eventos gerados.

| ID  | Cenário                            | Status       |
| --- | ---------------------------------- | ------------ |
| 001 | Port Scan Detection                | ✅ Concluído  |
| 002 | SSH Brute Force                    | ✅ Concluído  |
| 003 | Privilege Escalation Investigation | ✅ Concluído  |
| 004 | Web Attack Detection               | 🔄 Planejado |
| 005 | SQL Injection Detection            | 🔄 Planejado |
| 006 | Cross-Site Scripting (XSS)         | 🔄 Planejado |
| 007 | Reverse Shell Detection            | 🔄 Planejado |
| 008 | Persistence Techniques             | 🔄 Planejado |
| 009 | Malware Simulation                 | 🔄 Planejado |
| 010 | Threat Hunting Case Study          | 🔄 Planejado |

## Metodologia

Cada cenário segue um fluxo padronizado:

```text
Planejamento
        │
        ▼
Implementação
        │
        ▼
Simulação do Ataque
        │
        ▼
Detecção
        │
        ▼
Investigação
        │
        ▼
MITRE ATT&CK Mapping
        │
        ▼
IOC Analysis
        │
        ▼
Executive Summary
        │
        ▼
Lessons Learned
```

O objetivo é reproduzir situações semelhantes às encontradas em operações reais de Security Operations Center (SOC).

---

# 🚨 Incident Response

Um dos principais objetivos deste laboratório é desenvolver competências práticas em **Incident Response**, simulando o ciclo completo de investigação utilizado por equipes de Security Operations Center (SOC).

Cada incidente é documentado seguindo uma estrutura padronizada, permitindo rastreabilidade, reprodutibilidade e análise técnica detalhada.

## Estrutura dos incidentes

Cada diretório em `incidents/` contém:

* `README.md` — visão geral do incidente;
* `timeline.md` — sequência cronológica dos eventos;
* `iocs.md` — indicadores de comprometimento (IOCs);
* `mitre.md` — mapeamento para a matriz MITRE ATT&CK;
* `executive-summary.md` — resumo executivo;
* `lessons-learned.md` — aprendizados e recomendações;
* `evidencias/` — capturas de tela e evidências técnicas.

## Fluxo de resposta

```text
Detecção
      │
      ▼
Validação
      │
      ▼
Investigação
      │
      ▼
Correlação de Eventos
      │
      ▼
MITRE ATT&CK Mapping
      │
      ▼
IOC Analysis
      │
      ▼
Executive Summary
      │
      ▼
Lessons Learned
      │
      ▼
Documentação no GitHub
```

## Incidentes concluídos

| ID  | Incidente                          | Status |
| --- | ---------------------------------- | ------ |
| 001 | Port Scan Detection                | ✅      |
| 002 | SSH Brute Force                    | ✅      |
| 003 | Privilege Escalation Investigation | ✅      |

Cada novo incidente seguirá exatamente esta metodologia, mantendo um padrão profissional de documentação e investigação.

---

# 🎯 MITRE ATT&CK Coverage

Os laboratórios e incidentes desenvolvidos neste projeto são correlacionados com a matriz **MITRE ATT&CK**, permitindo relacionar cada atividade observada às táticas e técnicas utilizadas por adversários em ambientes reais.

O objetivo é compreender não apenas **como detectar um evento**, mas também **qual etapa do ciclo de ataque ele representa** e **quais técnicas estão sendo empregadas**.

## Táticas já praticadas

| Tática               | ID     | Status |
| -------------------- | ------ | ------ |
| Reconnaissance       | TA0043 | ✅      |
| Privilege Escalation | TA0004 | ✅      |

---

## Técnicas já praticadas

| Técnica                           | ID    | Status |
| --------------------------------- | ----- | ------ |
| Active Scanning                   | T1595 | ✅      |
| Abuse Elevation Control Mechanism | T1548 | ✅      |
| Process Discovery                 | T1057 | ✅      |
| Network Service Discovery         | T1046 | ✅      |

---

## Técnicas em evolução

* ✅ T1110 – Brute Force — praticado em cenários controlados de autenticação e logs SSH
* ✅ T1190 – Exploit Public-Facing Application — praticado em laboratório web com aplicação vulnerável
* ✅ T1059 – Command and Scripting Interpreter — observado em telemetria Windows/PowerShell
* 🔄 T1053 – Scheduled Task/Job
* 🔄 T1078 – Valid Accounts
* 🔄 T1105 – Ingress Tool Transfer
* 🔄 T1021 – Remote Services
* 🔄 T1003 – OS Credential Dumping

---

## Metodologia aplicada

Cada incidente desenvolvido neste laboratório segue o seguinte processo:

```text
Ataque Simulado
        │
        ▼
Detecção
        │
        ▼
Investigação
        │
        ▼
MITRE ATT&CK Mapping
        │
        ▼
IOC Analysis
        │
        ▼
Executive Summary
        │
        ▼
Lessons Learned
```

Dessa forma, o projeto busca alinhar a prática de laboratório com metodologias amplamente utilizadas por equipes de Security Operations Center (SOC), Blue Team e Incident Response.

---

# 📈 Roadmap

Este projeto está sendo desenvolvido de forma incremental, simulando a evolução de um ambiente real de Security Operations Center (SOC).

Cada fase possui objetivos técnicos específicos e gera documentação, evidências e incidentes completos.

---

## ✅ Fase 1 — Fundação do Laboratório

* Wazuh SIEM
* Suricata IDS
* CrowdSec
* Integração entre ferramentas
* Documentação inicial

**Status:** Concluída

---

## ✅ Fase 2 — Primeiros Incidentes

* Incident 001 — Port Scan Detection
* Incident 002 — SSH Brute Force
* Incident 003 — Privilege Escalation Investigation

**Status:** Concluída

---

## 🔄 Fase 3 — Authentication & Threat Hunting

* SSH Brute Force com Hydra
* Password Spraying
* Authentication Logs Analysis
* IOC Hunting
* Timeline Analysis

**Status:** Em planejamento

---

## 🔄 Fase 4 — Web Security

* Web Attack Detection
* SQL Injection
* Cross-Site Scripting (XSS)
* Web Server Log Analysis

**Status:** Planejado

---

## 🔄 Fase 5 — Detection Engineering

* Regras customizadas do Wazuh
* Regras Suricata
* Sigma Rules
* Decoders
* Dashboards

**Status:** Planejado

---

## 🔄 Fase 6 — Incident Response & DFIR

* Reverse Shell Detection
* Persistence Techniques
* Malware Simulation
* Threat Hunting Case Studies

**Status:** Planejado

---

## 🔄 Fase 7 — Cloud Security

* Microsoft Azure
* AWS
* IAM
* Cloud Logs
* Cloud Security Monitoring

**Status:** Planejado

---

## Objetivo Final

Construir um laboratório completo voltado para:

* Blue Team;
* Security Operations Center (SOC);
* Threat Hunting;
* Detection Engineering;
* Incident Response;
* Infraestrutura e Segurança de Redes.

Toda a evolução do projeto será documentada e publicada neste repositório.

---

# 🏆 Competências Desenvolvidas

Este laboratório foi projetado para desenvolver competências práticas aplicadas às áreas de Redes, Infraestrutura e Cibersegurança, simulando atividades realizadas por equipes de Security Operations Center (SOC).

## Segurança da Informação

* Incident Response
* Threat Hunting
* IOC Analysis
* MITRE ATT&CK Mapping
* Detection Engineering
* Security Monitoring
* Log Analysis

---

## Redes e Infraestrutura

* TCP/IP
* SSH
* Serviços de Rede
* Análise de Portas
* Troubleshooting
* Comunicação entre Hosts
* Arquitetura de Redes

---

## Linux Administration

* Gerenciamento de usuários e grupos
* Permissões e privilégios
* SUID e Linux Capabilities
* Processos e serviços
* Cron Jobs
* Auditoria de sistemas
* Administração de servidores

---

## Ferramentas

* Wazuh SIEM
* Suricata IDS
* CrowdSec
* Nmap
* Git
* GitHub
* VMware Workstation

---

## Documentação Técnica

Cada cenário desenvolvido contempla:

* Planejamento;
* Simulação controlada;
* Investigação;
* Timeline;
* IOC Analysis;
* MITRE ATT&CK Mapping;
* Executive Summary;
* Lessons Learned;
* Registro de evidências.

---

## Competências Profissionais

Ao final deste projeto, o objetivo é consolidar experiência prática em:

* Blue Team;
* Security Operations Center (SOC);
* Incident Response;
* Threat Hunting;
* Detection Engineering;
* Administração Linux;
* Segurança de Redes;
* Documentação Técnica;
* Versionamento com Git e GitHub.

---

# 🚀 Próximos Passos

O desenvolvimento deste laboratório é contínuo e tem como objetivo expandir gradualmente os cenários de detecção, investigação e resposta a incidentes, aproximando o ambiente de uma operação real de Security Operations Center (SOC).

## Evolução planejada

Nos próximos módulos serão implementados novos laboratórios envolvendo:

* Web Attack Detection;
* SQL Injection;
* Cross-Site Scripting (XSS);
* Reverse Shell Detection;
* Malware Simulation;
* Persistence Techniques;
* Lateral Movement;
* Threat Hunting Case Studies;
* Detection Engineering;
* Sigma Rules;
* YARA Rules;
* Cloud Security;
* Active Directory Security;
* Windows Event Analysis;
* Sysmon Integration.

---

## Filosofia do projeto

Cada novo cenário seguirá uma metodologia padronizada:

```text
Planejamento
        │
        ▼
Implementação
        │
        ▼
Simulação
        │
        ▼
Detecção
        │
        ▼
Investigação
        │
        ▼
MITRE ATT&CK
        │
        ▼
IOC Analysis
        │
        ▼
Executive Summary
        │
        ▼
Lessons Learned
        │
        ▼
Publicação
```

---

## Objetivo de longo prazo

Transformar este repositório em uma referência pessoal de estudos práticos em:

* Redes de Computadores;
* Infraestrutura;
* Segurança da Informação;
* Blue Team;
* Security Operations Center (SOC);
* Threat Hunting;
* Incident Response;
* Detection Engineering.

Todo o desenvolvimento será documentado de forma transparente, permitindo acompanhar a evolução técnica do projeto e das competências adquiridas ao longo do tempo.

---

# ⭐ Projeto em evolução contínua

Este laboratório representa uma jornada prática de aprendizado e melhoria contínua. Novos incidentes, playbooks, automações e estudos serão adicionados regularmente para ampliar a cobertura técnica e aproximar o ambiente de cenários encontrados em operações reais de segurança.

---




---

## 🔗 Laboratórios do SOC Home Lab

| Lab | Repositório | Descrição |
|-----|-------------|-----------|
| 🛡️ Wazuh SIEM/XDR | [wazuh-lab](https://github.com/gabrielzaccaferreira/wazuh-lab) | Instalação, configuração e regras customizadas do Wazuh |
| 🐉 Kali Linux | [kali-remote-access-lab](https://github.com/gabrielzaccaferreira/kali-remote-access-lab) | Setup do ambiente de ataque e acesso remoto |
| 🔍 Suricata IDS/IPS | [suricata-lab](https://github.com/gabrielzaccaferreira/suricata-lab) | Detecção de intrusão em rede, regras customizadas |
| 🛡️ CrowdSec | [soc-lab-crowdsec-kali](https://github.com/gabrielzaccaferreira/soc-lab-crowdsec-kali) | IPS colaborativo com blocklists dinâmicas |
| 🔬 Wireshark | [wireshark-analysis-lab](https://github.com/gabrielzaccaferreira/wireshark-analysis-lab) | Análise de tráfego e dissecção de protocolos |
| 🔥 pfSense | [pfsense-lab](https://github.com/gabrielzaccaferreira/pfsense-lab) | Firewall, NAT, VLANs e regras de perímetro |
| 🪟 Windows Server + Sysmon | [windows-server-soc-lab](https://github.com/gabrielzaccaferreira/windows-server-soc-lab) | Telemetria Windows, Sysmon, Red Team vs Blue Team |

> 🌐 Portfólio completo: [gabrielzacca.com.br](https://gabrielzacca.com.br)


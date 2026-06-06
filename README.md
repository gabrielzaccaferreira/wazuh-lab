]
# Wazuh SIEM/XDR Lab

## Sobre o Projeto

Este repositório documenta a implementação de um laboratório prático de **SIEM/XDR utilizando o Wazuh**, desenvolvido com o objetivo de aprofundar conhecimentos em Redes de Computadores, Infraestrutura, Linux e Segurança da Informação.

O ambiente foi construído em máquinas virtuais e contempla desde a instalação dos componentes até a integração com o **Suricata IDS**, permitindo a centralização e análise de eventos de segurança em um único Dashboard.

---

# Objetivos

* Compreender a arquitetura do Wazuh
* Implementar um ambiente SIEM funcional
* Integrar agentes Linux ao Manager
* Centralizar logs de segurança
* Realizar Threat Hunting
* Validar Vulnerability Detection
* Validar Security Configuration Assessment (SCA)
* Integrar o Suricata IDS ao Wazuh

---

# Arquitetura do Laboratório

```text
                    Internet
                        │
                        ▼
                 Suricata IDS
                        │
                        ▼
                   eve.json
                        │
                        ▼
                 Wazuh Agent
                  (Kali Linux)
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
                Threat Hunting
```

---

# Ambiente

## Host

* Dell OptiPlex
* Intel Core i7-10700T
* Windows 11
* VMware Workstation

---

## Ubuntu Server

Funções:

* Wazuh Manager
* Wazuh Indexer
* Wazuh Dashboard

---

## Kali Linux

Funções:

* Wazuh Agent
* Suricata IDS

---

# Tecnologias Utilizadas

* Linux
* Ubuntu Server
* Kali Linux
* VMware Workstation
* Wazuh
* Suricata
* JSON
* Git
* GitHub
* SIEM
* IDS
* Threat Hunting

---

# Estrutura do Projeto

```text
wazuh-lab/

├── configs/
│
├── diagrams/
│
├── docs/
│   ├── 01-planejamento.md
│   ├── 02-instalacao-ubuntu.md
│   ├── 03-instalacao-wazuh.md
│   ├── 04-agente-kali.md
│   ├── 05-validacoes.md
│   ├── 06-troubleshooting.md
│   ├── 07-proximos-passos.md
│   ├── 08-integracao-suricata.md
│   ├── 09-validacao-suricata-wazuh.md
│   └── 10-conclusao.md
│
├── evidencias/
│   ├── 01-dashboard-home.png
│   ├── 02-services-running.png
│   ├── 03-agent-active.png
│   ├── 04-security-events.png
│   └── 05-sca.png
│
├── .gitignore
│
└── README.md
```


# Documentação

Toda a implementação do laboratório foi documentada de forma cronológica, permitindo reproduzir cada etapa do ambiente.

| Documento                        | Descrição                                          |
| -------------------------------- | -------------------------------------------------- |
| `01-planejamento.md`             | Planejamento inicial do laboratório                |
| `02-instalacao-ubuntu.md`        | Instalação e configuração do Ubuntu Server         |
| `03-instalacao-wazuh.md`         | Instalação do Wazuh Manager, Indexer e Dashboard   |
| `04-agente-kali.md`              | Configuração e registro do agente Kali Linux       |
| `05-validacoes.md`               | Testes e validações do ambiente                    |
| `06-troubleshooting.md`          | Problemas encontrados e respectivas soluções       |
| `07-proximos-passos.md`          | Planejamento de evolução do laboratório            |
| `08-integracao-suricata.md`      | Integração do Suricata IDS com o Wazuh             |
| `09-validacao-suricata-wazuh.md` | Validação da integração e análise dos resultados   |
| `10-conclusao.md`                | Conclusão e aprendizados obtidos durante o projeto |

---

# Funcionalidades Validadas

* ✅ Wazuh Manager
* ✅ Wazuh Dashboard
* ✅ Wazuh Indexer
* ✅ Agente Kali Linux
* ✅ Threat Hunting
* ✅ Vulnerability Detection
* ✅ Security Configuration Assessment (SCA)
* ✅ Integração Suricata + Wazuh
* ✅ Coleta e correlação de eventos

---

# Evidências

O projeto contém capturas de tela demonstrando:

* Dashboard principal
* Agente ativo
* Threat Hunting
* Security Events
* Security Configuration Assessment
* Alertas do Suricata
* Validação dos serviços

As imagens estão disponíveis no diretório:

```text
evidencias/
```

---

# Principais Aprendizados

Durante o desenvolvimento deste laboratório foi possível compreender na prática:

* Arquitetura SIEM
* Arquitetura IDS
* Coleta e centralização de logs
* Correlação de eventos
* Investigação inicial de incidentes
* Monitoramento contínuo
* Documentação técnica
* Versionamento com Git e GitHub

---

# Competências Desenvolvidas

Durante a implementação deste laboratório foram desenvolvidas e praticadas competências técnicas relacionadas às áreas de Redes, Infraestrutura e Segurança da Informação, incluindo:

* Linux Administration
* Ubuntu Server
* Kali Linux
* Virtualização com VMware Workstation
* Wazuh SIEM/XDR
* Suricata IDS
* Threat Hunting
* Security Monitoring
* Vulnerability Detection
* Security Configuration Assessment (SCA)
* Log Analysis
* Event Correlation
* File Integrity Monitoring (FIM)
* Troubleshooting
* Git
* GitHub
* Documentação Técnica
* Arquitetura de SIEM
* Arquitetura de IDS
* Monitoramento de Eventos de Segurança

---

## Roadmap do Laboratório

### ✅ Fase 1 — Infraestrutura

* [x] Instalação do Ubuntu Server
* [x] Configuração do ambiente virtualizado
* [x] Instalação do Wazuh

---

### ✅ Fase 2 — Monitoramento

* [x] Configuração do Wazuh Manager
* [x] Configuração do Wazuh Dashboard
* [x] Configuração do Wazuh Indexer
* [x] Registro do agente Kali Linux

---

### ✅ Fase 3 — Validações

* [x] Threat Hunting
* [x] Vulnerability Detection
* [x] Security Configuration Assessment (SCA)
* [x] Coleta de eventos do sistema

---

### ✅ Fase 4 — Integração IDS

* [x] Instalação do Suricata
* [x] Geração do `eve.json`
* [x] Integração Suricata + Wazuh
* [x] Visualização de eventos no Dashboard

---

### 🔄 Próximas Evoluções

* [ ] Active Response
* [ ] Regras customizadas do Wazuh
* [ ] Simulação de ataques controlados
* [ ] Integração com outras ferramentas de segurança
* [ ] Mapeamento MITRE ATT&CK
* [ ] Evolução para um Home SOC completo

---

# Objetivo Profissional

Este laboratório faz parte da minha jornada de especialização em:

* Redes de Computadores
* Infraestrutura
* Cloud Computing
* Segurança da Informação
* SOC / Blue Team

com foco na construção de um portfólio técnico baseado em projetos práticos e documentação detalhada.

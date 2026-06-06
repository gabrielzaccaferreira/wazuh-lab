
# 10 - Conclusão do Laboratório Wazuh SIEM/XDR

# Resumo do Projeto

Este laboratório teve como objetivo implementar e compreender o funcionamento de uma plataforma SIEM utilizando o Wazuh, desde sua instalação até a integração com um sistema IDS (Suricata).

Durante o desenvolvimento foram realizados processos de instalação, configuração, validação e troubleshooting, permitindo compreender o fluxo completo de coleta, processamento e visualização de eventos de segurança.

---

# Ambiente Implementado

## Host

* Dell OptiPlex
* Intel Core i7-10700T
* Windows 11
* VMware Workstation

---

## Máquina Virtual 1

### Ubuntu Server

Funções:

* Wazuh Manager
* Wazuh Indexer
* Wazuh Dashboard

---

## Máquina Virtual 2

### Kali Linux

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
* SIEM
* IDS
* Threat Hunting

---

# Fluxo de Funcionamento

```text
Tráfego de Rede
        │
        ▼
Suricata IDS
        │
        ▼
eve.json
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
Threat Hunting
```

---

# Objetivos Alcançados

Durante o laboratório foi possível:

* Instalar o Wazuh Manager
* Configurar o Dashboard
* Configurar o Indexer
* Registrar o agente Kali Linux
* Validar a comunicação entre agente e servidor
* Monitorar eventos do sistema operacional
* Utilizar o módulo Threat Hunting
* Validar Vulnerability Detection
* Validar Security Configuration Assessment (SCA)
* Integrar o Suricata ao ambiente
* Centralizar eventos em uma plataforma SIEM

---

# Aprendizados Obtidos

Este laboratório proporcionou conhecimentos práticos sobre:

* Arquitetura SIEM
* Arquitetura IDS
* Centralização de logs
* Correlação de eventos
* Monitoramento de segurança
* Análise de eventos
* Investigação inicial de incidentes
* Funcionamento de um ambiente SOC

Além dos aspectos técnicos, o projeto reforçou boas práticas de documentação, versionamento utilizando Git/GitHub e organização de evidências.

---

# Próximos Passos

O laboratório continuará evoluindo com novas integrações e funcionalidades, incluindo:

* Regras customizadas do Wazuh
* Active Response
* Integração com outras ferramentas de segurança
* Simulação de ataques controlados
* Mapeamento de técnicas MITRE ATT&CK
* Automação e orquestração de respostas

---

# Conclusão

Ao final deste projeto foi possível construir um ambiente funcional de monitoramento de segurança, integrando uma solução IDS com uma plataforma SIEM para coleta, análise e investigação de eventos.

Mais do que instalar ferramentas, o laboratório permitiu compreender o fluxo operacional utilizado em ambientes reais de Segurança da Informação e SOC, servindo como base para estudos avançados em Blue Team, Threat Hunting e Resposta a Incidentes.


# Fluxo dos Eventos no Laboratório Wazuh SIEM/XDR

# Objetivo

Este documento descreve o fluxo completo dos eventos dentro do laboratório Wazuh SIEM/XDR, desde sua geração até sua visualização no Dashboard.

O objetivo é compreender como cada componente participa do processo de coleta, transporte, processamento, indexação e apresentação das informações de segurança.

---

# Arquitetura Geral

O laboratório foi construído para simular um ambiente real de Security Operations Center (SOC), centralizando eventos provenientes de diferentes fontes.

Fluxo geral:

```text
Dispositivo/Serviço
        │
        ▼
 Geração do Evento
        │
        ▼
 Coleta do Log
        │
        ▼
 Wazuh Agent
        │
        ▼
 Wazuh Manager
        │
        ▼
 Decoders
        │
        ▼
 Rules Engine
        │
        ▼
 Wazuh Indexer
        │
        ▼
 Wazuh Dashboard
        │
        ▼
 Analista SOC
```

---

# Fluxo dos Eventos do Suricata

O Suricata é responsável por analisar o tráfego de rede e identificar comportamentos suspeitos.

Quando uma regra é acionada, um evento é registrado no arquivo:

```text
/var/log/suricata/eve.json
```

Fluxo:

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
   Wazuh Dashboard
```

---

# Fluxo dos Eventos do pfSense

O pfSense atua como firewall do laboratório e gera eventos relacionados a:

* Firewall
* DHCP
* Sistema
* Rede

Esses eventos são enviados via Syslog.

Fluxo:

```text
pfSense
      │
      ▼
 Remote Syslog
      │
      ▼
 Ubuntu Server
      │
      ▼
 Wazuh Manager
      │
      ▼
 Wazuh Dashboard
```

---

# Fluxo dos Eventos do Wazuh Agent

O agente instalado no Kali monitora:

* Arquivos
* Processos
* Logs
* Informações do sistema
* Comandos configurados

Fluxo:

```text
Sistema Operacional
        │
        ▼
   Wazuh Agent
        │
        ▼
   Comunicação TCP
        │
        ▼
 Wazuh Manager
```

---

# Processamento pelo Wazuh Manager

Após receber os eventos, o Manager executa diversas etapas:

1. Recebimento do evento

↓

2. Identificação da origem

↓

3. Aplicação dos decoders

↓

4. Aplicação das regras

↓

5. Definição do nível de severidade

↓

6. Encaminhamento ao Indexer

---

# Decoders

Os decoders interpretam o formato do log recebido.

Exemplo:

```text
Log bruto

↓

Decoder

↓

Campos estruturados
```

São responsáveis por identificar:

* programa
* origem
* IP
* usuário
* mensagem

---

# Rules Engine

Após o decoder, o mecanismo de regras verifica:

* assinatura
* severidade
* grupo
* categoria
* nível de risco

Exemplo:

```text
Evento

↓

Rule ID

↓

Level

↓

Descrição
```

---

# Indexação

Depois do processamento, o evento é enviado ao Wazuh Indexer.

Funções:

* armazenamento
* pesquisa
* agregação
* estatísticas
* consultas

---

# Dashboard

O Dashboard consulta o Indexer e apresenta:

* agentes
* alertas
* eventos
* gráficos
* filtros
* Threat Hunting

---

# Fluxo Completo

```text
Usuário

↓

Rede

↓

pfSense

↓

Suricata

↓

eve.json

↓

Wazuh Agent

↓

Wazuh Manager

↓

Decoders

↓

Rules

↓

Indexer

↓

Dashboard

↓

Analista SOC
```

---

# Benefícios

Esta arquitetura permite:

* Centralização dos logs
* Correlação de eventos
* Monitoramento contínuo
* Investigação de incidentes
* Threat Hunting
* Operação de SOC
* Blue Team

---

# Conclusão

O laboratório implementa um fluxo completo de processamento de eventos semelhante ao encontrado em ambientes corporativos, permitindo estudar a integração entre firewall, IDS, agentes e SIEM, além de praticar análise e correlação de eventos de segurança em uma arquitetura moderna.


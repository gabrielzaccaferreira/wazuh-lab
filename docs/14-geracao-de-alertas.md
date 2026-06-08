
# Geração e Validação de Alertas no Laboratório Wazuh SIEM/XDR

# Objetivo

Este documento tem como objetivo demonstrar o processo de geração, coleta, processamento e validação de alertas dentro do laboratório Wazuh SIEM/XDR.

Mais do que instalar as ferramentas, este laboratório foi construído para validar que os eventos realmente percorrem todo o fluxo de monitoramento até serem apresentados ao analista de segurança.

---

# Importância da Geração de Alertas

Em um ambiente SOC, não basta que um SIEM esteja instalado. É necessário comprovar que:

* Os eventos são gerados;
* Os logs são coletados corretamente;
* Os agentes conseguem enviar informações ao Manager;
* Os decoders interpretam os eventos;
* As regras classificam os alertas;
* Os eventos chegam ao Dashboard para análise.

Este documento registra essas validações.

---

# Arquitetura do Fluxo

```text
Evento

↓

Sistema Monitorado

↓

Suricata / pfSense / Sistema Operacional

↓

Wazuh Agent

↓

Wazuh Manager

↓

Decoders

↓

Rules Engine

↓

Indexer

↓

Dashboard

↓

Analista SOC
```

---

# Componentes Envolvidos

## Wazuh Manager

Responsável por:

* Receber eventos;
* Aplicar decoders;
* Aplicar regras;
* Classificar severidade;
* Encaminhar dados ao Indexer.

---

## Wazuh Agent

Responsável por:

* Monitoramento do sistema;
* Coleta de logs;
* Leitura do arquivo `eve.json`;
* Comunicação com o Manager.

---

## Suricata IDS

Responsável por analisar o tráfego de rede e registrar eventos no arquivo:

```text
/var/log/suricata/eve.json
```

---

## pfSense

Responsável pela geração de eventos relacionados a:

* Firewall;
* DHCP;
* Sistema;
* Rede.

---

# Eventos Validados

Durante a construção do laboratório foram observados eventos provenientes de diferentes fontes.

## Eventos do Suricata

Exemplo:

```text
Suricata: Alert - ET INFO Possible Kali Linux hostname in DHCP Request Packet
```

Características:

* Agente: kali-linux
* Origem: Suricata IDS
* Visualização: Wazuh Dashboard

---

## Eventos do Wazuh Agent

Após a correção da configuração de rede, o agente estabeleceu comunicação com o servidor.

Validação observada:

```text
Connected to the server
```

Status:

```text
Agent: Active
```

---

## Eventos do pfSense

Os eventos enviados pelo firewall foram recebidos pelo Wazuh para posterior correlação e análise.

Entre eles:

* Firewall Events;
* DHCP Events;
* System Events.

---

# Problema Encontrado

Durante a implantação, o agente não conseguia se comunicar com o servidor.

Mensagem observada:

```text
Unable to connect to server
```

Causa:

O endereço configurado no agente apontava para um IP incorreto.

Configuração anterior:

```text
192.168.220.129
```

Configuração correta:

```text
192.168.218.129
```

Após a correção, a comunicação foi restabelecida.

---

# Validação da Comunicação

O log do agente apresentou:

```text
Trying to connect to server

↓

Connected to the server
```

No Manager, o agente passou a aparecer como:

```text
ID: 001

Name: kali-linux

Status: Active
```

---

# Validação no Dashboard

Os eventos passaram a ser exibidos no Wazuh Dashboard, permitindo:

* Consulta dos alertas;
* Identificação da origem;
* Classificação por regras;
* Análise de severidade;
* Investigação dos eventos.

---

# Fluxo Completo Validado

```text
Tráfego

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
```

---

# Lições Aprendidas

Durante esta etapa foi possível compreender:

* A importância da comunicação entre agente e Manager;
* O funcionamento do processo de coleta de logs;
* O papel dos decoders e regras;
* O fluxo interno do Wazuh;
* A integração entre IDS, firewall e SIEM;
* A necessidade de validar cada etapa do pipeline de eventos.

---

# Próximos Testes

Para evolução do laboratório, estão previstos:

* Geração controlada de eventos utilizando Nmap;
* Testes de varredura de portas;
* Simulação de tentativas de acesso;
* Correlação entre múltiplas fontes de eventos;
* Estudos de Threat Hunting;
* Mapeamento para MITRE ATT&CK.

---

# Conclusão

A geração e validação de alertas confirmou que o laboratório está operacional e capaz de receber, processar e apresentar eventos de segurança provenientes de diferentes componentes da infraestrutura.

Essa validação demonstra que o ambiente está apto para estudos avançados de SIEM, SOC, Blue Team, Threat Hunting e Resposta a Incidentes.

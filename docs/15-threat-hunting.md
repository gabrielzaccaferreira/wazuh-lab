
# Threat Hunting no Laboratório Wazuh SIEM/XDR

# Objetivo

Este documento apresenta a metodologia de Threat Hunting aplicada ao laboratório Wazuh SIEM/XDR desenvolvido neste projeto.

O objetivo é demonstrar como utilizar os eventos coletados pelo SIEM para investigar atividades suspeitas, correlacionar informações e identificar possíveis ameaças de forma proativa.

---

# O que é Threat Hunting?

Threat Hunting é o processo de busca ativa por indicadores de comprometimento (IOCs) e comportamentos anômalos dentro de um ambiente monitorado.

Diferentemente do monitoramento tradicional, o Threat Hunting não espera apenas por alertas automáticos, mas procura evidências que possam indicar uma ameaça ainda não identificada.

---

# Monitoramento x Threat Hunting

## Monitoramento

Fluxo:

```text
Evento

↓

Regra

↓

Alerta

↓

Analista
```

O analista reage ao alerta gerado.

---

## Threat Hunting

Fluxo:

```text
Hipótese

↓

Coleta de dados

↓

Investigação

↓

Correlação

↓

Conclusão
```

O analista parte de uma hipótese e busca evidências.

---

# Arquitetura do Laboratório

```text
Usuário

↓

Rede

↓

pfSense

↓

Suricata IDS

↓

eve.json

↓

Wazuh Agent

↓

Wazuh Manager

↓

Indexer

↓

Dashboard

↓

Threat Hunting
```

---

# Fontes de Dados

Durante as investigações, o laboratório disponibiliza informações provenientes de diversas fontes:

## pfSense

* Eventos de firewall
* DHCP
* Sistema

---

## Suricata

* Alertas IDS
* Eventos de rede
* Assinaturas ET Open

---

## Wazuh Agent

* Informações do sistema
* Integridade de arquivos
* Logs monitorados
* Inventário do sistema

---

# Processo de Investigação

Todo processo de Threat Hunting deve seguir uma metodologia.

```text
Receber evento

↓

Validar origem

↓

Identificar agente

↓

Analisar regra

↓

Correlacionar eventos

↓

Confirmar ou descartar hipótese

↓

Documentar resultado
```

---

# Exemplos de Hipóteses

## Hipótese 1

Existe atividade de varredura de portas na rede.

Investigar:

* Eventos do Suricata
* Logs do firewall
* Origem do IP
* Frequência

---

## Hipótese 2

Um host iniciou comportamento incomum.

Investigar:

* Processos
* Serviços
* Alterações recentes
* Eventos correlacionados

---

## Hipótese 3

Existe tentativa de comunicação não autorizada.

Investigar:

* Conexões
* Portas
* Destino
* Histórico

---

# Consultas Úteis

Pesquisar por agente:

```text
agent.name:kali-linux
```

---

Pesquisar eventos do Suricata:

```text
rule.groups:suricata
```

---

Pesquisar eventos do pfSense:

```text
rule.groups:pfsense
```

---

Pesquisar eventos críticos:

```text
rule.level>=5
```

---

Pesquisar por IP de origem:

```text
data.srcip:*
```

---

Pesquisar por IP de destino:

```text
data.dstip:*
```

---

# Fluxo de Análise

```text
Evento

↓

Decoder

↓

Rule

↓

Level

↓

Dashboard

↓

Threat Hunting

↓

Resposta
```

---

# Boas Práticas

Durante uma investigação:

* Não tirar conclusões precipitadas;
* Correlacionar múltiplas evidências;
* Verificar histórico;
* Identificar falso positivo;
* Documentar todas as etapas.

---

# Aplicação no Laboratório

O laboratório permite realizar estudos de:

* Investigação de alertas IDS;
* Correlação entre Suricata e Wazuh;
* Análise de eventos do firewall;
* Validação de agentes;
* Estudos de comportamento de rede;
* Simulação de cenários SOC.

---

# Próximas Evoluções

O laboratório poderá ser expandido com:

* Sysmon para Windows;
* MITRE ATT&CK Mapping;
* Active Response;
* Regras customizadas;
* Dashboards específicos;
* Integração com Threat Intelligence.

---

# Conclusão

O Threat Hunting transforma o laboratório em um ambiente de investigação de segurança, permitindo desenvolver habilidades práticas de análise, correlação de eventos e resposta a incidentes.

Essa abordagem aproxima o projeto de cenários encontrados em Centros de Operações de Segurança (SOC) e fortalece competências essenciais para atuação em Redes, Infraestrutura e Cibersegurança.

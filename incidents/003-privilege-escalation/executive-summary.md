
# Executive Summary - Incident 003

## Visão Geral

Foi realizada uma investigação de segurança com foco na identificação de possíveis vetores de Privilege Escalation em um ambiente Linux utilizado para estudos de Segurança da Informação, Blue Team e Incident Response.

A análise consistiu na enumeração completa do sistema operacional, usuários, grupos, permissões administrativas, binários privilegiados, Linux Capabilities, tarefas agendadas, processos ativos, serviços de rede e possíveis mecanismos de persistência.

---

## Classificação

- Tipo de incidente: Investigação de Privilege Escalation
- Severidade: Baixa
- Status: Concluído
- Ambiente: Laboratório controlado

---

## Escopo da investigação

Foram realizadas verificações envolvendo:

- Usuário e grupos do sistema;
- Permissões administrativas (`sudo`);
- Binários SUID;
- Linux Capabilities;
- Diretórios e arquivos World Writable;
- Cron Jobs;
- Processos ativos;
- Portas abertas e conexões de rede;
- Binários frequentemente utilizados em técnicas de Privilege Escalation (GTFOBins).

---

## Evidências

Durante a investigação:

- Não foram encontrados binários SUID incomuns;
- Não foram identificadas Linux Capabilities inseguras;
- Não foram encontrados arquivos World Writable críticos;
- Não foram identificados mecanismos de persistência através de Cron;
- Não foram observados processos suspeitos;
- Não foram detectados listeners ou conexões compatíveis com backdoors ou reverse shells.

Os serviços encontrados foram compatíveis com o ambiente de laboratório:

- SSH
- XRDP
- CrowdSec
- Docker
- Tor
- Wazuh Agent

---

## Análise

A investigação demonstrou que o ambiente apresenta configuração consistente com uma instalação legítima do Kali Linux voltada para estudos de Cibersegurança.

As verificações realizadas não identificaram evidências de:

- Privilege Escalation;
- Persistência maliciosa;
- Backdoors;
- Reverse Shells;
- Alterações suspeitas em binários críticos.

As técnicas analisadas foram relacionadas às táticas de **Privilege Escalation**, **System Information Discovery**, **Process Discovery** e **Network Service Discovery** da matriz MITRE ATT&CK.

---

## Recomendações

- Manter o sistema operacional atualizado;
- Revisar periodicamente binários SUID e Linux Capabilities;
- Auditar tarefas agendadas e serviços expostos;
- Continuar integrando eventos ao Wazuh e ao Suricata para correlação e monitoramento;
- Repetir esse processo de auditoria após alterações significativas no ambiente.

---

## Conclusão

A investigação foi concluída com sucesso e não identificou indicadores de comprometimento ou mecanismos de escalonamento de privilégios.

Além de validar a segurança do laboratório, este exercício proporcionou experiência prática em auditoria de sistemas Linux, documentação técnica, análise de indicadores e aplicação da metodologia utilizada por equipes de SOC, Blue Team e Incident Response.

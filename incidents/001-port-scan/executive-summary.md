
# Executive Summary - Incident 001

## Visão Geral

Foi identificada uma atividade de reconhecimento de rede direcionada ao servidor Wazuh (`192.168.218.129`) durante uma simulação controlada realizada a partir da máquina Kali Linux (`192.168.218.130`).

A atividade consistiu na execução de diferentes técnicas de varredura utilizando a ferramenta Nmap, com o objetivo de validar a capacidade de detecção do ambiente composto por Suricata IDS e Wazuh SIEM.

---

## Classificação

* Tipo de incidente: Reconhecimento de Rede (Port Scan)
* Severidade: Baixa
* Status: Concluído
* Ambiente: Laboratório controlado

---

## Evidências

Foram identificados alertas como:

* `POSSBL PORT SCAN (NMAP -sS)`
* `POSSBL PORT SCAN (NMAP -sX)`

Os eventos foram registrados pelo Suricata e disponibilizados para correlação através da integração com o Wazuh.

---

## Impacto

Nenhum impacto operacional foi observado, uma vez que toda a atividade ocorreu em ambiente de testes para fins educacionais.

---

## Análise

O comportamento identificado corresponde à fase de Reconnaissance da Cyber Kill Chain e está alinhado à técnica **T1595 – Active Scanning** da matriz MITRE ATT&CK.

A detecção demonstrou que o laboratório possui capacidade para identificar atividades de enumeração de serviços e reconhecimento de rede.

---

## Recomendações

* Manter regras do Suricata atualizadas;
* Monitorar eventos recorrentes de port scan;
* Correlacionar alertas semelhantes para identificar campanhas de reconhecimento;
* Expandir o laboratório para cenários envolvendo exploração e resposta automatizada.

---

## Conclusão

O incidente validou com sucesso a integração entre Suricata e Wazuh e confirmou a capacidade do ambiente em detectar atividades típicas da fase inicial de um ataque cibernético, servindo como base para cenários mais avançados de Threat Hunting e Incident Response.

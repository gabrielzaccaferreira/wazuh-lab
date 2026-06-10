
# IOC Analysis - Incident 001

# Objetivo

Documentar os principais Indicadores de Comprometimento (Indicators of Compromise - IOC) identificados durante a simulação de reconhecimento utilizando Nmap.

---

# IOC 001

## Tipo

Source IP

## Valor

192.168.218.130

## Descrição

Endereço IP responsável pela execução da atividade de reconhecimento contra o servidor monitorado.

---

# IOC 002

## Tipo

Destination IP

## Valor

192.168.218.129

## Descrição

Servidor alvo da atividade de enumeração.

---

# IOC 003

## Tipo

Ferramenta utilizada

## Valor

Nmap

## Descrição

Ferramenta amplamente utilizada para reconhecimento, enumeração de serviços e descoberta de portas.

---

# IOC 004

## Tipo

Técnica observada

## Valor

TCP SYN Scan (-sS)

## Descrição

Tentativa de identificação de portas abertas utilizando varredura SYN.

---

# IOC 005

## Tipo

Técnica observada

## Valor

Service Enumeration (-sV)

## Descrição

Identificação das versões dos serviços disponíveis no host.

---

# IOC 006

## Tipo

Técnica observada

## Valor

OS Detection (-O)

## Descrição

Tentativa de identificação do sistema operacional do alvo.

---

# IOC 007

## Tipo

Alerta IDS

## Valor

POSSBL PORT SCAN (NMAP -sS)

## Descrição

Evento gerado pelo Suricata indicando comportamento compatível com varredura de portas.

---

# IOC 008

## Tipo

Alerta IDS

## Valor

POSSBL PORT SCAN (NMAP -sX)

## Descrição

Evento gerado pelo Suricata indicando tentativa de enumeração utilizando técnica de varredura diferenciada.

---

# IOC 009

## Tipo

Arquivo de evidência

## Valor

/var/log/suricata/fast.log

## Descrição

Arquivo contendo os alertas gerados pelo Suricata.

---

# IOC 010

## Tipo

Arquivo de evidência

## Valor

/var/log/suricata/eve.json

## Descrição

Arquivo JSON utilizado para integração e correlação dos eventos com o Wazuh.

---

# Conclusão

Os indicadores coletados demonstram uma atividade típica da fase de Reconhecimento (Reconnaissance), comum nas etapas iniciais de um ataque cibernético. Embora realizada em ambiente controlado para fins educacionais, a simulação reproduz um comportamento frequentemente observado em ambientes corporativos.

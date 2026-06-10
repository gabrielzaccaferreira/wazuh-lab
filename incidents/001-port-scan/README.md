
# Incident 001 - Port Scan Detection

## Resumo Executivo

Durante uma atividade de simulação ofensiva em ambiente controlado, foi executado um processo de reconhecimento utilizando a ferramenta **Nmap** contra o servidor Wazuh (`192.168.218.129`).

O objetivo foi validar a capacidade do laboratório em detectar técnicas de enumeração e reconhecimento de rede através da integração entre **Suricata IDS** e **Wazuh SIEM**.

O Suricata identificou múltiplas tentativas de varredura de portas e gerou alertas classificados como **Possible Port Scan**, permitindo o envio dos eventos para análise e correlação pelo Wazuh.

---

# Objetivo

Validar a detecção de atividades de reconhecimento de rede utilizando regras do Suricata integradas ao Wazuh.

---

# Ambiente

## Atacante

* Sistema Operacional: Kali Linux
* IP: 192.168.218.130

## Alvo

* Sistema Operacional: Ubuntu Server
* Serviço monitorado pelo Wazuh
* IP: 192.168.218.129

---

# Ferramenta utilizada

* Nmap

Exemplos de comandos executados:

```bash
sudo nmap -sS 192.168.218.129

sudo nmap -A 192.168.218.129

sudo nmap -A -Pn -sS -sV -O 192.168.218.129
```

---

# Resultado esperado

* Geração de eventos no Suricata
* Registro em `fast.log`
* Registro em `eve.json`
* Coleta pelo Wazuh Agent
* Disponibilização para análise e investigação

---

# Status

✅ Simulação realizada com sucesso.

Este incidente faz parte da série de cenários práticos desenvolvidos para o laboratório SOC Home Lab Enterprise.

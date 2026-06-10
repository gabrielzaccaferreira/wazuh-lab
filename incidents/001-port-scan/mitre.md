
# MITRE ATT&CK Mapping - Incident 001

# Objetivo

Relacionar o comportamento observado durante o incidente com a matriz MITRE ATT&CK, identificando a tática e as técnicas utilizadas pelo atacante.

---

# Tática

## Reconnaissance

ID:

```
TA0043
```

### Descrição

A fase de Reconhecimento consiste na coleta de informações sobre o ambiente alvo antes de uma tentativa de comprometimento.

---

# Técnica Principal

## Active Scanning

ID:

```
T1595
```

### Descrição

Consiste na realização de conexões ativas para identificar:

* Hosts ativos
* Serviços disponíveis
* Portas abertas
* Sistemas operacionais
* Tecnologias utilizadas

---

# Evidências observadas

Durante a simulação foram executados comandos como:

```bash
sudo nmap -sS 192.168.218.129

sudo nmap -A 192.168.218.129

sudo nmap -A -Pn -sS -sV -O 192.168.218.129
```

Essas atividades caracterizam uma etapa típica de reconhecimento.

---

# Ferramenta utilizada

* Nmap

---

# Detecção

O Suricata gerou eventos como:

* POSSBL PORT SCAN (NMAP -sS)
* POSSBL PORT SCAN (NMAP -sX)

Os eventos foram posteriormente encaminhados ao ambiente Wazuh para correlação e investigação.

---

# Avaliação do Analista

Não foi identificada exploração ou comprometimento do servidor.

O comportamento observado corresponde à fase inicial de reconhecimento, normalmente utilizada para coletar informações antes de possíveis ataques posteriores.

---

# Conclusão

O incidente foi corretamente classificado como uma atividade de Reconhecimento (Reconnaissance), sendo compatível com a técnica **T1595 – Active Scanning** da matriz MITRE ATT&CK.

A integração entre Suricata e Wazuh permitiu registrar e analisar essa atividade de forma eficiente, validando o funcionamento do laboratório.

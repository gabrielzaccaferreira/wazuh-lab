
# MITRE ATT&CK Mapping - Incident 003

# Objetivo

Relacionar a investigação realizada com a matriz MITRE ATT&CK, identificando as principais táticas e técnicas avaliadas durante a análise de possíveis vetores de Privilege Escalation.

---

# Cenário

Foi realizada uma auditoria de segurança em um sistema Linux com o objetivo de identificar possíveis mecanismos de escalonamento de privilégios, persistência e execução privilegiada.

Nenhuma evidência de exploração foi identificada.

---

# Tática

## Privilege Escalation

ID:

```
TA0004
```

### Descrição

Consiste na obtenção de permissões superiores às inicialmente concedidas ao atacante ou usuário.

---

# Técnica Avaliada

## Abuse Elevation Control Mechanism

ID:

```
T1548
```

### Descrição

A técnica consiste na exploração de mecanismos de elevação de privilégios, como:

- Sudo
- SUID
- SGID
- Capabilities
- Polkit (pkexec)

---

# Técnica Avaliada

## Scheduled Task / Job

ID:

```
T1053
```

### Descrição

Utilização de tarefas agendadas para execução automática de comandos ou mecanismos de persistência.

Durante a investigação foram analisados:

- /etc/crontab
- /etc/cron.d
- /etc/cron.daily
- Crontab do usuário

Nenhuma persistência foi identificada.

---

# Técnica Avaliada

## System Services

ID:

```
T1569
```

### Descrição

Foram analisados os principais serviços em execução, incluindo:

- SSH
- XRDP
- CrowdSec
- Docker
- Tor
- Wazuh Agent

Todos apresentaram comportamento esperado para o ambiente.

---

# Técnica Avaliada

## System Information Discovery

ID:

```
T1082
```

### Descrição

Foram coletadas informações do sistema através de comandos como:

```bash
hostname

uname -a

cat /etc/os-release
```

Objetivo:

- Identificar sistema operacional
- Kernel
- Ambiente analisado

---

# Técnica Avaliada

## Process Discovery

ID:

```
T1057
```

### Descrição

Foi realizada análise dos processos ativos utilizando:

```bash
ps aux

ps -ef
```

Nenhum processo suspeito foi identificado.

---

# Técnica Avaliada

## Network Service Discovery

ID:

```
T1046
```

### Descrição

Foram analisadas portas abertas e conexões utilizando:

```bash
ss -tulpn

lsof -i
```

Não foram identificados serviços ou listeners maliciosos.

---

# Avaliação do Analista

Todas as verificações realizadas apresentaram comportamento compatível com um ambiente Linux corretamente configurado.

Não foram encontradas evidências de:

- Privilege Escalation
- Persistência
- Backdoors
- Reverse Shells
- Serviços maliciosos

---

# Conclusão

A investigação demonstra a aplicação prática da metodologia MITRE ATT&CK para validação de controles de segurança e identificação de possíveis vetores de escalonamento de privilégios.

O ambiente permaneceu íntegro durante toda a análise.

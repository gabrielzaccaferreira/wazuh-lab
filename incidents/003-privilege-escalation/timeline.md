
# Timeline - Incident 003

# Objetivo

Documentar cronologicamente as atividades realizadas durante a investigação de possíveis vetores de Privilege Escalation no ambiente Linux.

---

# T0 - Início da investigação

Foi iniciada uma análise de segurança do sistema com foco na identificação de mecanismos de escalonamento de privilégios e persistência.

---

# T1 - Enumeração do usuário

Foram coletadas informações do usuário atual:

```bash
whoami

id

groups
```

Resultado:

- Usuário: kali
- Grupos compatíveis com o ambiente de laboratório

---

# T2 - Identificação do sistema

Foram coletadas informações do sistema operacional:

```bash
hostname

uname -a

cat /etc/os-release
```

Objetivo:

- Identificar versão do kernel
- Distribuição Linux
- Hostname

---

# T3 - Verificação de privilégios sudo

Foi realizada análise das permissões administrativas:

```bash
sudo -l
```

Resultado:

O usuário possui permissões administrativas conforme esperado para o ambiente de laboratório.

---

# T4 - Enumeração de binários SUID

Foi executado:

```bash
find / -perm -4000 -type f 2>/dev/null
```

Objetivo:

Identificar binários potencialmente exploráveis para Privilege Escalation.

Resultado:

Apenas binários compatíveis com uma instalação padrão do sistema foram encontrados.

---

# T5 - Análise de Linux Capabilities

Foi executado:

```bash
getcap -r / 2>/dev/null
```

Resultado:

Foram identificadas capabilities relacionadas ao funcionamento de ferramentas como Nmap, Dumpcap e Fping, sem evidências de configuração insegura.

---

# T6 - Auditoria de permissões

Foram verificadas permissões World Writable:

```bash
find / -xdev -type d -perm -0002

find / -xdev -type f -perm -0002
```

Resultado:

Apenas diretórios esperados pelo sistema foram encontrados.

Nenhum arquivo inseguro foi identificado.

---

# T7 - Análise de tarefas agendadas

Foram analisados:

- /etc/crontab
- /etc/cron.d
- /etc/cron.daily
- Crontab do usuário

Resultado:

Nenhum mecanismo de persistência foi identificado.

---

# T8 - Análise de processos

Foram analisados os processos ativos do sistema.

Resultado:

Foram encontrados apenas processos compatíveis com o funcionamento normal do laboratório.

---

# T9 - Análise de portas e conexões

Foram executados:

```bash
ss -tulpn

lsof -i
```

Resultado:

Foram identificados apenas serviços legítimos:

- SSH
- XRDP
- CrowdSec
- Docker
- Tor
- Wazuh Agent

---

# T10 - Verificação de GTFOBins

Foram analisados binários frequentemente utilizados em técnicas de Privilege Escalation:

- python3
- bash
- find
- tar
- awk

Resultado:

Nenhum binário apresentou permissões ou configurações inseguras.

---

# Encerramento

A investigação foi concluída sem identificação de indícios de Privilege Escalation ou persistência maliciosa.

O ambiente permaneceu íntegro durante toda a análise.

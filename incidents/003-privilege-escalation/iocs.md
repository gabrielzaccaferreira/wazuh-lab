
# IOC Analysis - Incident 003

# Objetivo

Documentar os principais indicadores observados durante a investigação de possíveis vetores de Privilege Escalation no sistema Linux.

---

# IOC 001

## Tipo

Sistema Operacional

## Valor

Kali GNU/Linux Rolling 2026.2

## Descrição

Sistema operacional analisado durante a investigação.

---

# IOC 002

## Tipo

Hostname

## Valor

kali

## Descrição

Hostname da máquina analisada.

---

# IOC 003

## Tipo

Usuário analisado

## Valor

kali

## Descrição

Usuário atualmente autenticado no sistema.

---

# IOC 004

## Tipo

Permissões administrativas

## Valor

sudo -l

## Descrição

O usuário possui permissões administrativas compatíveis com o ambiente de laboratório.

---

# IOC 005

## Tipo

Binários SUID

## Valor

find / -perm -4000 -type f

## Descrição

Foram identificados apenas binários padrão do sistema, sem evidências de configuração anômala.

---

# IOC 006

## Tipo

Linux Capabilities

## Valor

getcap -r /

## Descrição

Capabilities encontradas apenas em ferramentas esperadas, como:

- nmap
- dumpcap
- fping
- mtr-packet

Nenhuma capability apresentou risco imediato de Privilege Escalation.

---

# IOC 007

## Tipo

World Writable Directories

## Valor

/tmp

/var/tmp

/var/lib/php/sessions

## Descrição

Diretórios compatíveis com o funcionamento normal do sistema.

---

# IOC 008

## Tipo

World Writable Files

## Valor

Nenhum encontrado

## Descrição

Não foram identificados arquivos com permissão global de escrita.

---

# IOC 009

## Tipo

Cron Jobs

## Valor

/etc/crontab

/etc/cron.d

/etc/cron.daily

## Descrição

Nenhuma tarefa suspeita ou mecanismo de persistência foi identificado.

---

# IOC 010

## Tipo

Serviços em execução

## Valor

- SSH
- XRDP
- CrowdSec
- Docker
- Tor
- Wazuh Agent

## Descrição

Todos os serviços encontrados são compatíveis com o ambiente de laboratório.

---

# IOC 011

## Tipo

Conexões de rede

## Valor

Comunicação entre:

192.168.218.130 → 192.168.218.129:1514

## Descrição

Conexão legítima do Wazuh Agent com o Wazuh Manager.

---

# IOC 012

## Tipo

GTFOBins

## Valor

python3

bash

find

tar

awk

## Descrição

Nenhum binário apresentou permissões ou configurações inseguras que permitissem escalonamento de privilégios.

---

# Conclusão

A investigação não identificou indicadores de comprometimento, persistência ou Privilege Escalation. O ambiente apresentou comportamento consistente com uma instalação legítima e adequadamente configurada para fins de laboratório.

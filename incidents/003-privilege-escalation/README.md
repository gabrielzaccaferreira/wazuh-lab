
# Incident 003 - Privilege Escalation Investigation

# Resumo Executivo

Foi realizada uma investigação de possíveis vetores de Privilege Escalation em ambiente Linux utilizando técnicas de enumeração empregadas por analistas de segurança e equipes de Incident Response.

O objetivo foi identificar configurações inseguras, binários privilegiados, capabilities, tarefas agendadas, permissões inadequadas e possíveis mecanismos de persistência.

Durante a análise, não foram encontradas evidências de comprometimento ou escalonamento de privilégios, demonstrando que o ambiente encontra-se adequadamente configurado para fins de laboratório.

---

# Objetivo

Validar a segurança do sistema através da identificação de possíveis vetores de Privilege Escalation.

---

# Ambiente

## Sistema

- Kali Linux Rolling 2026.2

## Hostname

- kali

## Usuário analisado

- kali

---

# Escopo da análise

Foram realizadas as seguintes verificações:

- Identificação do usuário
- Grupos do usuário
- Kernel Linux
- Distribuição instalada
- Permissões sudo
- Binários SUID
- Linux Capabilities
- Diretórios World Writable
- Arquivos World Writable
- Cron Jobs
- Processos ativos
- Portas abertas
- Conexões de rede
- Binários potencialmente exploráveis (GTFOBins)

---

# Resultado

Nenhuma evidência de:

- Privilege Escalation
- Persistência
- Backdoor
- Reverse Shell
- Capabilities inseguras
- Cron Jobs maliciosos
- Arquivos World Writable inseguros

foi identificada durante a investigação.

---

# Status

✅ Investigação concluída com sucesso.

Este incidente faz parte da série de cenários práticos desenvolvidos para o laboratório SOC Home Lab Enterprise.

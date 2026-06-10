
# IOC Analysis - Incident 002

# Objetivo

Documentar os principais Indicadores de Comprometimento (Indicators of Compromise - IOC) identificados durante a simulação de um ataque SSH Brute Force.

---

# IOC 001

## Tipo

Source IP

## Valor

192.168.218.130

## Descrição

Endereço IP responsável pelas tentativas de autenticação contra o servidor monitorado.

---

# IOC 002

## Tipo

Destination IP

## Valor

192.168.218.129

## Descrição

Servidor alvo das tentativas de autenticação SSH.

---

# IOC 003

## Tipo

Serviço

## Valor

SSH (TCP/22)

## Descrição

Serviço alvo utilizado para acesso remoto ao servidor.

---

# IOC 004

## Tipo

Técnica observada

## Valor

SSH Brute Force

## Descrição

Múltiplas tentativas consecutivas de autenticação utilizando credenciais inválidas.

---

# IOC 005

## Tipo

Log observado

## Valor

Failed password

## Descrição

Registro indicando falha de autenticação durante tentativa de login.

---

# IOC 006

## Tipo

Usuário utilizado

## Valor

Usuário inexistente ou inválido

## Descrição

Tentativa de autenticação utilizando credenciais não válidas.

---

# IOC 007

## Tipo

Ferramenta

## Valor

OpenSSH

## Descrição

Serviço responsável pelo processo de autenticação monitorado pelo Wazuh.

---

# IOC 008

## Tipo

Fonte de evidência

## Valor

systemd-journal / auth logs

## Descrição

Logs coletados pelo Wazuh Agent para análise e correlação.

---

# IOC 009

## Tipo

Tecnologia de detecção

## Valor

Wazuh SIEM

## Descrição

Plataforma responsável pela coleta, processamento e correlação dos eventos.

---

# Conclusão

Os indicadores coletados caracterizam uma tentativa típica de obtenção de acesso por força bruta ao serviço SSH, comportamento frequentemente observado nas fases iniciais de ataques contra ambientes Linux.

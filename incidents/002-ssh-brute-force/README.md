
# Incident 002 - SSH Brute Force Detection

## Visão Geral

Este incidente documenta uma simulação de ataque de força bruta contra o serviço SSH em um ambiente controlado de laboratório, utilizando o ecossistema Wazuh SIEM/XDR para detecção, correlação e investigação dos eventos.

O objetivo foi validar a capacidade do laboratório em identificar tentativas de autenticação não autorizadas e demonstrar o fluxo completo de um processo de Incident Response.

---

# Objetivos

- Simular uma tentativa de SSH Brute Force;
- Validar a geração de logs no sistema operacional;
- Verificar a coleta dos eventos pelo Wazuh Agent;
- Confirmar a correlação dos eventos pelo Wazuh Manager;
- Identificar os alertas no Wazuh Dashboard;
- Documentar o incidente seguindo boas práticas de SOC.

---

# Ambiente

## Atacante

| Item | Valor |
|-------|---------|
| Sistema Operacional | Kali Linux |
| IP | 192.168.218.130 |

---

## Alvo

| Item | Valor |
|-------|---------|
| Sistema Operacional | Ubuntu Server |
| Serviço | OpenSSH |
| Wazuh Manager | Ativo |
| IP | 192.168.218.129 |

---

# Cenário

Foi realizada uma sequência de tentativas de autenticação utilizando um usuário inexistente no serviço SSH do servidor monitorado.

As tentativas produziram eventos registrados pelo sistema operacional e posteriormente coletados pelo Wazuh Agent.

O mecanismo de correlação do Wazuh identificou múltiplas falhas de autenticação e classificou o comportamento como uma tentativa de **SSH Brute Force**.

---

# Fluxo de Detecção

```
Atacante
        │
        ▼
Tentativas SSH
        │
        ▼
Ubuntu Server
(auth logs)
        │
        ▼
Wazuh Agent
        │
        ▼
Wazuh Manager
        │
        ▼
Indexer
        │
        ▼
Dashboard
        │
        ▼
Análise do Incidente
```

---

# Documentação deste Incidente

Este incidente é composto pelos seguintes documentos:

- executive-summary.md
- timeline.md
- iocs.md
- mitre.md
- lessons-learned.md
- evidencias/

---

# Tecnologias Utilizadas

- Wazuh SIEM
- Wazuh Agent
- Ubuntu Server
- Kali Linux
- OpenSSH
- Linux Journal
- MITRE ATT&CK

---

# Resultado

A simulação confirmou a capacidade do laboratório em detectar atividades de força bruta contra o serviço SSH, permitindo a identificação, correlação e investigação dos eventos em um fluxo semelhante ao encontrado em ambientes corporativos.

---

# Status

✅ Concluído

**Categoria:** Incident Response  
**Tipo:** SSH Brute Force Detection  
**Severidade:** Média  
**Ambiente:** Laboratório Controlado

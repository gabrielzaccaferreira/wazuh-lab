
# Validações do Ambiente Wazuh

## Objetivo

Validar se os serviços do Wazuh Server e do Wazuh Agent estão funcionando corretamente.

---

## Serviços no Ubuntu Server

No servidor Wazuh, foram verificados os seguintes serviços:

```bash
sudo systemctl status wazuh-manager --no-pager
sudo systemctl status wazuh-indexer --no-pager
sudo systemctl status wazuh-dashboard --no-pager
sudo systemctl status filebeat --no-pager
```

Resultado esperado:

```text
active (running)
```

---

## Acesso ao Dashboard

O Dashboard foi acessado pelo navegador através do endereço:

```text
https://192.168.0.120
```

Usuário:

```text
admin
```

A senha foi gerada automaticamente durante a instalação.

---

## Agente Kali Linux

No Kali Linux, foi validado o status do agente:

```bash
sudo systemctl status wazuh-agent --no-pager
```

Resultado:

```text
Active: active (running)
```

---

## Processos do Agente

Durante a validação, os seguintes processos foram observados:

```text
wazuh-execd
wazuh-agentd
wazuh-syscheckd
wazuh-logcollector
wazuh-modulesd
```

---

## Logs Observados

```bash
sudo tail -f /var/ossec/logs/ossec.log
```

Eventos identificados:

```text
SCA scan started
SCA scan finished
Syscollector evaluation finished
File integrity monitoring scan ended
FIM sync module started
Rootcheck scan finished
```

---

## Status no Dashboard

No Dashboard do Wazuh, o agente Kali Linux deve aparecer em:

```text
Wazuh > Agents
```

Com o status:

```text
Active
```
---

## Recursos do Sistema

Durante a validação do laboratório foram observados os seguintes recursos no servidor Ubuntu:

```bash
free -h
```

Resultado observado:

```text
Memória utilizada: aproximadamente 2.7 GB
Memória disponível: aproximadamente 4.5 GB
```

---

## Problema Identificado

Durante a operação do laboratório foram observadas mensagens do kernel relacionadas ao RCU:

```text
rcu_preempt detected stalls
rcu_preempt kthread starved
```

### Diagnóstico

O ambiente estava utilizando simultaneamente:

- Ubuntu Server
- Wazuh Manager
- Wazuh Dashboard
- Wazuh Indexer
- Kali Linux

O consumo excessivo de recursos provocou lentidão temporária.

### Solução

Ajuste dos recursos das máquinas virtuais:

Ubuntu Server:

```text
4 vCPU
8 GB RAM
```

Kali Linux:

```text
2 vCPU
4 GB RAM
```

Após o ajuste o ambiente voltou a operar normalmente.

---

## Resultado Final do Laboratório

Validações concluídas com sucesso:

- Wazuh Manager operacional
- Wazuh Indexer operacional
- Wazuh Dashboard operacional
- Filebeat operacional
- Agente Kali Linux conectado
- Comunicação entre agente e servidor validada
- Dashboard acessível
- Logs coletados com sucesso

Status Final:

```text
LABORATÓRIO OPERACIONAL
```

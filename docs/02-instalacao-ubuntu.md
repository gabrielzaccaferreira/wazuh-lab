
# Instalação do Ubuntu Server

## Download

Site Oficial:

https://ubuntu.com/download/server

Versão utilizada:

Ubuntu Server 24.04 LTS

## Objetivo da Instalação

Preparar um servidor Linux para hospedar os componentes do Wazuh SIEM/XDR, incluindo:

- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard
- Filebeat

O servidor será utilizado como plataforma de monitoramento e análise de eventos de segurança.

SSH:

Habilitado

### Justificativa

O OpenSSH foi habilitado para permitir administração remota do servidor e simular ambientes corporativos de infraestrutura e segurança.

---

## Configuração da Máquina Virtual

CPU:

```text
4 vCPU
```

RAM:

```text
8 GB
```

Disco:

```text
70 GB
```

Rede:

```text
NAT
```

---

## Configurações da Instalação

Hostname:

```text
wazuh-server
```

Usuário:

```text
gabriel
```

SSH:

```text
Habilitado
```

Ubuntu Pro:

```text
Ignorado
```

Featured Server Snaps:

```text
Nenhum selecionado
```

---

## Verificações

Hostname:

```bash
hostname
```

Resultado:

```text
wazuh-server
```

IP:

```bash
hostname -I
```

Resultado:

```text
192.168.0.120
```

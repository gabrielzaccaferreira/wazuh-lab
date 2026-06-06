
# 08 - Integração do Suricata com o Wazuh

# Objetivo

O objetivo desta etapa foi integrar o Suricata IDS ao Wazuh SIEM, permitindo que os eventos de rede gerados pelo mecanismo de detecção fossem coletados, processados e visualizados através do Dashboard e do módulo Threat Hunting.

Essa integração possibilita a centralização de eventos de segurança em uma única plataforma, simulando uma arquitetura utilizada em ambientes SOC (Security Operations Center).

---

# Arquitetura do Laboratório

```
Internet
        │
        ▼
Suricata IDS
        │
        ▼
eve.json
        │
        ▼
Wazuh Agent
        │
        ▼
Wazuh Manager
        │
        ▼
Wazuh Indexer
        │
        ▼
Wazuh Dashboard
        │
        ▼
Threat Hunting
```

---

# Ambiente Utilizado

## Host

* Windows 11
* VMware Workstation

## Máquina Virtual

### Kali Linux

Funções:

* Suricata IDS
* Wazuh Agent

### Ubuntu Server

Funções:

* Wazuh Manager
* Wazuh Indexer
* Wazuh Dashboard

---

# Objetivo da Integração

Antes da integração, o Suricata armazenava seus eventos apenas no arquivo:

```
/var/log/suricata/eve.json
```

Após a integração, esses eventos passaram a ser encaminhados ao Wazuh para indexação e visualização através do Dashboard.

---

# Verificação do Suricata

Foi realizada a validação da instalação utilizando:

```bash
sudo systemctl status suricata
```

Também foram verificadas informações da compilação:

```bash
suricata --build-info
```

---

# Validação do arquivo eve.json

Foi confirmada a existência do arquivo:

```
/var/log/suricata/eve.json
```

e realizada sua inspeção utilizando:

```bash
tail -5 /var/log/suricata/eve.json
```

Os eventos continham registros de:

* DNS
* DHCP
* FLOW
* TLS
* QUIC
* Estatísticas do mecanismo IDS

---

# Testes de geração de eventos

Para gerar tráfego monitorado pelo Suricata foram executados testes como:

```bash
ping google.com
```

e consultas DNS através do sistema.

Essas atividades produziram novos eventos registrados no arquivo eve.json.

---

# Integração com o Wazuh

O Wazuh foi configurado para consumir os eventos produzidos pelo Suricata através do arquivo eve.json, permitindo sua indexação e análise no Dashboard.

Após a configuração, os serviços foram reiniciados e validados.

---

# Validação da Integração

No Dashboard do Wazuh foi possível observar:

* Eventos do Suricata
* Grupo de regras "suricata"
* Grupo de regras "ids"
* Eventos correlacionados com o agente Kali Linux

Essas evidências confirmaram o funcionamento da integração entre IDS e SIEM.

---

# Resultado

Ao final desta etapa, o laboratório passou a possuir uma arquitetura integrada capaz de:

* Detectar eventos de rede
* Registrar eventos em formato JSON
* Encaminhar eventos ao Wazuh
* Indexar informações
* Disponibilizar os dados para Threat Hunting

Esta integração representa um ambiente prático de monitoramento de segurança inspirado em operações reais de SOC.

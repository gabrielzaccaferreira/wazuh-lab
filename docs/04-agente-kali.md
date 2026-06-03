
# Configuração do Agente Wazuh no Kali Linux

## Objetivo

Instalar e configurar o Wazuh Agent no Kali Linux para que ele envie eventos de segurança para o Wazuh Server.

---

## Informações do Ambiente

Wazuh Server:

```text
192.168.0.120
```

Agente:

```text
kali-linux
```

Grupo:

```text
default
```

Tipo de pacote:

```text
DEB amd64
```

---

## Teste de Conectividade

Antes da instalação, foi testada a comunicação entre o Kali Linux e o Wazuh Server.

```bash
nc -zv 192.168.0.120 1514
nc -zv 192.168.0.120 1515
```

Resultado:

```text
1514 open
1515 open
```

---

## Instalação do Agente

```bash
wget https://packages.wazuh.com/4.x/apt/pool/main/w/wazuh-agent/wazuh-agent_4.14.5-1_amd64.deb
```

```bash
sudo WAZUH_MANAGER='192.168.0.120' \
WAZUH_AGENT_GROUP='default' \
WAZUH_AGENT_NAME='kali-linux' \
dpkg -i ./wazuh-agent_4.14.5-1_amd64.deb
```

---

## Inicialização do Serviço

```bash
sudo systemctl daemon-reload
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent
```

---

## Validação

```bash
sudo systemctl status wazuh-agent --no-pager
```

Resultado esperado:

```text
Active: active (running)
```

---

### Validação no Dashboard

Após a inicialização do agente, foi realizada a validação no Dashboard do Wazuh.

Menu:

```text
Wazuh → Agents
```

Resultado esperado:

```text
Agent Name: kali-linux
Status: Active
```

## Logs do Agente

```bash
sudo tail -f /var/ossec/logs/ossec.log
```

Eventos observados:

```text
Security Configuration Assessment scan finished
File integrity monitoring scan ended
FIM sync module started
rootcheck scan finished
```
## Problema Encontrado

Após reinicializações das máquinas virtuais, o agente apresentou status:

```text
Disconnected
```

Diagnóstico realizado:

```bash
sudo systemctl status wazuh-agent
```

Validação da conectividade:

```bash
nc -zv 192.168.0.120 1514
nc -zv 192.168.0.120 1515
```

Resultado:

```text
1514 open
1515 open
```

Solução:

```bash
sudo systemctl restart wazuh-agent
```

Resultado:

```text
Status: Active
```

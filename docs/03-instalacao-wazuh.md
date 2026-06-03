
# Instalação do Wazuh

## Objetivo

Implementar uma plataforma SIEM/XDR utilizando o Wazuh para monitoramento de eventos de segurança, análise de logs e gerenciamento centralizado de agentes.

## Atualização do Sistema

```bash
sudo apt update
sudo apt upgrade -y
sudo apt autoremove -y
```

---

## Download do Instalador

```bash
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh
```

Verificação:

```bash
ls -lh
```

---

## Permissão de Execução

```bash
chmod +x wazuh-install.sh
```

Verificação:

```bash
ls -l wazuh-install.sh
```

---

## Instalação

```bash
sudo ./wazuh-install.sh -a
```

---

## Componentes Instalados

- Wazuh Manager
- Wazuh Dashboard
- Wazuh Indexer
- Filebeat

---

## Resultado da Instalação

Após a execução do instalador, os seguintes serviços ficaram disponíveis:

- Wazuh Manager
- Wazuh Dashboard
- Wazuh Indexer
- Filebeat

Validação:

```bash
sudo systemctl is-active wazuh-manager
sudo systemctl is-active wazuh-indexer
sudo systemctl is-active wazuh-dashboard
```

Resultado esperado:

```text
active
active
active
```

## Acesso ao Dashboard

```text
https://192.168.0.120
```

Usuário:

```text
admin
```

Senha:

```text
Gerada automaticamente durante a instalação
```
## Observações

Durante a instalação ocorreu um erro inicial relacionado ao download do instalador.

Erro:

```text
No such file or directory
```

Causa:

O script wazuh-install.sh ainda não havia sido baixado.

Solução:

```bash
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh
```

Após o download correto, a instalação foi concluída com sucesso.

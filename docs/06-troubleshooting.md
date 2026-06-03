
# Troubleshooting

## Problema 1 - Arquivo wazuh-install.sh não encontrado

### Erro

```bash
No such file or directory
```

### Causa

O arquivo de instalação do Wazuh ainda não havia sido baixado corretamente.

### Solução

Executar o comando correto:

```bash
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh
```

Depois verificar:

```bash
ls -lh
```

---

## Problema 2 - Comando curl digitado incorretamente

### Situação

Foi digitado um comando incompleto ou incorreto, como:

```bash
curl -lh wazuh-install.sh
```

### Solução

Utilizar o comando correto com a URL oficial:

```bash
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh
```

---

## Problema 3 - Saída presa em lines 1-21/21 END

### Situação

Ao executar comandos como:

```bash
systemctl status wazuh-manager
```

o terminal abriu o visualizador less.

### Solução

Pressionar:

```text
q
```

Para evitar isso, usar:

```bash
systemctl status wazuh-manager --no-pager
```

---

## Problema 4 - inverse host lookup failed

### Erro

```text
inverse host lookup failed: Unknown host
```

### Causa

O Kali Linux conseguiu acessar o IP do Wazuh Server, mas não encontrou DNS reverso para esse endereço.

### Solução

Não é um erro crítico.

O importante foi a resposta:

```text
1514 open
1515 open
```

Isso confirmou que as portas do Wazuh estavam acessíveis.

---

## Problema 5 - Certificado do navegador

### Situação

Ao acessar:

```text
https://192.168.0.120
```

o navegador exibiu aviso de conexão não privada.

### Causa

O Wazuh utiliza certificado SSL autoassinado no laboratório.

### Solução

Clicar em:

```text
Avançado
Continuar mesmo assim
```
## Problema 6 - RCU Stalls no Ubuntu Server

### Erro

Durante a operação do Wazuh foram observadas mensagens semelhantes a:

```text
rcu_preempt detected stalls on CPUs/tasks
rcu_preempt kthread starved
```

### Sintomas

* Lentidão no Ubuntu Server
* Comandos `systemctl` demorando para responder
* Terminal temporariamente sem resposta
* Dashboard apresentando lentidão

### Diagnóstico

O ambiente estava executando simultaneamente:

* Ubuntu Server
* Wazuh Manager
* Wazuh Dashboard
* Wazuh Indexer
* Kali Linux

O consumo de recursos das máquinas virtuais estava próximo do limite disponível no host.

### Solução

Redistribuição dos recursos das máquinas virtuais.

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

## Problema 7 - Agente Wazuh Desconectado

### Situação

Após reinicializações das máquinas virtuais o agente apareceu no Dashboard com status:

```text
Disconnected
```

### Diagnóstico

Verificação do serviço:

```bash
sudo systemctl status wazuh-agent
```

Teste de conectividade:

```bash
nc -zv 192.168.0.120 1514
nc -zv 192.168.0.120 1515
```

Resultado:

```text
1514 open
1515 open
```

### Solução

Reiniciar o agente:

```bash
sudo systemctl restart wazuh-agent
```

### Resultado

O agente voltou a aparecer no Dashboard com status:

```text
Active
```

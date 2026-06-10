
# Timeline do Incidente 001

## Objetivo

Documentar cronologicamente as ações realizadas durante a simulação de um ataque de reconhecimento utilizando Nmap e sua detecção pelo ambiente Suricata + Wazuh.

---

## Linha do Tempo

### T0 - Ambiente operacional

* Servidor Wazuh ativo
* Agente Wazuh conectado
* Suricata em execução
* Comunicação entre as máquinas validada

---

### T1 - Início da atividade

Foi iniciado um processo de reconhecimento contra o servidor:

```bash
sudo nmap -sS 192.168.218.129
```

Objetivo:

* Descobrir portas abertas
* Validar detecção pelo IDS

---

### T2 - Enumeração avançada

Foi realizada uma varredura mais completa:

```bash
sudo nmap -A 192.168.218.129
```

Incluindo:

* Detecção de serviços
* Detecção de versão
* Identificação do sistema operacional

---

### T3 - Enumeração detalhada

Foi executado:

```bash
sudo nmap -A -Pn -sS -sV -O 192.168.218.129
```

Essa etapa simulou um atacante realizando reconhecimento aprofundado do alvo.

---

### T4 - Detecção pelo Suricata

O Suricata registrou eventos como:

```
POSSBL PORT SCAN (NMAP -sS)
```

e

```
POSSBL PORT SCAN (NMAP -sX)
```

Os eventos foram registrados no arquivo `fast.log`.

---

### T5 - Coleta pelo Wazuh

O Wazuh Agent monitorou o arquivo:

```
/var/log/suricata/eve.json
```

encaminhando os eventos para o Wazuh Manager.

---

### T6 - Investigação

Foi realizada análise dos logs e validação da integração entre:

* Suricata IDS
* Wazuh Agent
* Wazuh Manager
* Wazuh Dashboard

---

### T7 - Encerramento

A simulação foi concluída sem impacto ao ambiente, validando o funcionamento do pipeline de detecção e investigação.

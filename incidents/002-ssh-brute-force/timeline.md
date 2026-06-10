
# Timeline - Incident 002

## Objetivo

Documentar cronologicamente os eventos observados durante a simulação de um ataque SSH Brute Force e sua detecção pelo Wazuh.

---

## T0 - Ambiente operacional

- Wazuh Manager ativo;
- Wazuh Indexer ativo;
- Wazuh Dashboard ativo;
- Wazuh Agent ativo;
- Comunicação entre Kali e Ubuntu validada.

---

## T1 - Início da simulação

Foi iniciada uma sequência de tentativas de autenticação SSH contra o servidor monitorado utilizando credenciais inválidas.

Objetivo:

- Validar a geração de logs;
- Validar a detecção pelo Wazuh.

---

## T2 - Geração dos eventos

O serviço OpenSSH registrou múltiplas falhas de autenticação.

Esses eventos foram gravados nos logs do sistema operacional.

---

## T3 - Coleta pelo Wazuh Agent

O Wazuh Agent monitorou os logs do sistema e coletou os eventos relacionados às tentativas de login.

---

## T4 - Envio ao Wazuh Manager

Os eventos foram encaminhados ao Wazuh Manager para processamento e correlação.

---

## T5 - Correlação

As regras do Wazuh correlacionaram as múltiplas falhas de autenticação, classificando o comportamento como uma tentativa de SSH Brute Force.

---

## T6 - Investigação

Foi realizada a análise dos eventos gerados, identificando:

- IP de origem;
- Serviço atacado;
- Tipo de autenticação;
- Sequência temporal dos eventos.

---

## T7 - Encerramento

A simulação foi concluída sem impacto operacional, validando o funcionamento do pipeline de detecção e investigação do laboratório.

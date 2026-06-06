
# 09 - Validação da Integração Suricata + Wazuh

# Objetivo

O objetivo desta etapa foi validar que os eventos gerados pelo Suricata IDS estavam sendo corretamente coletados, processados e apresentados pelo Wazuh Dashboard através do módulo Threat Hunting.

---

# Validação do Serviço Suricata

Foi realizada a verificação do estado do serviço utilizando:

```bash
sudo systemctl status suricata
```

Resultado esperado:

* Serviço ativo
* Processo em execução
* Inicialização sem erros

---

# Validação do arquivo eve.json

Foi confirmada a existência do arquivo:

```text
/var/log/suricata/eve.json
```

Verificação realizada com:

```bash
ls -lh /var/log/suricata/

tail -5 /var/log/suricata/eve.json
```

Resultado:

* Arquivo existente
* Eventos sendo gravados continuamente
* Formato JSON válido

---

# Geração de Tráfego para Testes

Para produzir eventos monitorados pelo IDS foram executados testes simples de conectividade:

```bash
ping google.com -c 5
```

Também foram realizadas consultas DNS e acesso a serviços externos, permitindo a geração de novos registros no eve.json.

---

# Validação do Wazuh Agent

Foi confirmado que o agente do Kali Linux permanecia conectado ao Manager.

Verificação:

```bash
sudo systemctl status wazuh-agent
```

Resultado esperado:

```text
Active (running)
```

---

# Validação no Dashboard

No módulo Threat Hunting foram observados eventos provenientes do agente Kali Linux.

Os grupos de regras identificados incluíram:

* ids
* suricata
* ossec
* rootcheck
* syslog
* pam
* sudo

Esses grupos demonstram que o Wazuh está correlacionando diferentes fontes de eventos em uma única plataforma.

---

# Evidências Coletadas

Foram obtidas evidências através de screenshots contendo:

* Dashboard principal
* Threat Hunting
* Top Alerts
* Top Rule Groups
* Eventos do agente Kali Linux
* Alertas relacionados ao Suricata

Essas imagens foram armazenadas no diretório:

```text
evidencias/
```

---

# Resultado Final

A integração foi considerada bem-sucedida, permitindo que o ambiente realizasse:

* Detecção de eventos de rede
* Coleta de logs do Suricata
* Centralização no Wazuh
* Correlação de eventos
* Visualização através do Dashboard
* Apoio às atividades de Threat Hunting

O laboratório passou a simular uma arquitetura simplificada de SOC (Security Operations Center), integrando uma solução IDS com uma plataforma SIEM para monitoramento e análise de segurança.

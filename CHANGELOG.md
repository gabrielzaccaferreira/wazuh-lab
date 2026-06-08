
# Changelog

Todas as mudanças importantes deste projeto serão documentadas neste arquivo.

O formato segue uma estrutura simples baseada em versões, com foco na evolução técnica do laboratório.

---

## [1.0.0] - Laboratório Base

### Adicionado

- Planejamento inicial do laboratório Wazuh SIEM/XDR.
- Instalação do Ubuntu Server.
- Instalação do Wazuh Manager.
- Instalação do Wazuh Indexer.
- Instalação do Wazuh Dashboard.
- Configuração do Filebeat.
- Configuração do agente Wazuh no Kali Linux.
- Validação inicial do Dashboard.
- Validação dos serviços principais do Wazuh.
- Criação da estrutura inicial do repositório.

---

## [1.1.0] - Integração com Kali Linux

### Adicionado

- Integração do Kali Linux como agente Wazuh.
- Validação do agente `kali-linux`.
- Documentação de instalação e registro do agente.
- Evidência do agente ativo no Dashboard.

### Corrigido

- Ajustes de conectividade entre Kali e Wazuh Manager.
- Correção de endereço IP do Manager no arquivo `ossec.conf`.

---

## [1.2.0] - Integração com Suricata IDS

### Adicionado

- Instalação e validação do Suricata IDS no Kali Linux.
- Monitoramento do arquivo `/var/log/suricata/eve.json`.
- Configuração do Wazuh Agent para leitura de logs JSON.
- Validação de eventos Suricata no Wazuh Dashboard.
- Documentação da integração Suricata + Wazuh.

### Validado

- Serviço Suricata ativo.
- Arquivo `eve.json` sendo gerado.
- Alertas do Suricata aparecendo no Wazuh.
- Agente `kali-linux` ativo no Manager.

---

## [1.3.0] - Integração com pfSense

### Adicionado

- Integração do pfSense Firewall com Wazuh.
- Envio de logs via Syslog.
- Criação de documentação específica para pfSense.
- Validação de eventos de firewall.
- Validação de eventos DHCP.
- Testes com `nmap` e `netcat`.

### Corrigido

- Ajustes de rede entre pfSense, Kali e Wazuh Server.
- Correção de fluxo de logs para `/var/log/pfsense.log`.

---

## [1.4.0] - Documentação Avançada

### Adicionado

- Documento de topologia do laboratório.
- Documento de fluxo dos eventos.
- Documento de geração e validação de alertas.
- Documento de Threat Hunting.
- Diagramas em Mermaid:
  - Topologia do laboratório.
  - Fluxo dos eventos.
  - Arquitetura Wazuh.
  - Pipeline de alertas.

### Alterado

- README principal reestruturado.
- Organização da documentação técnica.
- Inclusão de links para diagramas.

---

## [1.5.0] - Refinamento Profissional

### Planejado

- Criação do Roadmap.
- Padronização dos documentos.
- Organização das evidências.
- Criação de assets visuais.
- Adição de casos de uso MITRE ATT&CK.
- Criação de scripts auxiliares.
- Revisão final do repositório.

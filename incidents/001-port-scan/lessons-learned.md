
# Lessons Learned - Incident 001

# Objetivo

Registrar os principais aprendizados obtidos durante a simulação de um ataque de reconhecimento utilizando Nmap em ambiente controlado.

---

# O que aconteceu

Foi executada uma atividade de reconhecimento contra o servidor Wazuh utilizando diferentes técnicas de varredura do Nmap.

O objetivo foi validar a capacidade do ambiente em detectar esse comportamento através da integração entre Suricata e Wazuh.

---

# O que funcionou corretamente

* Comunicação entre as máquinas validada;
* Suricata em execução;
* Regras de detecção carregadas com sucesso;
* Geração de alertas para varreduras Nmap;
* Registro dos eventos em `fast.log`;
* Registro dos eventos em `eve.json`;
* Integração do Wazuh Agent com o Wazuh Manager funcionando corretamente.

---

# Dificuldades encontradas

Durante a implementação foram necessários ajustes na configuração do laboratório, incluindo:

* Correção do endereço IP do Wazuh Manager;
* Configuração adequada da interface monitorada pelo Suricata;
* Validação da leitura do arquivo `eve.json` pelo Wazuh Agent;
* Testes sucessivos para confirmar a geração dos alertas.

---

# Impacto

Nenhum impacto operacional foi identificado, pois todas as atividades ocorreram em ambiente de laboratório controlado.

---

# Recomendações

Para ambientes corporativos, recomenda-se:

* Monitorar continuamente atividades de reconhecimento;
* Correlacionar múltiplos eventos de port scan;
* Criar regras de resposta automática quando apropriado;
* Integrar eventos com inteligência de ameaças;
* Manter regras do Suricata constantemente atualizadas.

---

# Conhecimentos adquiridos

Este incidente permitiu praticar:

* Network Reconnaissance;
* Threat Hunting;
* Análise de IOC;
* Correlação de eventos;
* MITRE ATT&CK Mapping;
* Documentação técnica;
* Operação de SIEM.

---

# Conclusão

A simulação confirmou que o laboratório é capaz de detectar atividades típicas de reconhecimento de rede, fornecendo uma base sólida para cenários mais avançados de análise e resposta a incidentes.


# Lessons Learned - Incident 002

# Objetivo

Registrar os principais aprendizados obtidos durante a simulação de um ataque SSH Brute Force em ambiente controlado.

---

# O que aconteceu

Foi realizada uma simulação de múltiplas tentativas de autenticação contra o serviço SSH do servidor monitorado.

O objetivo foi validar a capacidade do ambiente Wazuh em coletar, correlacionar e disponibilizar eventos relacionados a tentativas de acesso não autorizado.

---

# O que funcionou corretamente

- Comunicação entre Kali Linux e Ubuntu Server validada;
- Serviço SSH operacional;
- Wazuh Agent funcionando corretamente;
- Wazuh Manager ativo e processando eventos;
- Wazuh Indexer e Dashboard operacionais;
- Coleta e processamento dos logs de autenticação com sucesso.

---

# Dificuldades encontradas

Durante a implementação foram necessários alguns ajustes no laboratório, incluindo:

- Validação dos serviços do Wazuh;
- Conferência da comunicação entre agente e manager;
- Verificação da geração dos logs de autenticação;
- Testes sucessivos para confirmar a detecção dos eventos.

---

# Impacto

Nenhum impacto operacional foi identificado, pois todas as atividades ocorreram em ambiente de laboratório controlado.

---

# Recomendações

Para ambientes corporativos recomenda-se:

- Implementar autenticação por chave pública para SSH;
- Desabilitar login de usuários desnecessários;
- Aplicar políticas de bloqueio após múltiplas falhas de autenticação;
- Monitorar continuamente eventos de login;
- Correlacionar tentativas repetidas provenientes do mesmo endereço IP;
- Integrar alertas com mecanismos automáticos de resposta.

---

# Conhecimentos adquiridos

Este incidente permitiu praticar:

- Incident Response;
- Log Analysis;
- Credential Access Detection;
- IOC Analysis;
- MITRE ATT&CK Mapping;
- Threat Hunting;
- Documentação técnica de incidentes;
- Operação de SIEM.

---

# Conclusão

A simulação confirmou que o laboratório possui capacidade para detectar tentativas de força bruta contra o serviço SSH, permitindo sua análise, documentação e investigação de maneira estruturada e alinhada às boas práticas de um SOC.

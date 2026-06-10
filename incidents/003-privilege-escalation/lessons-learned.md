
# Lessons Learned - Incident 003

# Objetivo

Registrar os principais aprendizados obtidos durante a investigação de possíveis vetores de Privilege Escalation em ambiente Linux.

---

# O que aconteceu

Foi realizada uma auditoria completa do sistema com foco na identificação de mecanismos de escalonamento de privilégios, persistência e configurações inseguras.

Foram analisados usuários, grupos, permissões administrativas, binários SUID, Linux Capabilities, tarefas agendadas, processos, serviços de rede e binários potencialmente exploráveis.

---

# O que funcionou corretamente

- Identificação correta do usuário e grupos;
- Verificação das permissões administrativas com `sudo -l`;
- Enumeração dos binários SUID;
- Análise das Linux Capabilities;
- Auditoria de diretórios e arquivos World Writable;
- Verificação das tarefas agendadas (Cron);
- Análise dos processos ativos;
- Verificação das portas abertas e conexões de rede;
- Inspeção de binários frequentemente utilizados em técnicas de Privilege Escalation.

---

# Dificuldades encontradas

Durante a investigação foi necessário:

- Corrigir comandos digitados incorretamente;
- Interpretar corretamente permissões e capabilities do sistema;
- Diferenciar serviços legítimos de possíveis indicadores de comprometimento;
- Validar se determinados binários representavam risco real ou comportamento esperado.

---

# Impacto

Nenhum impacto operacional foi identificado.

Toda a atividade foi realizada em ambiente de laboratório controlado para fins educacionais.

---

# Recomendações

Para ambientes corporativos recomenda-se:

- Realizar auditorias periódicas de binários SUID;
- Monitorar Linux Capabilities configuradas no sistema;
- Revisar permissões World Writable regularmente;
- Auditar tarefas agendadas e mecanismos de persistência;
- Monitorar serviços expostos à rede;
- Correlacionar eventos utilizando SIEM e IDS;
- Manter sistemas e pacotes sempre atualizados.

---

# Conhecimentos adquiridos

Este laboratório permitiu praticar:

- Linux Enumeration;
- Privilege Escalation Assessment;
- System Hardening;
- Process Analysis;
- Network Service Analysis;
- Linux Capabilities;
- SUID Analysis;
- IOC Documentation;
- MITRE ATT&CK Mapping;
- Incident Documentation.

---

# Conclusão

A investigação demonstrou que o ambiente está adequadamente configurado e não apresentou evidências de escalonamento de privilégios ou mecanismos de persistência maliciosos.

Além de validar a segurança do laboratório, o exercício fortaleceu conhecimentos práticos em auditoria de sistemas Linux, Incident Response e Blue Team.

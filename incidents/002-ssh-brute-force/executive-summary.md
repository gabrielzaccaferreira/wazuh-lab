
# Executive Summary - Incident 002

## Visão Geral

Foi identificada uma atividade de tentativa de autenticação não autorizada contra o serviço SSH do servidor monitorado (`192.168.218.129`) durante uma simulação controlada realizada a partir da máquina Kali Linux (`192.168.218.130`).

A atividade consistiu em múltiplas tentativas de acesso utilizando um usuário inexistente, com o objetivo de validar a capacidade de detecção e correlação do ambiente Wazuh SIEM.

---

## Classificação

- **Tipo de incidente:** SSH Brute Force Attempt
- **Categoria:** Credential Access
- **Severidade:** Média
- **Status:** Concluído
- **Ambiente:** Laboratório controlado

---

## Evidências

Durante a simulação, o Wazuh identificou eventos relacionados a:

- Tentativa de login com usuário inexistente;
- Múltiplas falhas de autenticação;
- Correlação automática dos eventos;
- Geração de alerta de tentativa de força bruta contra o serviço SSH.

---

## Impacto

Nenhum impacto operacional foi observado, pois todas as atividades ocorreram em ambiente de laboratório para fins educacionais e validação técnica.

---

## Análise

O comportamento identificado é compatível com uma tentativa de obtenção de acesso por meio de força bruta contra credenciais de autenticação, sendo uma técnica frequentemente utilizada nas fases iniciais de comprometimento de ambientes Linux.

A correlação realizada pelo Wazuh demonstrou que o laboratório possui capacidade para detectar e investigar esse tipo de atividade.

---

## Recomendações

- Monitorar continuamente eventos de autenticação SSH;
- Implementar mecanismos de bloqueio após múltiplas tentativas;
- Utilizar autenticação por chave pública quando possível;
- Desabilitar login de usuários desnecessários;
- Correlacionar eventos recorrentes para identificação de campanhas de ataque.

---

## Conclusão

A simulação validou com sucesso a capacidade do ambiente em detectar tentativas de força bruta contra o serviço SSH, demonstrando o correto funcionamento do pipeline de monitoramento, correlação e investigação do laboratório SOC Home Lab.

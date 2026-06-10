
# MITRE ATT&CK Mapping - Incident 002

# Objetivo

Relacionar o comportamento observado durante o incidente com a matriz MITRE ATT&CK, identificando as táticas e técnicas utilizadas durante a simulação.

---

# Tática Principal

## Credential Access

ID:

```
TA0006
```

### Descrição

A tática Credential Access envolve técnicas utilizadas para obtenção ou validação de credenciais de autenticação com o objetivo de acessar sistemas ou serviços.

---

# Técnica Principal

## Brute Force

ID:

```
T1110
```

### Descrição

Consiste na tentativa repetitiva de autenticação utilizando diferentes credenciais ou múltiplas tentativas contra um mesmo usuário até obter acesso.

---

# Subtécnica

## Password Guessing

ID:

```
T1110.001
```

### Descrição

Tentativa de autenticação utilizando senhas incorretas ou usuários inexistentes para validar credenciais.

---

# Evidências observadas

Durante a simulação foram registrados eventos compatíveis com:

- Falhas consecutivas de autenticação;
- Tentativas de acesso ao serviço SSH;
- Geração de logs pelo OpenSSH;
- Correlação automática realizada pelo Wazuh.

---

# Serviço afetado

- SSH (TCP/22)

---

# Tecnologia de detecção

- Wazuh SIEM
- Wazuh Agent
- OpenSSH Logs

---

# Avaliação do Analista

Não houve comprometimento do servidor ou obtenção de acesso.

O comportamento observado corresponde a uma tentativa de força bruta contra o serviço SSH, prática frequentemente utilizada por agentes maliciosos para obtenção inicial de acesso.

---

# Conclusão

O incidente foi corretamente classificado como uma tentativa de **Brute Force (T1110)** pertencente à tática **Credential Access (TA0006)** da matriz MITRE ATT&CK.

A simulação demonstrou a capacidade do laboratório em detectar, correlacionar e investigar esse tipo de atividade de forma semelhante a um ambiente corporativo.

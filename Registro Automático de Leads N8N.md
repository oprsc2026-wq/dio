# Documentação de Automação: Registro Automático de Leads N8N

> Gerado pelo GeraPrompt em 13/10/2026 18:50

## 1. Definição do Processo
- **Tarefa a Automatizar:** Registrar automaticamente leads recebidos por formulário
- **Público/Responsável:** Equipe comercial e time de vendas
- **Resultado Esperado:** Salvar os dados em uma planilha e enviar uma notificação para o time de vendas

## 2. Contexto Operacional & Regras de Negócio
- **Ferramentas Integradas:** Google Forms, Google Sheets, Gmail e N8N
- **Fluxo Sequencial:**
1. Receber uma nova resposta do formulário
2. Registrar os dados na planilha Google Sheets
3. Enviar um e-mail de confirmação ao lead

- **Regras e Validações:** Ignorar registros sem e-mail corporativo válido. Reenviar notificação se falhar.

## 3. Arquitetura de Nós N8N
### Nós Recomendados no N8N para este Fluxo:

- **Trigger Node**: Início do fluxo via Webhook / Cron / App Event (baseado em: Google Forms, Google Sheets, Gmail e N8N).
- **Data Validation & Filter Node (If / Filter)**: Validação das regras de negócio (Ignorar registros sem e-mail corporativo válido. Reenviar notificação se falhar.).
- **Transformation Node (Code / Set)**: Mapeamento dos campos dos leads e normalização de dados.
- **Service Integration Nodes**: Integração com ferramentas destino para alcançar: Salvar os dados em uma planilha e enviar uma notificação para o time de vendas.
- **Error Trigger**: Fluxo de fallback em caso de falha de conexão ou timeout.


## 4. Prompt Especialista para Inteligência Artificial
```text
Atue como um especialista em N8N e Engenharia de Automações.

Crie uma automação para Registrar automaticamente leads recebidos por formulário.

Público ou responsável:
Equipe comercial e time de vendas

Resultado esperado:
Salvar os dados em uma planilha e enviar uma notificação para o time de vendas

Ferramentas envolvidas:
Google Forms, Google Sheets, Gmail e N8N

Fluxo desejado:
- 1. Receber uma nova resposta do formulário
- 2. Registrar os dados na planilha Google Sheets
- 3. Enviar um e-mail de confirmação ao lead

Regras importantes:
Ignorar registros sem e-mail corporativo válido. Reenviar notificação se falhar.

Requisitos de entrega:
1. Explique quais nós do N8N devem ser utilizados (Triggers, Actions, Transforms, Error Handlers).
2. Apresente a lógica de funcionamento e o payload trafegado entre os nós.
3. Adicione instruções para tratamento de erro e resiliência no fluxo.

```

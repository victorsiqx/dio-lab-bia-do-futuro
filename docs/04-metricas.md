# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação pode ser feita de duas formas complementares:

1. **Testes estruturados:** Você define perguntas e respostas esperadas;
2. **Feedback real:** Pessoas testam o agente e dão notas.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu o que foi perguntado? | Perguntar o saldo e receber o valor correto |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência** | A resposta faz sentido para o perfil do cliente? | Sugerir investimento conservador para cliente conservador |

> [!TIP]
> Peça para 3-5 pessoas (amigos, família, colegas) testarem seu agente e avaliarem cada métrica com notas de 1 a 5. Isso torna suas métricas mais confiáveis! Caso use os arquivos da pasta `data`, lembre-se de contextualizar os participantes sobre o **cliente fictício** representado nesses dados.

---

## Exemplos de Cenários de Teste

Crie testes simples para validar seu agente:

### Teste 1: Consulta de gastos
- **Pergunta:** "Quanto gastei com alimentação?"
- **Resposta esperada:** Valor baseado no `transacoes.csv`
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 2: Recomendação de produto
- **Pergunta:** "Qual investimento você recomenda para mim?"
- **Resposta esperada:** Produto compatível com o perfil do cliente
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo?"
- **Resposta esperada:** Agente informa que só trata de finanças
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 4: Informação inexistente
- **Pergunta:** "Quanto rende o produto XYZ?"
- **Resposta esperada:** Agente admite não ter essa informação
- **Resultado:** [X] Correto  [ ] Incorreto

---

## Formulário de feedback
Use com os participantes do teste:

| Métrica | Pergunta | Nota (1-5)|
|---------|----------|-----------|
| Assertividade | "A resposta respondeu sua pergunta?" | ___ |
| Segurança | "As informações pareceram confiáveis?" | ___ |
| Coerência | "A linguagem foi clara e fácil de entender?" | ___ |


## Resultados

Após os testes, registre suas conclusões:

**O que funcionou bem:**
- Integração de Dados: O sistema conseguiu carregar corretamente os arquivos CSV e JSON, permitindo que as consultas sobre o saldo e o perfil do cliente fossem respondidas com base nos dados reais.
- Filtro de Escopo (Segurança): O agente demonstrou maturidade ao se recusar a responder perguntas fora do nicho financeiro (como a previsão do tempo), mantendo o papel de educador conforme definido no System Prompt.
- Interface Didática: A estrutura do Streamlit tornou a interação amigável, facilitando o uso para testes rápidos.

**O que pode melhorar:**
- Latência de Resposta: Com o modelo llama3:8b rodando localmente em uma máquina com 8GB de RAM, o tempo de resposta pode ser um pouco alto; seria ideal otimizar o prompt ou testar modelos ainda menores (como o phi3) se a velocidade for crítica.
- Gestão de Contexto: Em conversas mais longas, o agente pode começar a esquecer o histórico de atendimento anterior; melhorar a forma como o historico_atendimento.csv é lido ou sumarizado pode ajudar.
- Refinamento de Dados: As respostas sobre os produtos financeiros podem ser mais detalhadas se criarmos um prompt que incentive o agente a citar as regras de aporte mínimo descritas no arquivo produtos_financeiros.json.

---

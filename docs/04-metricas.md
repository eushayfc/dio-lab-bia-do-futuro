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

# Avaliação e Métricas

## Como avalio a qualidade do agente

O agente foi desenvolvido para atuar como analista de backoffice, com foco em identificar possíveis erros operacionais na rentabilidade de fundos.

### 1. Precisão na identificação de erros

Avalio se o agente identifica corretamente dias com comportamento fora da banda.

Exemplo:
- Dia 2026-03-10 contém erro real
- O agente deve identificar corretamente esse dia

Métrica:
- Acertos / Total de cenários testados

---

### 2. Taxa de falsos positivos

Avalio se o agente evita marcar dias normais como erro.

Métrica:
- Quantidade de dias incorretamente marcados como erro

---

### 3. Coerência com o mercado (IBOV)

O agente deve considerar o comportamento do IBOV como referência.

Métrica:
- Percentual de análises coerentes com o movimento do IBOV

---

### 4. Segurança da resposta

O agente não deve sugerir investimentos nem fazer análises de mercado.

Métrica:
- % de respostas alinhadas com o papel de backoffice

---

## Conclusão

O agente é considerado eficiente quando:

- Identifica corretamente outliers reais
- Evita falsos positivos
- Considera o contexto do IBOV
- Mantém foco em análise operacional

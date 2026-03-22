# 📊 Shay — Analista Inteligente 

Agente de backoffice especializado em **identificar erros operacionais de rentabilidade** em fundos de investimento, comparando histórico e benchmark (IBOV).

---

## O Problema

Fundos de investimento estão sujeitos a erros operacionais no lançamento diário da rentabilidade — valores fora da banda histórica ou em divergência com o mercado. Identificar esses erros manualmente é suscetível a falhas humanas.

## A Solução

A **Shay** é uma analista de backoffice baseada em IA que:

- 📈 Compara a rentabilidade diária do fundo com o histórico e o IBOV
- 🚨 Sinaliza automaticamente valores fora da banda esperada
- 💬 Responde perguntas dos analistas via chat, restrita ao escopo operacional

---

## Arquitetura

```
Analista → Interface (Streamlit) → LLM (Ollama/TinyLlama)
                                        ↓
                               Base de Conhecimento (CSV)
                                        ↓
                                  Validação → Resposta
```

---

## Base de Conhecimento

| Arquivo | Formato | Conteúdo |
|---------|---------|----------|
| `data/dados.csv` | CSV | Histórico de rentabilidade diária do fundo Shay vs. IBOV |

Os dados contêm: `data`, `fundo`, `rentabilidade`, `IBOV`.

---

## Prompts

**System Prompt — comportamento do agente:**

> Você é um analista de backoffice de fundos de investimento. Seu papel é identificar possíveis erros operacionais na rentabilidade. Identifique outliers, compare com o IBOV e sinalize dias suspeitos. Não responda sobre outros assuntos.

**Regras:**
- Fora da banda → `FORA DA BANDA: data -> rentabilidade (possível erro operacional)`
- Tudo normal → `TODOS OS DIAS DENTRO DO PADRÃO OPERACIONAL`
- Fora do escopo → `Pergunta fora do escopo da análise de fundos.`

---

## Como Rodar

```bash
pip install streamlit requests

# Certifique-se que o Ollama está rodando localmente
ollama run tinyllama

streamlit run src/app.py
```

---

## Métricas de Avaliação

| Métrica | Critério |
|---------|----------|
| Precisão na detecção de outliers | Identifica corretamente dias com erro real |
| Taxa de falsos positivos | Não marca dias normais como erro |
| Coerência com IBOV | Considera o mercado como referência |
| Segurança de escopo | Não extrapola o papel de backoffice |

---

## Limitações

- Não substitui um analista humano
- Não faz recomendações de investimento
- Não acessa dados externos em tempo real
- Baseado exclusivamente nos dados fornecidos

---

## Estrutura do Repositório

```
📁 lab-agente-financeiro/
├── data/dados.csv                    # Histórico do fundo Shay
├── docs/
│   ├── 01-documentacao-agente.md
│   ├── 02-base-conhecimento.md
│   ├── 03-prompts.md
│   ├── 04-metricas.md
│   └── 05-pitch.md
└── src/app.py                        # Aplicação Streamlit
```

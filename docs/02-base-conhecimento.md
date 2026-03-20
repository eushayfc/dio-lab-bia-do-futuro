# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Pra que serve a base |
|---------|---------|---------------------|
| `transacoes.csv` | CSV | Analisar o histórico das movimentações do fundo e encontrar algo fora da banda |

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

As transações foram substituidas por movimentações históricas do fundo Shay Previdência Multimercado

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Existem duaspossibilidades, injetar os dados diretamente no prompt (Ctrl + C, Ctrl + V) ou carregar os arquivos via código, como no exemplo abaixo.

'''python
import pandas as pd

#CSVs
transações = pd.read_csv('data/transações.csv')

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Para simplificar, podemos simplesmente "injetar" os dados em nosso prompt, garantindo que o agente tenha o maior historico possível. Em soluções mais robustas, o ideal é que essas informações sejam carregadas dinamicamente para que possamos ganhar flexibilidade.
'''text
DADOS DA NOTA (data/transações.csv):
(
data,nome,aplicação,resgate,patrimônio,rentabilidade
2026-03-20,Shay Previdência Multimercado,53.2,46.8,42.1,1.02
2026-03-19,Shay Previdência Multimercado,52.8,47.1,41.9,1.01
2026-03-18,Shay Previdência Multimercado,53.0,46.9,42.0,0.98
2026-03-17,Shay Previdência Multimercado,53.4,46.6,42.2,1.03
2026-03-16,Shay Previdência Multimercado,52.9,47.0,42.1,1.00
2026-03-13,Shay Previdência Multimercado,53.1,46.8,42.0,0.97
2026-03-12,Shay Previdência Multimercado,53.3,46.7,42.2,1.04
2026-03-11,Shay Previdência Multimercado,52.7,47.2,41.8,0.95
2026-03-10,Shay Previdência Multimercado,53.5,46.5,42.3,-0.42
2026-03-09,Shay Previdência Multimercado,53.2,46.8,42.1,1.02
)

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

Informações relevantes resumidas.

```
Movimentação do fundo:
- Nome: Shay Previdência Multimercado
- Patrimônio: 42.1
- Rentabilidade: 1.02
- Data: 2026-03-20

Últimas movimentações:
- aplicação: 53.2
- resgate: 46.8
...
```

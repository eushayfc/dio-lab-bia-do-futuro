# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Pra que serve a base |
|---------|---------|---------------------|
| `dados.csv` | CSV | Analisar o histórico das movimentações do fundo e encontrar algo fora da banda |

---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

As transações foram substituidas por movimentações históricas do fundo Shay 

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Existem duas possibilidades, injetar os dados diretamente no prompt (Ctrl + C, Ctrl + V) ou carregar os arquivos via código, como no exemplo abaixo.

'''python
import pandas as pd

#CSVs
dados  = pd.read_csv('data/dados.csv')

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

Para simplificar, podemos simplesmente "injetar" os dados em nosso prompt, garantindo que o agente tenha o maior historico possível. Em soluções mais robustas, o ideal é que essas informações sejam carregadas dinamicamente para que possamos ganhar flexibilidade.
'''text
DADOS DA NOTA (data/dados.csv):
(
data,fundo,rentabilidade,IBOV
2026-03-20,Shay,1.02,-2.25
2026-03-19,Shay,1.01,0.35
2026-03-18,Shay,0.99,-0.43
2026-03-17,Shay,1.03,0.30
2026-03-16,Shay,1.01,1.25
2026-03-13,Shay,0.98,-0.91
2026-03-12,Shay,1.00,-2.55
2026-03-11,Shay,0.97,0.28
2026-03-10,Shay,-0.42,1.40
2026-03-09,Shay,1.02,0.86
)

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente.

Informações relevantes resumidas.

```
Movimentação do fundo:
- Nome: Shay 
- Patrimônio: 42.1
- Rentabilidade: 1.02
- Data: 2026-03-20


